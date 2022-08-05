# The Pull Request Process
## Pull requests are the backbone of any open source project. This section will introduce you to the best practices for opening a pull request to a Camunda Community Hub extension, and aims to serve as a point of reference for not only new contributors, but those who may contribute to open source software less frequently.

This guide is intended for those who already have a pull request to submit to a Camunda Community Hub Extension. If you are interested in submitting a pull request that is related to the commercial offerings of Camunda Cloud or the Camunda Platform, please visit [How to Contribute](https://camunda.com/developers/how-to-contribute/). 

### Creating a pull request

* Follow the directions included in the [pull request template](https://github.com/Camunda-Community-Hub/community/issues/new/choose). This will help the community members and/or extension maintainers who respond to your pull request.
* If a pull request is a typo/grammatical error fix, please make sure that you review the entire document for potential errors. Don’t open separate PRs for small fixes included in the same document.
* Reference any open issues that your PR can solve, or issues that it is related to.
* Avoid making large changes in a single commit. Instead, break your request into smaller pieces. This will ensure that reviewers are able to review your PR in a timely manner.
* Use comments where needed to add additional context
* Don’t assign an excessive amount of reviewers. If a reviewer is not automatically assigned via the Camunda Community Probot, /assign the pull request to the most relevant project maintainer
* If your PR is considered a Work-in-Progress [WIP], adding that prefix in your PR title will prevent the PR from being merged until the WIP or /hold command is lifted.
*  * This can also be achieved by setting your PR as a [`Draft Pull Request`](https://github.blog/2019-02-14-introducing-draft-pull-requests/) on GitHub
* If your PR has not been reviewed within 14 days, please don’t close your PR and re-open it. Please @ your reviewer and alert a Camunda team member, who will help you triage the pull request if need be.
* If you feel that your PR isn’t getting the attention it deserves, please post it in the relevant extension’s thread on the [Community Forums](https://forum.camunda.org/c/community-extensions/13) to find additional reviewers.

### Example PR description:

References Issues #021 #009

Fix to [xyz feature] was added to resolve bug referenced in #021, #009. All builds now pass, and the extension is performing as expected.

<code> /lm needs-review, community-extension, bug-fix</code>
<code>/assign @approver1 @approver2 @approver3</code>

### What’s included in the example issue description:

* Reference to other issues or PRs (#021, #009)
* Additional context around the changes that were made in the PR
* The <code>/lm </code>command automatically assigns the 'needs review', 'community extension', and 'bug fix' labels to the issue
* The <code>/assign </code> command assigns reviewers to a pull request. Maintainers or reviewers will /approve a PR after it has been approved and no changes are requested.
* Work-In-Progress pull requests

If you are working on a pull request with many moving parts, we strongly recommend that you break up your request into smaller PRs, rather than one large PR with many lines of code to review. This helps Community Extension Maintainers review and approve your pull requests quickly. 

If you add a [WIP] title to your pull request, or issue a /hold comment, the Camunda GitHub Probot will add the do-not-merge/work in progress label to your issue, and the do-not-merge/hold labels, respectively. While either of these labels is active on your pull request, it will not be considered for merging by a Maintainer or a Reviewer. 
