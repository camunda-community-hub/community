# Relocation of the GroupId

The Camunda Community Hub decided for a unified GroupId of `org.camunda.community`. Therefore, all contributors will require a bit of work to switch their repositories to the new GroupId.

Maven differentiates between two ways of how to approach this topic. Please look at the [official documentation](https://maven.apache.org/guides/mini/guide-relocation.html) for more information.
The `Working on past versions` is not supported as the Camunda Nexus does not have an automatic nor manual sync to Maven Central.
`Releasing the next version` on the other hand is something that can be utilized and will inform future users about the relocation.

### Performing a relocation for a future version

The following will describe a procedure of how one could tackle the relocation for future releases with the given tools (maven release action).
In total, we'll do two releases with two different groupIds for the same version. If a person consumes the latest version of the old groupId, a warning will be issued that mentions the relocation to the new groupId.
```
[WARNING] While downloading org.camunda.infra.githubdemo:camunda-infra-githubdemo:2.0.0
  This artifact has been relocated to org.camunda.community.infra.githubdemo:camunda-infra-githubdemo:2.0.0.
  It was decided on a unified GroupId
```

1. Create a branch of the primary branch, e.g., called `relocation`. It will be used later to publish the relocation pom.
2. On the primary branch - Update your repository with the new groupId, e.g., in the `pom.xml` but also don't forget to move your src from `/foo/bar` to `/org/camunda/community/bar`
3. Create a new release based on the updated branch with the new groupId. As an example, we'll go with 2.0.0.
4. Switch back to the backup branch `relocation` and add the following to the `distributionManagement`.
```
<relocation>
	<groupId>org.camunda.community.bar</groupId>
	<message>Custom message that YOU can either omit or define for YOUR userbase.</message>
</relocation>
```
5. Rename your 2.0.0 tag to 2.0.0-new, e.g., by using the GitHub UI. `https://github.com/org/repo/releases/edit/2.0.0`. Editing the tag will create a new tag based on the latest primary branch commit but not cause an additional release.
6. Delete the old 2.0.0 tag as we have to reuse the tag to publish the old POM. Either use the GitHub UI or run `git push --delete origin 2.0.0` in your repo with the adjusted tag version.
7. Create a new release based on the backup branch `relocation` with the same version number 2.0.0.

From then on, you can publish every new release under the new groupId. People using the old groupId will be informed about the change if they consume the old groupId.
