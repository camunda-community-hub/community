# How to build and release projects on the Camunda Community Hub

## Maven

In order to build and release your Maven projects properly, you need to prepare:

1. **[Onboard](#onboarding-your-repository) your repository** (which makes sure you will have all necessary credentials available)
2. Use the **[release parent pom](https://github.com/camunda-community-hub/community-hub-release-parent) in your Maven project (which will take care of distribution management)**
3. Setup a GitHub workflow leveraging the [Community Hub Maven Release **GitHub Action**](https://github.com/camunda-community-hub/community-action-maven-release) (which will take care to do the proper releases)

Then you can simply create GitHub releases, which will also trigger all necessary Maven magic to deploy to 

- [Camunda Artifactory](https://artifacts.camunda.com/)
- [Maven Central](https://central.sonatype.com/publishing/deployments)

> View an example repository demonstrating the setup of Maven Build Management and CI/CD [here.](https://github.com/camunda-community-hub/community-hub-extension-example) 

More information [below](#maven-1).


## Docker

In order to build and release Docker images, you need to prepare:

1. **[Onboard](#onboarding-your-repository) your repository** (which makes sure you will have all necessary credentials available)
2. Use the **image name** `camundacommunityhub/*`
3. Setup a GitHub workflow to push your Docker images to Dockerhub. We recommend using the [official Docker login GitHub Action.](https://github.com/marketplace/actions/docker-login)

More information [below](#docker-1).


# Detailed instructions

## Onboarding your repository

You need to register your repository by opening a pull request in the [Camunda Infrastructure](https://github.com/camunda-community-hub/infrastructure) repo and follow the instructions listed for [onboarding a new repository](https://github.com/camunda-community-hub/infrastructure#use-case-onboarding-a-new-community-hub-repository).


## Maven

> View an example repository demonstrating the setup of Maven Build Management and CI/CD [here.](https://github.com/camunda-community-hub/community-hub-extension-example) 

### Use the Camunda Community Hub groupId

The Camunda Community Hub decided on a unified groupId. Use a Maven groupId based on: `org.camunda.community`, so for example: `org.camunda.community.awesomeextension`

### Add release parent to POM

Any project needs to use the [community-hub-release-parent](https://github.com/camunda-community-hub/community-hub-release-parent) in their POM:

```xml
<parent>
    <groupId>org.camunda.community</groupId>
    <artifactId>community-hub-release-parent</artifactId>
    <version><!-- Use the newest version available! --></version>
    <relativePath />
</parent>
```

This parent POM contains all necessary settings for the GitHub Action to function properly.

### Add GitHub workflow

Add a GitHub workflow (e.g. by adding a file `.github/workflows/deploy.yaml` to your) to your project [as described here.](https://github.com/camunda-community-hub/community-action-maven-release#add-github-workflow)

### Performing a release

Create a new Release using https://github.com/camunda-community-hub/:repo/releases/new (replace `:repo` with name of repository). 

This will trigger the release flow, to build, sign, and publish the released version to Maven Central, and will push the generated tags once the process has completed.

There are two options:

1. Use the **auto release property** in your GitHub workflow (**recommended**), so that all releases will be automatically be released to Maven Central:

```yaml
# ...snip...

     - name: Deploy SNAPSHOT / Release
       uses: camunda-community-hub/community-action-maven-release@v2
       with:
          maven-auto-release-after-close: true
          # ...

# ...snip...
```

2. Open an issue to let [@camunda-community-hub/devrel](https://github.com/orgs/camunda-community-hub/teams/devrel) review and release your artifact. Therefore, open a new issue in your repository and include [@camunda-community-hub/devrel](https://github.com/orgs/camunda-community-hub/teams/devrel) in a comment with a waiting-for-camunda [issue label](https://github.com/camunda-community-hub/template-repo/labels) applied. 

After an artifact has been released, it can take up to an hour to be retrievable, and 2-3 hours for it to be reflected on the public page of the artifact.


## Docker

[TBD]


# FAQ

## Migration to Sonatype Central Portal — How To?

### What You Need to Know

Sonatype is [retiring OSSRH](https://central.sonatype.org/news/20250326_ossrh_sunset/) in favor of their new [Central Portal](https://central.sonatype.org/faq/what-is-different-between-central-portal-and-legacy-ossrh/) for publishing artifacts.

As part of this change, all Camunda namespaces (`io.camunda`, `io.zeebe`, and `org.camunda`) will be migrated to the new Central Portal.  
> **Note:** This migration is one-way, once a namespace is migrated, publishing via OSSRH will no longer be possible.

### What’s Changing for You

To support this transition, we have added a new Maven profile in the parent POM used by community projects:

- ✅ `central-sonatype-publish` (for Central Portal)
- ⚠️ `oss-maven-central` (now deprecated)

The composite GitHub Action `camunda-community-hub/community-action-maven-release@v2` handles failover per namespace, from OSSRH to the Central Portal.  
You do **not** need to track namespace-specific timelines yourself, as long as you are using the latest `@v2` version of the action.

### What You Need to Do

To ensure a seamless migration for your Camunda community project, it’s recommended to take the following steps now, you don’t need to wait for the namespace migration to be completed:

1. **Update the parent POM** to get the new `central-sonatype-publish` profile available:
   - `org.camunda.community:community-hub-release-parent` → version `2.0.0` (or higher)

2. **Update the GitHub Action** to use `@v2`:
   - Use `camunda-community-hub/community-action-maven-release@v2`
        - if you prefer not to use the @v2 tag, make sure to regularly update to the latest v2 release. The automatic fallback from the deprecated `oss-maven-central` profile to the new `central-sonatype-publish` profile will be handled via v2 patch releases, aligned with the migration timeline of each namespace
   - Ensure the following changes are applied to its configuration:
     - ✅ **Use the new default central release profile** by removing any explicit `central-release-profile` value (default is now `central-sonatype-publish`)
         - as long as the `central-sonatype-publish` profile is used, a fallback from OSSRH to the Central Portal is handled by the action for a smooth transition
     - 🆕 Add new credentials for the Central Portal:
       ```yaml
       central-sonatype-usr: ${{ secrets.COMMUNITY_HUB_MAVEN_CENTRAL_CP_USR }}
       central-sonatype-psw: ${{ secrets.COMMUNITY_HUB_MAVEN_CENTRAL_CP_PSW }}
       ```
     - 🧩 Keep the following **deprecated parameters** for now, at least until the concerned namespaces are migrated (they will be ignored afterwards and removed in `@v3`):
       ```yaml
       maven-usr: ${{ secrets.<...> }}
       maven-psw: ${{ secrets.<...> }}
       maven-url: (s01.)?oss.sonatype.org
       ```

> ✅ When the namespace migration occurs, no further changes will be needed. The `@v2` (and subsequent patch versions) of the action will use the appropriate profile and credentials.

> 📌 For a concrete example of the required changes, see this sample [PR](https://github.com/camunda-community-hub/community-hub-extension-example/pull/30
) in the `camunda-community-hub/community-hub-extension-example` project.

### What About SNAPSHOT and Release Builds?

Publishing both SNAPSHOT and release builds will continue to work as before—just now via the [Central Portal](https://central.sonatype.org/publish/publish-portal-guide).

> [!IMPORTANT]  
> If you consume Maven SNAPSHOT artifacts, you **must update the repository URL** in your local setup:  
> [Guide for consuming SNAPSHOT releases](https://central.sonatype.org/publish/publish-portal-snapshots/#consuming-snapshot-releases-for-your-project)  
> New URL: `https://central.sonatype.com/repository/maven-snapshots/`

## What if my release fails while deploying integration tests?

Integration tests should be versioned when preparing a release, but should never be deployed to Maven Central. If you have an integration-tests module in your project, add the following profile to your parent POM:

```
<profiles>
    <profile>
        <id>it</id>
        <activation>
            <property>
                <name>performRelease</name>
                <value>!true</value>
            </property>
        </activation>
        <modules>
            <module>integration-test</module>
        </modules>
    </profile>
</profiles>
```

This will ensure that when the `mvn release:perform `is triggered (with the `-DperformRelease` flag set) the `integration-tests` module is skipped.


## What if my release says it's missing a key for GPG?

Verify that you have adjusted your extension's release workflow GPG files to match the example shown in the [Community Action Maven Release](https://github.com/camunda-community-hub/community-action-maven-release/blob/22004c20cb61979859e889cf17081b3e886849b8/example-workflows/java11/deploy.yml#L25-L30) documentation. For more information on Java setup actions and what GPG does, review the [documentation on GitHub](https://github.com/actions/setup-java/blob/main/docs/advanced-usage.md#gpg).


## Integrating GitHub Actions with Zeebe on Camunda 8

If you are interested in working with GitHub Actions using Zeebe on Camunda 8, visit our [Camunda 8 GitHub Action](https://github.com/camunda-community-hub/camunda-cloud-github-action) repository to get started.


## Troubleshooting

1. If you are facing any issues regarding your extension's release process, please [open an issue](https://github.com/camunda-community-hub/community-action-maven-release/issues) and assign it to [@camunda-community-hub/devrel](https://github.com/orgs/camunda-community-hub/teams/devrel) with applicable issue labels applied.
2. If you see an update or improvement that can be made to the release process in the Camunda Community Hub, we encourage you to submit an issue with your request, and thank you for your suggestion!
3. Please make use of the [Camunda Community Hub Pull Request Template](https://github.com/camunda-community-hub/community/issues/new?assignees=&labels=&template=camunda-community-hub-pull-request-template.md&title=Pull+Request) when opening a troubleshooting pull request and include as much information as possible in order to help reviewers better understand the issue you are facing.
