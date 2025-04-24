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
    <version>2.0.0</version> <!-- Use the newest version available! -->
    <relativePath />
</parent>
```

This parent POM contains all necessary settings for the GitHub Action to function properly.

### Add GitHub workflow

Add a GitHub workflow (e.g. by adding a file `.github/workflows/deploy.yaml` to your) to your project [as described here.](https://github.com/camunda-community-hub/community-action-maven-release#add-github-workflow)

### Performing a release

Create a new Release using https://github.com/camunda-community-hub/:repo/releases/new (replace `:repo` with name of repository). 

This will trigger the release flow, which uses `mvn release:prepare release:perform` to build, sign, and publish the released version to Maven Central, and will push the generated tags once the process has completed.

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

## Why do I have to migrate to [community-hub-release-parent](https://github.com/camunda-community-hub/community-hub-release-parent) v2?

Sonatype announced the [end-of-life of the legacy OSSRH](https://central.sonatype.org/news/20250326_ossrh_sunset/) service that the Community Hub historically used to publish to Maven Central. The [community-hub-release-parent](https://github.com/camunda-community-hub/community-hub-release-parent) POM v1 and the [Community Hub Maven Release GitHub Action](https://github.com/camunda-community-hub/community-action-maven-release) v1 only work against the legacy OSSRH service.

Publishing to Maven Central via the new [Central Portal](https://central.sonatype.org/faq/what-is-different-between-central-portal-and-legacy-ossrh/) service requires a different Maven Plugin and different settings in the parent POM and the GitHub Action. Since this is a breaking change, there is new major versions v2 available for both.

See the next FAQ entry for details on how to migrate.


## How to migrate to [community-hub-release-parent](https://github.com/camunda-community-hub/community-hub-release-parent) v2?

When you are publishing to the `org.camunda.community` Maven groupId on Maven Central via the [Community Hub Maven Release GitHub Action](https://github.com/camunda-community-hub/community-action-maven-release), you need to commit the following changes to your repository:

1. In your `pom.xml` change the `<parent>` section to use `<version>2.0.0</version>` (Use the newest version available!) of the [community-hub-release-parent](https://github.com/camunda-community-hub/community-hub-release-parent).
2. In your GHA workflow for publishing (e.g. `.github/workflows/deploy.yaml`) find the step named `Deploy SNAPSHOT / Release`:
    1. Change to `uses: camunda-community-hub/community-action-maven-release@v2`
    2. Change to `maven-usr: ${{ secrets.COMMUNITY_HUB_MAVEN_CENTRAL_CP_USR }}`
    3. Change to `maven-psw: ${{ secrets.COMMUNITY_HUB_MAVEN_CENTRAL_CP_PSW }}`
    4. Remove the line with `maven-url: ...` parameter if present

Publishing Maven SNAPSHOT and release builds just work as before but now via the [Central Portal](https://central.sonatype.org/publish/publish-portal-guide).

> [!IMPORTANT]  
> In case you consuming Maven SNAPSHOT artifacts from Maven Central, you now need to configure [a different URL](https://central.sonatype.org/publish/publish-portal-snapshots/#consuming-snapshot-releases-for-your-project) locally: https://central.sonatype.com/repository/maven-snapshots/


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
