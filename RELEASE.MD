# How to build and release projects on the Camunda Community Hub

## Maven

In order to build and release your Maven projects properly, you need to prepare:

1. **[Onboard](#onboarding-your-repository) your repository** (which makes sure you will have all necessary credentials available)
2. Use the **[release parent pom](https://github.com/camunda-community-hub/community-hub-release-parent) in your Maven project (which will take care of distribution management)**
3. Setup a GitHub workflow leveraging the [Community Hub Maven Release **GitHub Action**](https://github.com/camunda-community-hub/community-action-maven-release) (which will take care to do the proper releases).

Then you can simply create GitHub releases, which will also trigger all necessary Maven magic to deploy to 

- [Camunda Artifactory](https://artifacts.camunda.com/)
- [Sonatype](https://oss.sonatype.org/#stagingRepositories) (aka Maven Central)

More information below.

## Docker

In order to build and release Docker images, you need to prepare:

1. **[Onboard](#onboarding-your-repository) your repository** (which makes sure you will have all necessary credentials available)
2. Use the **image name** `camundacommunityhub/*`
3. Setup a GitHub workflow to push your Docker images to Dockerhub. We recommend using the [official Docker login GitHub Action.](https://github.com/marketplace/actions/docker-login)

More information below.

# Detailed instructions

## Onboarding your repository

You need to register your repository by opening a pull request in the [Camunda Infrastructure](https://github.com/camunda-community-hub/infrastructure) repo and follow the instructions listed for [onboarding a new repository](https://github.com/camunda-community-hub/infrastructure#use-case-onboarding-a-new-community-hub-repository).

## Maven

### Use common groupId

The Camunda Community Hub decided on a unified groupId. Use a Maven groupId based on: `org.camunda.community`, so for example: `org.camunda.community.awesomeextension`

### Add release parent to POM

Any project needs to use the [community-hub-release-parent](https://github.com/camunda-community-hub/community-hub-release-parent) in their POM:

```xml
<parent>
    <groupId>org.camunda.community</groupId>
    <artifactId>community-hub-release-parent</artifactId>
    <version>1.4.3</version>
    <relativePath />
</parent>
```

This parent POM contains all necessary settings for the GitHub action to function properly.

### Add GitHub workflow

[Add a GitHub workflow (e.g. by adding a file `.github/workflows/deploy.yaml` to your) to your project as described here.](https://github.com/camunda-community-hub/community-action-maven-release#add-github-workflow)


### Performing a release


Create a new Release using https://github.com/camunda-community-hub/:repo/releases/new (replace `:repo` with name of repository). 

This will trigger the release flow, which uses `mvn release:prepare release:perform` to build, sign, and deploy the released version to Maven Central, and will push the generated tags once the process has completed.

There are two options:

1. Use the **auto release property** in your GitHub workflow (**recommended**), so that all releases will be automatically be released to Maven Central:

```
...
     - name: Deploy SNAPSHOT / Release
        uses: camunda-community-hub/community-action-maven-release@v1
        with:
          ...
          maven-auto-release-after-close: true
          ...
```
:warning: Please, note, that this functionality starts to work in `community-hub-release-parent` with version `1.4.1`. [Source](https://github.com/camunda-community-hub/kotlin-coworker/issues/42#issuecomment-1432808578).

2. Open an issue to let [@camunda-community-hub/devrel](https://github.com/orgs/camunda-community-hub/teams/devrel) review and release your artifact. Therefore, open a new issue in your repository and include [@camunda-community-hub/devrel](https://github.com/orgs/camunda-community-hub/teams/devrel) in a comment with a waiting-for-camunda [issue label](https://github.com/camunda-community-hub/template-repo/labels) applied. 

After an artifact has been released, it can take up to an hour to be retrievable, and 2-3 hours for it to be reflected on the public page of the artifact.

## Docker

[TBD]

# FAQ

### What if my release fails while deploying integration tests?

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

### What if my release says it's missing a key for GPG?

Verify that you have adjusted your extension's release workflow GPG files to match the example shown in the [Community Action Maven Release](https://github.com/camunda-community-hub/community-action-maven-release/blob/22004c20cb61979859e889cf17081b3e886849b8/example-workflows/java11/deploy.yml#L25-L30) documentation. For more information on Java setup actions and what GPG does, review the [documentation on GitHub](https://github.com/actions/setup-java/blob/main/docs/advanced-usage.md#gpg).

## Integrating GitHub Actions with Zeebe on Camunda Cloud

If you are interested in working with GitHub Actions using Zeebe on Camunda Cloud, visit our [Camunda Cloud GitHub Action](https://github.com/camunda-community-hub/camunda-cloud-github-action) repository to get started.

## Troubleshooting

1. If you are facing any issues regarding your extension's release process, please [open an issue](https://github.com/camunda-community-hub/community-action-maven-release/issues) and assign it to [@camunda-community-hub/devrel](https://github.com/orgs/camunda-community-hub/teams/devrel) with applicable issue labels applied.
2. If you see an update or improvement that can be made to the release process in the Camunda Community Hub, we encourage you to submit an issue with your request, and thank you for your suggestion!
3. Please make use of the [Camunda Community Hub Pull Request Template](https://github.com/camunda-community-hub/community/issues/new?assignees=&labels=&template=camunda-community-hub-pull-request-template.md&title=Pull+Request) when opening a troubleshooting pull request and include as much information as possible in order to help reviewers better understand the issue you are facing.

