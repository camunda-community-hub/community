# Transferring existing Camunda community extensions

## Why migrate to the hub?

The Camunda Community Hub aims to make the process of contributing to, maintaining, and using Camunda Community Extensions more efficient. This reduces a number of issues regarding the continued maintenance and infrastructure related to community extensions, creating a better experience for users as well as maintainers. Here are some advantages to your extension being listed under the Camunda Community Hub:

* Automated publishing of your Camunda extension's Maven releases to Maven Central, with more automation on the way for different programming languages
* Automated releases
* Automated issue and pull request labelling 
* Improved issue triage process 
* Improved visibility as to where an extension is in its lifecycle
* Consistent formatting of new issues and releases with new templates and tooling
* Visibility of your project for new contributors interested in getting involved with open source software

The Camunda Community Hub aims to help extension maintainers coordinate, cross-test, and ensure that extensions hosted under the Hub can be used without causing conflict with other applications.


## Maintainer and reviewer expectations

Please review our [maintainers guide](/maintainers-reviewers/maintainers-start-here.md) and [maintainer expectations](/docs/maintainer-reviewer-expectations.md) before initiating the process of transferring your repo.

## Transferring your repo

In order to work within the Camunda Community Hub, Maintainers are asked to transfer their repository into the Camunda Community Hub rather than fork it into the Hub. 

### Transferring a repository from your personal GitHub account or company's organization

Open an issue in your repository titled "Transfer (your repository) into the Camunda Community Hub" and assign it to `@camunda-community-hub/DevRel`, or tag the [Camunda DevRel team](https://github.com/orgs/camunda-community-hub/teams/devrel) in a comment on the issue itself if you are unable to assign the issue to them. 

A DevRel team member will identify themselves as the person to transfer the repository to. [Follow these instructions for transferring the repository to them](https://docs.github.com/en/repositories/creating-and-managing-repositories/transferring-a-repository#transferring-a-repository-owned-by-your-personal-account), then they will transfer it to the Community Hub and give you Admin access.

Once the repository has transferred, you can proceed to [the maintainer expectations page](/maintainers-reviewers/maintainer-reviewer-expectations.md) and follow the instructions there for what your README should contain.


## Maven and Docker setup
When onboarding, you will be asked if you would like to use our infrastructure for Maven and Docker. If so, [follow the onboarding instructions here. ](/maintainers-reviewers/RELEASE.MD)

## Personal information
When you migrate your extension into the Camunda Community Hub, we will receive your contact information and may occasionally reach out to you with questions, information, etc. 

You *will not* be added to any marketing lists, but you may be contacted by us or Camunda Community Hub open source contributors.