# Automated releasing to Maven Central

Releases are automated in the Camunda Community Hub via GitHub Actions. This contains the core release workflow that is required to publish Java-based Community Extensions for [Camunda Platform](https://camunda.com/products/camunda-bpm/) to Maven Central. The necessary credentials to tag in GitHub and push to Maven Central need to be set up as secrets in each repository.

### Performing a release

To perform a release, a repository Maintainer should create a new Release using https://github.com/camunda/:repo/releases/new (replace `:repo` with name of repository). 

This will trigger the release flow, which uses `mvn release:prepare release:perform` to build, sign, and deploy the released version to Maven Central, and will push the generated tags once the process has completed.

> ![A BPMN diagram of the release workflow](https://i.imgur.com/bx51tdE.png)
> Image description: BPMN workflow <code> StartEvent</code> with the text, 'Are you Maintainer?' branching to 'Create issue to ask maintainer for release,' and an <code>EndEvent</code>. 
> The gateway branches into a <code>SendTask</code>that is 'Create release with X,Y,Z' a <code>RecieveTask</code> that is 'Wait for workflow', a <code>Task</code> that is, 'Ask for signing of the release,' and finally a <code>EndEvent</code>
> The event Sub-Task <code>ReceiveTask</code> 'Release triggers workflow' begins, the <code>Task</code>'Perform mvn release,' is completed, and the <code>SendTask</code>'Workflow done' task ends.

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

