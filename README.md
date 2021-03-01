# Welcome to the Camunda Community Hub!
## A project to empower our open source community extension maintainers, and encourage new contributors to get started contributing to the Camunda open source ecosystem. 

**Table of Contents**

- [What is the Camunda Community Hub](#what-is-the-camunda-community-hub)
- [Why migrate to the hub](#why-migrate-to-the-hub)
- [Getting started](#getting-started)
- [Sign the CLA and agree to the Code of Conduct](#sign-the-cla-and-agree-to-the-code-of-conduct)
- [Open a New Community Extension proposal](#open-a-new-community-extension-proposal)
- [Extension Lifecycle](#extension-lifecycle)
- [Issue triage and labelling](#issue-triage-and-labelling)
- [Maintainer expectations](#maintainer-expectations)
- [Reviewer expectations](#reviewer-expectations)
- [Identifying a project maintainer](#identifying-a-project-maintainer)
- [What to include in your extension's README file](#what-to-include-in-your-extensions-readme-file)
- [Optional information to include in your README file](#optional-information-to-include-in-your-readme-file)
- [Maven artifacts](#maven-artifacts)
- [Root package name](#root-package-name)
- [Parent POM](#parent-pom)
- [Non-code Camunda community extension contributions](#non-code-camunda-community-extension-contributions)
- [Event-Based community roles](#event-based-community-roles)
- [Community education and onboarding](#community-education-and-onboarding)
- [Communication guidelines and expectations](#communication-guidelines-and-expectations)
- [Troubleshooting](#troubleshooting)
- [Community extension peer support](#community-extension-peer-support)
- [Inspiration](#inspiration)

### What is the Camunda Community Hub?

The Camunda Community Hub is a GitHub Organization for all of our community contributed extensions. Extensions in the Camunda Community Hub organization are independently led and maintained projects by members of the broader Camunda open source community, some of whom happen to be Camunda employees, or are projects/tutorials that are created and maintained by the Camunda Developer Relations team!

We’ve put together some commonly asked questions and answers as to the benefits of joining the Camunda Community Hub, our approach to open source contributions and Maintainership moving forward, and how we hope to empower our open source community in the future. 

If you have a question related to getting started contributing to the Camunda open source ecosystem, or need to reach out to the Camunda team, the Directly Responsible Individual for the Camunda Community Hub and your first point of contact should be Camunda Technical Community Builder [Rin Oliver](https://github.com/celanthe), who is available via email: community@camunda.com.

### Why migrate to the hub?

The Camunda Community Hub aims to make the process of contributing to, maintaining, and using Camunda Community Extensions more efficient. This reduces a number of issues regarding the continued maintenance and infrastructure related to community extensions, creating a better experience for users as well as maintainers.

Here are some advantages to your extension being listed under the Camunda Community Hub:

* Automated publishing of your Camunda extension's Maven releases to Maven Central, with more automation on the way for different programming languages
* Automated testing
* Automated issue and pull request labelling 
* Improved issue triage process 
* Improved visibility as to where an extension is in its lifecycle
* Consistent formatting of new issues and releases with new templates and tooling
* Visibility of your project for new contributors interested in getting involved with open source software

The Camunda Community Hub aims to help extension maintainers coordinate, cross-test, and ensure that extensions hosted under the Hub can be used without causing conflict with other applications. It is important to note that community extensions are maintained by the community, and are not maintained or officially supported by Camunda. 

For questions/support relating to the commercial Camunda Cloud and Camunda Platform offerings, please [contact us](https://camunda.com/contact/).

### Getting started

#### Working with an existing Camunda community extension repository

In order to work within the Camunda Community Hub, Maintainers are asked to transfer their repository into the Camunda Community Hub, rather than fork it into the Hub.

You can find the instructions for transferring a repository **owned by your organization** [here](https://docs.github.com/en/github/administering-a-repository/transferring-a-repository#transferring-a-repository-owned-by-your-organization)

If you are transferring a repository owned by your **user account**, please review the existing [documentation on GitHub.](https://docs.github.com/en/github/administering-a-repository/transferring-a-repository#transferring-a-repository-owned-by-your-user-account)

### Creating a new Camunda community extension

If you are interested in building a new Camunda Community Hub extension and have not done so previously, please follow these instructions.

#### Set and confirm your email address in Git

The first step to creating a community extension is to ensure that your Git configuration email address is confirmed and matches your email address listed on GitHub.

If you haven't [set your commit email address in Git](https://docs.github.com/en/github/setting-up-and-managing-your-github-user-account/setting-your-commit-email-address), you can find the full instructions for doing so by clicking the link above.

Here are the steps to take in order to set your Git commit address from the command line for every repository on your computer:

1. Open the Terminal.
2. Set an email address in Git. You can use your GitHub-provided no-reply email address or any email address. On the command line, enter:

`$ git config --global user.email "email@example.com"`

4. Confirm that you have set the email address correctly in Git:

```
$ git config --global user.email
email@example.com
```

Add the associated email address to your account on GitHub, so that your commits are attributed to you and appear in your contributions graph. If you'd like to set your email address for working within this individual repository, you can do so by following these steps:

1. Open a new Terminal window, and navigate to your current working directory in the repository you'd like to update the email address for:

`$ git config user.email "email@example.com"`

2. Confirm that you've set the email address correctly in Git:

```
$ git config user.email
email@example.com
```

3. To verify the change has taken effect, enter the following in your Terminal:

`$ git config --list`

For more information on how to set your email address in GitHub, you can read the [GitHub documentation](https://docs.github.com/en/github/setting-up-and-managing-your-github-user-account/setting-your-commit-email-address) which goes into much more detail on the subject. 

#### Sign the CLA and agree to the Code of Conduct

Once you’ve decided to move forward with creating your community extension, the next step is to sign our [CLA](https://cla-assistant.io/camunda/) and agree to abide by our [Code of Conduct](https://camunda.com/events/code-conduct/).

Next, you can browse the hub to see if there is an extension that already matches your idea. Alternatively, you can join the Camunda Cloud, Camunda Platform, and BPMN forums and post your idea in the Community Extensions thread. 

#### Open a New Community Extension proposal

Then, you’ll open a new issue in the Camunda Community Hub [issue tracker](https://github.com/Camunda-Community-Hub/community/issues/new/choose). Select ‘New Community Extension Proposal,’ from the available template options and follow the instructions listed there. 

#### Extension lifecycle

Once your extension proposal issue has been opened, use your best judegement after reviewing our [community extension lifecycle documentation](https://github.com/Camunda-Community-Hub/community/blob/main/extension-lifecycle.md) to identify where in the development process your extension is currently. You can select the applicable label from [this list](https://github.com/Camunda-Community-Hub/community/blob/main/issue-triage.md).

Note that if your extension is brand new, the label to apply to it should always be proof-of-concept. 

### Issue triage and labelling

For further information on Issue Triage & Labelling in the Camunda Community Hub, please read our [Issue Triage and Labelling documentation](https://github.com/Camunda-Community-Hub/community/blob/main/issue-triage.md).

### Maintainer expectations

Maintainers are often the first point of contact that new contributors have with an open source project, and significantly impact the way that the community is perceived. As such, Community Extension Maintainers are a crucial part of the Camunda open source community, and in shaping the Camunda Community Extension Hub. 

Both extension maintainers and reviewers should remember to abide by the Camunda Code of Conduct when communicating with community members. They should also strive to exceed expectations, exemplifying kindness, respectfulness, and collaboration.

- Maintainers and reviewers are encouraged to review open pull requests on a cadence basis, determined by the project maintainer if a project is in the Proof-of-Concept or Incubation [extension lifecycle stage](https://github.com/Camunda-Community-Hub/community/blob/main/extension-lifecycle.md). 

If an extension maintainer wishes for an extension to be listed as a Stable Community Extension, they must agree to the following standards for pull request review and issue triage:

- Maintainers of a Stable Camunda Community Extension are expected to review open pull requests and issues in their extension's repository within 30 days
- Follow the [guidelines](https://github.com/Camunda-Community-Hub/community/blob/main/issue-triage.md) for open issue and pull request triage

### Reviewer expectations

Reviewers can be anyone who is interested in contributing to an extension. They are primairily responsible for reviewing open pull requests (PRs) in a project, are expected to leave helpful feedback where necessary, assign issue triage labels, ask clarifying questions, and to understand the inner workings of the extension whose pull requests they are reviewing. They are encouraged to review any open PRs on a regular basis, which is often determined by the extension's maintainer. 

Reviewers can also review open pull requests at any time that works for them outside of any set official issue triage time set by the extension's maintainer. If a maintainer wishes for an extension to be labelled as a Stable Community Extension, they must agree to the following standards for pull request review and issue triage:

* Reviewers contributing to a Stable Camunda Community Extension are expected to review open pull requests assigned to them in a timely manner
    * If a reviewer fails to respond, a PR may be reassigned to another reviewer after three attempts to contact the reviewer
    * If you are a Camunda Community Extension reviewer, and you are going to be away for an extended period, or no longer have time to dedicate to issue review, please notify the project Maintainer, and remove yourself from any existing documentation that lists you as an active reviewer
    * Reviewers and Maintainers are expected to adhere to our guidelines surrounding [issue triage and labelling](https://github.com/Camunda-Community-Hub/community/blob/main/issue-triage.md) for Stable Community Extensions

#### Identifying a project maintainer

Each Camunda community extension will have listed a Maintainer whose responsibility it is to maintain the extension and drive its progression forward. 

### What to include in your extension's README file

* Lifecycle labels -- Please review the [Camunda Community Hub extension lifecycle](https://github.com/Camunda-Community-Hub/community/blob/main/extension-lifecycle.md) and add a [Shields.io badge](https://shields.io/) to your extension's README that indicates which area of the lifecycle it falls under.
    * Note: If you no longer wish to maintain your extension, please follow the instructions for opening a pull request using the template provided, and apply the Lifecycle - Maintainer Wanted Shield badge and Probot labels to your extension’s repository, issues, and open PRs.
* We highly suggest that all Camunda community extensions follow our established Style Guide when writing documentation
* A name that clearly identifies your project
    *  Implement the [Camunda community extension badge](https://img.shields.io/badge/Community%20Extension-An%20open%20source%20community%20maintained%20project-FF4700) if you so choose (this is optional)
* Installation -- If your project has certain dependencies that need to be installed, it is best practice to detail these in your README file
* Using your extension -- Give examples of how one might use your extension. Example use cases are helpful, even if they are smaller in scope. For larger project implementation examples, provide links to these rather than having them in your README file.
* Troubleshooting -- Clearly state the DRI (Directly Responsible Individual) that users of your extension can contact with questions, or if they run into a problem. In most cases this is the extension’s Maintainer, but in some cases it may not be. 
* While we encourage you to create a general discussion thread on our forums about your extension, please direct users that are having trouble working with your extension for any reason to open an issue on GitHub
* Contributing -- If your extension is open to outside contributions from the community, here’s where you should state that, and what your requirements are for accepting/merging a pull request. 
* Document any commands needed to run CI/CD tests, and be sure to include instructions for running tests. 
* Licensing information -- Please list the open source licenses your project is under here. For example, Apache 2.0.

#### Optional information to include in your README file

* Badges -- These are created using Shields.io, and give community members a visual representation of your extension’s build status, lifecycle, release version, and other useful metadata
* Visuals -- If your project relies on screenshots, please ensure that you also add alt text to screenshots to ensure accessibility for those using screen readers or that have visual disabilities
* Keep best practices in mind when using screenshots. Remember to obscure any API keys, secrets, or identifiers that could be exploited maliciously
* Authors, maintainers, and other acknowledgements -- If you would like to include this section, it is a nice way to show appreciation for the individuals who contributed to your project
* Roadmap -- GitHub [project boards](https://docs.github.com/en/github/managing-your-work-on-github/about-project-boards) are a great way to showcase your roadmap for your extension. If you have one set up, it’s a good idea to link to it in your README.
* Make the steps to get started with your extension clear to understand for those that may not have a similar background to yourself

### Maven artifacts

Community extensions should follow these naming conventions for Maven Artifacts:

* groupID
* artifactID

### Root package name

The root package name should be the same as the extension's Maven Artifact groupID.

### Parent POM

All community extensions using Maven are expected to use [TBD] as the parent POM. This POM contains project release and artifact publishing configurations.

### Non-Code Camunda community extension contributions

If you are interested in contributing to any Camunda Community Hub extension, there are a variety of ways to get involved without having to have coding experience: These include issue triage, writing documentation, and much, much more.

If you are interested in getting started contributing by doing any of these tasks, please complete the following steps:

1. Reach out to Camunda Technical Community Builder Rin Oliver by emailing community@camunda.com
2. Open a new issue in the Camunda Community Hub repository you'd like to contribute to and detail the non-code contributions that you would like to make.
3. If you see a 'Good First Issue' relating to non-code contributions (documentation, issues or pull requests that need triaging, process management, etc.) and you'd like to claim it, you are encouraged to /assign it to yourself 
4. Tag @celanthe in the comments on the issue

Some examples of how you can contribute to the Camunda Community Hub and the broader Camunda open source ecosystem are as follows:

#### Event-Based community roles

* Host or organize a Camunda Community Meetup
* Present your work with Camunda at Meetups
* Start a new Camunda event near you
* Community Education and Onboarding

#### Community education and onboarding

* Help new contributors get started working with the Hub, finding a repository to contribute to, forking a repo, and making their first pull request
* Getting people involved in writing documentation and issue triage
* Spreading the word about the Camunda Community Hub to the broader open source community 
* Answering questions on Slack, Discourse, GitHub Project boards, and the Camunda Cloud community forums

#### Create community content

* Write a blog post about your experience with Camunda, how you built a Community Hub Extension, etc.
* Be a guest on our Camunda Nation podcast
* Write walkthroughs, how-to guides, and more

#### Issue triage

* Labelling issues in Camunda Community Extension repositories
* Helping to triage issues by following up where needed, closing stale issues, and more

For more information on how to get started with issue triage and labelling, including what issue labels and pull request automation we use in the Camunda Community Hub, please [read the documentation](https://github.com/Camunda-Community-Hub/community/blob/main/issue-triage.md)

#### Post-Code specific contributions

These are roles that are not code-based, but require some knowledge in that you will need to have an understanding of the Camunda Community Extension ecosystem, the Camunda codebase, or general programming knowledge.

* Help project Maintainers write release notes for their extension
* GitHub management (tags, repositories, etc.)
* Mentoring new contributors and ensuring they have the tools they need to succeed when contributing to a Camunda Community Hub open source project
* Writing new or editing existing documentation
* Updating communication guidelines and expectations

### Communication guidelines and expectations

As is the nature of open source software, maintainers and extension creators often wear many hats. These range from administrative, to QA, and much more. As extensions in the Camunda Community Hub are community led, it is crucial that users of extensions understand that maintainers are often working on community extensions in their free time. Please remember to be kind, and follow the [Camunda Community Code of Conduct](https://camunda.com/events/code-conduct/) when interacting with project maintainers.

Keep in mind that communication styles vary, and no two individuals communicate in the same way. Please do your best to remain helpful, and try to avoid making sweeping demands or generalizations whenever possible. It is expected that Maintainers will follow the Camunda Code of Conduct when interacting with community members, and the same holds true for community members interacting with extension maintainers.

**Not ideal:** “This feature doesn’t work, please fix it!” 

**Preferred:** “This feature doesn’t work as expected when I [do XYZ], do you have any suggestions as to how I can fix it? Thank you so much!”

When closing a pull request as a community extension maintainer, please keep in mind the following examples of helpful communication:

**Not ideal** “This is not following the current pull request conventions! I’m closing this issue.”

**Preferred:** “I am closing this PR because this extension can’t support [use case]. In its current form, it would be improved by/better contributed to [XYZ]. Thank you so much for your work on this!”

### Troubleshooting

If you are struggling, the best thing to do is to reach out to the Camunda community. If you can’t find your answer in this guide, or by searching the Camunda Community Forums, then please feel free to start a troubleshooting conversation on the Camunda Forum your extension relates to in the '[Camunda Community Extensions](https://forum.camunda.org/c/community-extensions/13),' category.

### Community extension peer support

If you’re encountering a problem, remember that the community is here to help! Please feel free to start a post on the Camunda Cloud Discourse forums, or the Camunda Community Hub GitHub project board.

If you are struggling with creating a Camunda community extension, please open a Pull Request using the provided template.

We highly encourage you to post on the Camunda community forums about your extension, its wider impact for the open source community, and what made you decide to build a community extension.

### Meet the Camunda Developer Relations team

The [Camunda Developer Relations team](https://github.com/Camunda-Community-Hub/devrel-team) exists to serve the Camunda developer community, from internal employees to Open Source contributors, Enterprise customers, and the broader tech community.

It is our goal to provide opportunities for developers to be more successful by making them aware of our solutions, enabling them to be successful through great experiences, and fostering a culture of collaboration.

### Inspiration

This documentation was inspired by the following resources:

* [Kubernetes Contributors](https://www.kubernetes.dev/)
* [Quarkiverse](https://quarkus.io/blog/quarkiverse/)
* [KNIME](https://docs.knime.com)
* [CiviCRM](https://docs.civicrm.org/)
