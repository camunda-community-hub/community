# Automated releasing to Maven Central

Releases are automated in the Camunda Community Hub via [GitHub Actions](https://github.com/camunda-community-hub/community-action-maven-release). This contains the core release workflow that is required to publish Java-based Community Extensions for [Camunda Platform 7](https://camunda.com/platform-7/) to Maven Central. The necessary credentials to tag in GitHub and push to Maven Central need to be set up as secrets in each repository.

## Performing a release

**You must be a member of the Camunda Community Hub to work with the Infrastructure repo.**

1. If this is your first release in the Camunda Community Hub, you will then need to register your repository by opening a pull request in the [Camunda Infrastructure](https://github.com/camunda-community-hub/infrastructure) repo and follow the instructions listed for [onboarding a new repository](https://github.com/camunda-community-hub/infrastructure#use-case-onboarding-a-new-community-hub-repository).

2. Make sure to update your POM using the credentials and instructions found in the [Community Action Maven Release documentation](https://github.com/camunda-community-hub/community-action-maven-release)

3. Create a GitHub Action in your repository copying the code from [Community Action Maven Release documentation](https://github.com/camunda-community-hub/community-action-maven-release) 

4. Create a new Release using https://github.com/camunda-community-hub/:repo/releases/new (replace `:repo` with name of repository). 

5. This will trigger the release flow, which uses `mvn release:prepare release:perform` to build, sign, and deploy the released version to Maven Central, and will push the generated tags once the process has completed.

> ![A BPMN diagram of the release workflow](https://github.com/camunda-community-hub/community/blob/main/assets/release-new-version%20(1).png)
> Image description: To be updated.
> The gateway branches into a <code>SendTask</code>that is 'Create release with X,Y,Z' a <code>RecieveTask</code> that is 'Wait for workflow', a <code>Task</code> that is, 'Ask for signing of the release,' and finally a <code>EndEvent</code>
> The event Sub-Task <code>ReceiveTask</code> 'Release triggers workflow' begins, the <code>Task</code>'Perform mvn release,' is completed, and the <code>SendTask</code>'Workflow done' task ends.

6. After a new release has been built and staged, your next step is to open a new issue in your repository and assign it to [@camunda-community-hub/devrel](https://github.com/orgs/camunda-community-hub/teams/devrel) with a waiting-for-camunda [issue label](https://github.com/camunda-community-hub/template-repo/labels) applied. They will then review your pull request and release the artifact to Maven Central. After an artifact has been released, it can take up to an hour to be retrievable, and 2-3 hours for it to be reflected on the public page of the artifact.

## FAQ

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

