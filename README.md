# Welcome to the Camunda Community Hub!
## A project to empower our open source community extension maintainers, and encourage new contributors to get started contributing to the Camunda open source ecosystem. 

**Table of Contents**

- [What is the Camunda Community Hub](#what-is-the-camunda-community-hub)
- [Why migrate to the hub](#why-migrate-to-the-hub)
- [Getting started](#getting-started)
- [Issue triage and labelling](#issue-triage-and-labelling)
- [Maintainer expectations](#maintainer-expectations)
- [Reviewer expectations](#reviewer-expectations)
- [Identifying a project maintainer](#identifying-a-project-maintainer)
- [Automated Releases](#automated-releases)
- [Unified GroupID](#group-id)
- [What to include in your extension's README file](#what-to-include-in-your-extensions-readme-file)
- [Optional information to include in your README file](#optional-information-to-include-in-your-readme-file)
- [Communication guidelines and expectations](#communication-guidelines-and-expectations)
- [Troubleshooting](#troubleshooting)
- [Community extension peer support](#community-extension-peer-support)
- [Inspiration](#inspiration)

### What is the Camunda Community Hub?

The [Camunda Community Hub](https://camunda.com/blog/2021/03/introducing-the-camunda-community-hub/) is a GitHub Organization for all of our community contributed extensions. Extensions in the Camunda Community Hub organization are independently led and maintained projects by members of the broader Camunda open source community, some of whom happen to be Camunda employees, or are projects/tutorials that are created and maintained by the Camunda Developer Relations team!

We’ve put together some commonly asked questions and answers as to the benefits of joining the Camunda Community Hub, our approach to open source contributions and Maintainership moving forward, and how we hope to empower our open source community in the future. 

If you have a question related to getting started contributing to the Camunda open source ecosystem, or need to reach out to the Camunda team, the Directly Responsible Individual for the Camunda Community Hub and your first point of contact should be Camunda Technical Community Builder [Rin Oliver](https://github.com/celanthe), who is available via email: community@camunda.com.

### Why migrate to the hub?

The Camunda Community Hub aims to make the process of contributing to, maintaining, and using Camunda Community Extensions more efficient. This reduces a number of issues regarding the continued maintenance and infrastructure related to community extensions, creating a better experience for users as well as maintainers. Here are some advantages to your extension being listed under the Camunda Community Hub:

* Automated publishing of your Camunda extension's Maven releases to Maven Central, with more automation on the way for different programming languages
* Automated releases
* Automated issue and pull request labelling 
* Improved issue triage process 
* Improved visibility as to where an extension is in its lifecycle
* Consistent formatting of new issues and releases with new templates and tooling
* Visibility of your project for new contributors interested in getting involved with open source software

The Camunda Community Hub aims to help extension maintainers coordinate, cross-test, and ensure that extensions hosted under the Hub can be used without causing conflict with other applications. It is important to note that community extensions are maintained by the community, and are not maintained or officially supported by Camunda. For questions/support relating to the commercial Camunda Cloud and Camunda Platform offerings, please [contact us](https://camunda.com/contact/).

### Getting started

The first step to take is to [open an issue](https://github.com/camunda-community-hub/community/issues) in this repository and ask to be invited to join the Camunda Community Hub if you are not already a collaborator there.

Note: In order to work within the Camunda Community Hub, Maintainers are asked to transfer their repository into the Camunda Community Hub, rather than fork it into the Hub. When you migrate your extension into the Camunda Community Hub, we will receive your contact information and may occasionally reach out to you with questions, information, etc. You *will not* be added to any marketing lists, but you may be contacted by us or Camunda Community Hub open source contributors.

#### Transferring an existing Camunda community extension repository in a Camunda organization

Next, you will need to open an issue in your repository titled 'Transfer (your repository) into the Camunda Community Hub' and assign it to @celanthe, or tag them in a comment on the issue itself if you are unable to assign the issue to them. From there, they will then start the process of getting the repository transferred into the Hub. 

Once the repository has transferred, you can proceed to [the next step](https://github.com/camunda-community-hub/community/blob/main/README.md#what-to-include-in-your-extensions-readme-file) and follow the instructions there.

#### Transferring a repository in your personal GitHub Account

You will need to follow these instructions for transferring a repository in your own personal GitHub user account into the Camunda Community Hub: https://docs.github.com/en/github/administering-a-repository/transferring-a-repository#transferring-a-repository-owned-by-your-user-account

#### Transferring a repository in your company's organization

To transfer a repository in your company's GitHub organization into the Camunda Community Hub, please review the process documented at: https://docs.github.com/en/github/administering-a-repository/transferring-a-repository#transferring-a-repository-owned-by-your-organization

### Creating a new Camunda community extension

The first step to creating a new Camunda community extension is to ensure that your Git configuration email address is confirmed and matches your email address listed on GitHub. If you are interested in building a new Camunda Community Hub extension and have not done so previously, please follow these instructions. 

* [Set and confirm your commit email address](https://docs.github.com/en/github/setting-up-and-managing-your-github-user-account/setting-your-commit-email-address) in Git. For more information on how to set your email address in GitHub, you can read the [GitHub documentation](https://docs.github.com/en/github/setting-up-and-managing-your-github-user-account/setting-your-commit-email-address) which goes into much more detail on the subject. 
* Sign the CLA and agree to the Code of Conduct
* * Once you’ve decided to move forward with creating your community extension, the next step is to sign our [CLA](https://cla-assistant.io/camunda-community-hub/community) and agree to abide by our [Code of Conduct](https://camunda.com/events/code-conduct/). Next, you can browse the hub to see if there is an extension that already matches your idea. Alternatively, you can join the Camunda Cloud, Camunda Platform, and BPMN forums and post your idea in the Community Extensions thread. 
* Create a new repository. Title the repository with the name of your proposed extension.
* Open a New Community Extension proposal
* * To open a new Community Extension Proposal in the Camunda Community Hub, you can do so by viewing the [issue tracker](https://github.com/Camunda-Community-Hub/community/issues/new/choose). Next, select ‘New Community Extension Proposal,’ from the available template options. After completing the template, open the issue and give it a meaningful title.
* Evaluate your extension's lifecycle status
* * Once your extension proposal issue has been opened, use your best judgement after reviewing our [community extension lifecycle documentation](https://github.com/Camunda-Community-Hub/community/blob/main/extension-lifecycle.md) to identify where in the development process your extension is currently and add it to your extension's README along with a community extension lifecycle label. 

*Note that if your extension is new and/or untested, the label to apply to it should always be 'proof-of-concept.' 

### Issue triage and labelling

For further information on Issue Triage & Labelling in the Camunda Community Hub, please read our [Issue Triage and Labelling documentation](https://github.com/Camunda-Community-Hub/community/blob/main/issue-triage.md).

### Maintainer expectations

Maintainers are often the first point of contact that new contributors have with an open source project, and significantly impact the way that the community is perceived. As such, Community Extension Maintainers are a crucial part of the Camunda open source community, and in shaping the Camunda Community Extension Hub. Both extension maintainers and reviewers should remember to abide by the Camunda Code of Conduct when communicating with community members. They should also strive to exceed expectations, exemplifying kindness, respectfulness, and collaboration.

- Maintainers and reviewers are encouraged to review open pull requests on a cadence basis, determined by the project maintainer if a project is in the Proof-of-Concept or Incubation [extension lifecycle stage](https://github.com/Camunda-Community-Hub/community/blob/main/extension-lifecycle.md). 

If an extension maintainer wishes for an extension to be listed as a Stable Community Extension, they must agree to the following standards for pull request review and issue triage:

- Maintainers of a Stable Camunda Community Extension are expected to review open pull requests and issues in their extension's repository within 30 days
- Follow the [guidelines](https://github.com/Camunda-Community-Hub/community/blob/main/issue-triage.md) for open issue and pull request triage

If you are a contributor that would like to take over maintaining an extension in the Camunda Community hub that has the Lifecycle: Abandoned or 'Maintainer Wanted' labels, please review [becoming a Maintainer of an abandoned extension](https://github.com/camunda-community-hub/community/blob/main/abandoned-extension-maintainer-guidelines.MD)

#### Identifying a project maintainer

Each Camunda community extension will have listed a Maintainer whose responsibility it is to maintain the extension and drive its progression forward. 

### Reviewer expectations

Reviewers can be anyone who is interested in contributing to an extension. They are primarily responsible for reviewing open pull requests (PRs) in a project, are expected to leave helpful feedback where necessary, assign issue triage labels, ask clarifying questions, and to understand the inner workings of the extension whose pull requests they are reviewing. They are encouraged to review any open PRs on a regular basis, which is often determined by the extension's maintainer. 

Reviewers can also review open pull requests at any time that works for them outside of any set official issue triage time set by the extension's maintainer. If a maintainer wishes for an extension to be labelled as a Stable Community Extension, they must agree to the following standards for pull request review and issue triage:

* Reviewers contributing to a Stable Camunda Community Extension are expected to review open pull requests assigned to them in a timely manner
    * If a reviewer fails to respond, a PR may be reassigned to another reviewer after three attempts to contact the reviewer
    * If you are a Camunda Community Extension reviewer, and you are going to be away for an extended period, or no longer have time to dedicate to issue review, please notify the project Maintainer, and remove yourself from any existing documentation that lists you as an active reviewer
    * Reviewers and Maintainers are expected to adhere to our guidelines surrounding [issue triage and labelling](https://github.com/Camunda-Community-Hub/community/blob/main/issue-triage.md) for Stable Community Extensions.

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

### Automated releases

For more information on automated releases and how you can utilize automated releasing to Maven Central in the Camunda Community Hub, please view our [automated release](https://github.com/camunda-community-hub/community/blob/main/RELEASE.MD) documentation.

### Group ID 

The Camunda Community Hub members have decided to operate under a centralized GroupID as of January 15th, 2021:

```
org.camunda.community
```

To make use of this centralized GroupID in your own projects, including how to relocate your extension's GroupID, please review our [documentation](https://github.com/camunda-community-hub/community/blob/main/RELOCATE_GROUPID.md)

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

If you’re encountering a problem, remember that the community is here to help! Please feel free to start a post on the Camunda Cloud Discourse forums, or the Camunda Community Hub GitHub project board. If you are struggling with creating a Camunda community extension, please open a Pull Request using the provided template. We highly encourage you to post on the Camunda community forums about your extension, its wider impact for the open source community, and what made you decide to build a community extension. These are as follows:

* [Camunda Platform](https://forum.camunda.org/)
* [Camunda Cloud](https://forum.camunda.io/)
* [BPMN.io](https://forum.bpmn.io/)

### Meet the Camunda Developer Relations team

The [Camunda Developer Relations team](https://github.com/Camunda-Community-Hub/devrel-team) exists to serve the Camunda developer community, from internal employees to Open Source contributors, Enterprise customers, and the broader tech community. It is our goal to provide opportunities for developers to be more successful by making them aware of our solutions, enabling them to be successful through great experiences, and fostering a culture of collaboration.

### Inspiration

This documentation was inspired by the following resources:

* [Kubernetes Contributors](https://www.kubernetes.dev/)
* [Quarkiverse](https://quarkus.io/blog/quarkiverse/)
* [KNIME](https://docs.knime.com)
* [CiviCRM](https://docs.civicrm.org/)
