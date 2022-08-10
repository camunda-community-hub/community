# Contributor Guide

[fork]: /fork
[pr]: /compare
[CODE_OF_CONDUCT]: CODE_OF_CONDUCT.MD

Hi there! We're thrilled that you'd like to contribute to this project. Your help is essential for keeping it great.

Please note that this project is released with a [Contributor Code of Conduct](https://github.com/camunda-community-hub/community/blob/main/CODE_OF_CONDUCT.MD). By participating in this project you agree to abide by its terms.

- [Issues and PRs](#issues-and-prs)
- [Submitting a pull request](#submitting-a-pull-request)
- [Code Camunda community extension contributions](#code-camunda-community-extension-contributions)
- [Automated releases](#automated-releases)
  - [groupId](#groupid)
- [Non-code Camunda community extension contributions](#non-code-camunda-community-extension-contributions)
  - [Event-Based community roles](#event-based-community-roles)
  - [Community education and onboarding](#community-education-and-onboarding)
  - [Issue triage](#issue-triage)
  - [Post-code specific contributions](#post-code-specific-contributions)
  - [Help project maintainers write release notes for their extension](#help-project-maintainers-write-release-notes-for-their-extension)
- [Resources](#resources)

## Issues and PRs

If you have suggestions for how this project could be improved, or want to report a bug, open an issue! We'd love all and any contributions. If you have questions, too, we'd love to hear them.

We'd also love PRs. If you're thinking of a large PR, we advise opening up an issue first to talk about it, though! Look at the links in [Resources](#resources) if you're not sure how to open a PR.

## Submitting a pull request

Please feel free to fork this repository and open a pull request to update this documentation.

Work in Progress pull requests are also welcome to get feedback early on, or if there is something blocking you that you would like an additional person to take a look at.

For more guidance around pull requests, visit our [Pull Request Process](/Users/miamoore/community/pull-request-process.md).

## Code Camunda community extension contributions

While we have guidelines for every project in this organization, each one has its own preferences for accepting contributions. Check the repo for any specific guidance for contributing code.

We also have guidelines for [Maintainer and Reviewer expectations.](maintainer-reviewer-expectations.md)

## Automated releases

For more information on automated releases and how you can utilize automated releasing to Maven Central in the Camunda Community Hub, please view our [automated release](https://github.com/camunda-community-hub/community/blob/main/RELEASE.MD) documentation.

### groupId 

The Camunda Community Hub members have decided to operate under a centralized groupId as of January 15th, 2021:

```
org.camunda.community
```

To make use of this centralized groupId in your own projects, including how to relocate your extension's GroupID, please review our [documentation.](groupId.md)

1. Add GitHub Action [as decribed here](https://github.com/camunda-community-hub/community-action-maven-release#add-github-workflow). Check that the build is working when you push code to your repo. 

2. When you are ready to release, follow [performing a release](https://github.com/camunda-community-hub/community/blob/main/RELEASE.MD#performing-a-release).


## Non-code Camunda community extension contributions

If you are interested in contributing to any Camunda Community Hub extension, there are a variety of ways to get involved without having to have coding experience: These include issue triage, writing documentation, and much, much more.

### Event-Based community roles

* Host or organize a [Camunda Community Meetup](https://camunda.com/events/)
* Present your work with Camunda at Meetups
* Start [a new Camunda event](https://camunda.com/events/meetups/) near you

### Community education and onboarding

* Help new contributors get started working with the Hub, finding a repository to contribute to, forking a repo, and making their first pull request
* Getting people involved in writing documentation and issue triage
* Spreading the word about the Camunda Community Hub to the broader open source community
* Answering questions on Slack, Discourse, GitHub Project boards, and the Camunda Cloud community forums
* Create community content
* Write a blog post about your experience with Camunda, how you built a Community Hub Extension, etc.
* Be a guest on our [Camunda Nation](https://www.buzzsprout.com/454051) podcast
* Write walkthroughs, how-to guides, and more

### Issue triage

* Labelling issues in Camunda Community Extension repositories
* Helping to triage issues by following up where needed, closing stale issues, and more
* For more information on how to get started with issue triage and labelling, including what issue labels and pull request automation we use in the Camunda Community Hub, please read the [documentation.](https://github.com/camunda-community-hub/community/blob/main/issue-triage.md)

### Post-code specific contributions

These are roles that are not code-based, but require some knowledge in that you will need to have an understanding of the Camunda community extension ecosystem, the Camunda codebase, or general programming knowledge.

### Help project maintainers write release notes for their extension

* GitHub management (tags, repositories, etc.)
* Mentoring new contributors and ensuring they have the tools they need to succeed when contributing to a Camunda Community Hub open source project
* Writing new or editing existing documentation
* Updating communication guidelines and expectations

## Resources

- [How to Contribute to Open Source](https://opensource.guide/how-to-contribute/)
- [Using Pull Requests](https://help.github.com/articles/about-pull-requests/)
- [GitHub Help](https://help.github.com)
- [Camunda Code of Conduct](https://github.com/camunda-community-hub/community/blob/main/CODE_OF_CONDUCT.MD)
