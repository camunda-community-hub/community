# Automated releasing to Maven Central

Releases are automated in the Camunda Community Hub via [GitHub Actions](https://github.com/camunda-community-hub/community-action-maven-release). This contains the core release workflow that is required to publish Java-based Community Extensions for [Camunda Platform](https://camunda.com/products/camunda-bpm/) to Maven Central. The necessary credentials to tag in GitHub and push to Maven Central need to be set up as secrets in each repository.

### Performing a release

1. To perform a new release, a repository Maintainer should create a new Release using https://github.com/camunda-community-hub/:repo/releases/new (replace `:repo` with name of repository). 

2/ This will trigger the release flow, which uses `mvn release:prepare release:perform` to build, sign, and deploy the released version to Maven Central, and will push the generated tags once the process has completed.

> ![A BPMN diagram of the release workflow](https://i.imgur.com/bx51tdE.png)
> Image description: BPMN workflow <code> StartEvent</code> with the text, 'Are you Maintainer?' branching to 'Create issue to ask maintainer for release,' and an <code>EndEvent</code>. 
> The gateway branches into a <code>SendTask</code>that is 'Create release with X,Y,Z' a <code>RecieveTask</code> that is 'Wait for workflow', a <code>Task</code> that is, 'Ask for signing of the release,' and finally a <code>EndEvent</code>
> The event Sub-Task <code>ReceiveTask</code> 'Release triggers workflow' begins, the <code>Task</code>'Perform mvn release,' is completed, and the <code>SendTask</code>'Workflow done' task ends.

3. You will then need to register your repository by opening a pull request in the [Camunda Infrastructure](https://github.com/camunda-community-hub/infrastructure) repo and follow the instructions listed for [onboarding a new repository](https://github.com/camunda-community-hub/infrastructure#use-case-onboarding-a-new-community-hub-repository).

4. After your release workflow has been set up using GitHub Actions and a new release has been built and staged, your next step is to open a new issue in your repository and assign it to [@celanthe](https://github.com/celanthe) with a waiting-for-camunda [issue label](https://github.com/camunda-community-hub/template-repo/labels) applied. They will then review your pull request and release the artifact to Maven Central. After an artifact has been released, it can take up to an hour to be retrievable, and 2-3 hours for it to be reflected on the public page of the artifact.

### FAQ

#### What if my release fails while deploying integration tests?

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

### Integrating GitHub Actions with Zeebe on Camunda Cloud

If you are interested in working with GitHub Actions using Zeebe on Camunda Cloud, visit our [Camunda Cloud GitHub Action](https://github.com/camunda-community-hub/camunda-cloud-github-action) repository to get started.

