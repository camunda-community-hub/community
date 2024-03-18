# Maintainer and reviewer expectations

- [What is a maintainer?](#what-is-a-maintainer)
- [Becoming a maintainer](#becoming-a-maintainer)
- [Maintainer expectations](#maintainer-expectations)
  - [Maintainer expectations checklist](#maintainer-expectations-checklist)
  - [Active maintainers](#active-maintainers)
- [Maintainer inactivity and offboarding](#maintainer-inactivity-and-offboarding)
- [Important links](#important-links)
- [Extension lifecycle stages](#extension-lifecycle-stages)
  - [Proof-of-Concept](#proof-of-concept)
  - [Incubating](#incubating)
  - [Stable](#stable)
  - [Deprecated](#deprecated)
  - [Unmaintained](#unmaintained)
- [What to include in your extension's README](#what-to-include-in-your-extensions-readme)
  - [Optional information to include in your README](#optional-information-to-include-in-your-readme)
- [Reviewer expectations](#reviewer-expectations)
  - [Reviewer expectations checklist](#reviewer-expectations-checklist)

## What is a maintainer?
In open source software, a maintainer is the project leader. They are the one setting the direction and processes for a project.

Each Camunda community extension will have a maintainer listed whose responsibility it is to maintain the extension and drive its progression forward. Otherwise, it will be labeled as `Unmaintained`.

However you maintain your extension, we at Camunda want to empower and enable our community hub extension maintainers to do what they do best, see projects through to completion. 

Whether it’s dusting off an abandoned extension, stepping up to help an overburdened maintainer of a busy project, or even creating and maintaining something new -- we're here to help you!  

## Becoming a maintainer
* [Creating a new extension](
maintainers-reviewers/creating-new-extensions.md) in the Community Hub
* [Transferring an existing extension](maintainers-reviewers/transferring-extensions.md) to the Community Hub
* If you are interested in stepping up to maintain a previously unmaintained extension, please [open a new issue using the Extension Maintainer Proposal template](https://github.com/camunda-community-hub/community/issues/new/choose).
* [Maintainer best practices](maintainers-reviewers/maintainer-best-practices.md)

## Maintainer expectations

### Maintainer expectations checklist
All maintainers must:
- [ ] Follow [Code of Conduct](/docs/CODE_OF_CONDUCT.MD) and the [Camunda Community Values](https://camunda.com/developers/community-values/)
- [ ] Determine [extension lifecycle stage](#extension-lifecycle-stages)
- [ ] Review pull requests regularly according to lifecycle stage
- [ ] Ensure README contains the correct badges and information as detailed in [this section](#what-to-include-in-your-extensions-readme)


### Active maintainers

In the Camunda Community Hub, we define an active maintainer as someone who:
 - [ ] Responds to issues and pull requests in their project(s) within 30 days
- [ ] Follow additional requirements based on their extension's [lifecycle stage, as outlined below](#extension-lifecycle-stages)
   
Active maintainers are invited to join our private community Slack for centralized communication. If you have not received an invite, please reach out to ` @camunda-community-hub/devrel` in [an issue](https://github.com/camunda-community-hub/community/issues/new/choose).

## Maintainer inactivity and offboarding

Open source maintainers are often working on their projects in their spare time, and we understand that life happens and you might not always be able to be involved at the same level. 

If the workload is becoming too much, consider bringing on a co-maintainer.

If your extension is currently labeled as `Stable` and you can't keep up with it, consider moving to another lifecycle label to keep expectations around updates and responses clear.

If you know you will not have bandwidth to maintain your project, either temporarily or long-term, please reach out to a Camunda team member (`@camunda-community-hub/devrel`) with[ an issue](https://github.com/camunda-community-hub/community/issues/new/choose). If you have an expected time that you can return, let us know, otherwise we will list the extension as [`unmaintained/needs maintainer`](#unmaintained).

If a maintainer becomes inactive without contact, the Camunda team will reach out to check in. If there is 30 days of continued inactivity after this outreach, the Camunda team may take steps to revive the extension, including changing the lifecycle label, adding another maintainer, or removing the extension from the Camunda Community Hub.

## Important links
 * [RELEASE.md](maintainers-reviewers/RELEASE.MD) - how to release your extension via Maven or Docker

---
## Extension lifecycle stages

Each part of the extension lifecycle has different requirements for reviewing and responding to isseus and pull requests.

### Proof-of-Concept
* `Proof-of-Concept` extensions are just that, ideas that community members would like to explore further. 
* They offer little support, nor do they promise any stability. 
* This label is most often applied to extensions that are used to validate a Proof-of-Concept for working with Camunda 7 or Camunda 8, or for those interested in finding collaborators on a particular project that has the potential to grow into a `Stable` extension.

### Incubating
* Extensions with the `Incubating` label provide some degree of stability which is defined and adhered to by the project’s maintainer, community support, and are actively maintained and updated. 
* Documentation gaps, roadblocks, bugs, and other issues are to be expected. 
* There is currently no set time limit for an extension to move out of incubation status.

### Stable
If an extension maintainer wishes for an extension to be listed as a `Stable` community extension, they must agree to the following standards for pull request review and issue triage:
* An extension with the `Stable` label has an active, thriving community surrounding it. It releases updates on a regular basis, has active maintainers and community participants, and may be actively used at an organizational level.
* A Stable extension has at least one active maintainer.
* Stable extensions must be kept current and maintained between [Camunda main releases.](https://camunda.com/release-policy/)
* Maintainers of a stable Camunda community extension are expected to review open pull requests and issues in their extension's repository **within 30 days.**
* Maintainers of stable extensions are actively in contact with the Camunda team, or may have one or more Camunda team members actively contributing to the extension.
* Stable extension maintainers and reviewers are expected to adhere to [our expectations](https://github.com/camunda-community-hub/community#maintainer-expectations) surrounding PR reviews and communication.
* Stable Community Extensions have agreed to follow the Camunda Community Extension [issue triage and pull request review process](https://github.com/camunda-community-hub/community/blob/main/issue-triage.md).
* Your extension must contain and abide by the [Camunda Community Hub Code of Conduct](/docs/CODE_OF_CONDUCT.MD).
* Your extension must have a [contributor guide](https://github.com/camunda-community-hub/community/blob/main/CONTRIBUTING.MD).
* Having a stable community extension means that much of the heavy lifting of building/maintenance surrounding releases is done for you with the ability to implement GitHub actions to automatically publish your extension to [Maven Central](/maintainers-reviewers/RELEASE.MD) if applicable to your extension. Initially, by utilizing the above GitHub Workflow, maintainers of Java-based extensions can implement to automate the publishing of new artifacts to Maven Central. 

### Deprecated
* An extension with the `Deprecated` label is no longer being maintained. It may have been deprecated due to an official feature or other solution. Be sure to review the README and see if there is an alternative presented.

### Unmaintained
* Extensions are considered `Unmaintained` when the project’s owner is no longer updating the extension, has not responded to open issues or pull requests within 30 days, and/or has notified a Camunda team member that they are no longer actively maintaining the extension.

If you no longer wish to maintain your extension, please apply the `Maintainer Needed` badge and `Unmaintained` labels to your extension’s repository, issues, and open PRs.

> To report an extension as unmaintained, please [open a new issue using the Report Unmaintained Repo template](https://github.com/camunda-community-hub/community/issues/new/choose) template.
>
> 
> If you are interested in stepping up to maintain a previously unmaintained extension, please [open a new issue using the Extension Maintainer Proposal template](https://github.com/camunda-community-hub/community/issues/new/choose).


---

## What to include in your extension's README

- [ ] **Lifecycle labels**: Please review the [Camunda Community Hub extension lifecycle](https://github.com/Camunda-Community-Hub/community/blob/main/extension-lifecycle.md) and add a badge to your extension's README that indicates which area of the lifecycle it falls under.
- [ ]  Implement the **[Camunda community extension badge](https://img.shields.io/badge/Community%20Extension-An%20open%20source%20community%20maintained%20project-FF4700)**.
- [ ] Include a **[compataibility badge](https://github.com/Camunda-Community-Hub/community/blob/main/extension-lifecycle.md)** to clarify which Camunda product(s) your extension is compatible with. 
- [ ] A name that clearly identifies your project.
- [ ] **Installation**: If your project has certain dependencies that need to be installed, it is best practice to detail these in your README file.
- [ ] **Using your extension**: Give examples of how one might use your extension. Example use cases are helpful, even if they are smaller in scope. For larger project implementation examples, provide links to these rather than having them in your README file.
- [ ] **Troubleshooting**: Clearly state the maintainer(s) of your extension and how users can contact them with questions, or if they run into a problem. 
- [ ] **Contributing**: If your extension is open to outside contributions from the community, here’s where you should state that, and what your requirements are for accepting/merging a pull request. 
- [ ] Document any commands needed to run CI/CD tests, and be sure to include instructions for running tests. 
- [ ] **Licensing information**: Please list the open source licenses your project is under here, for example, Apache 2.0.

### Optional information to include in your README

- [ ] **[Additional badges](https://github.com/Camunda-Community-Hub/community/blob/main/extension-lifecycle.md)**: These give community members a visual representation of your extension’s build status, lifecycle, release version, and other useful metadata.
- [ ] Follow our established [Style Guide](https://camunda.com/brand/writing-style-guide/) when writing documentation.
- [ ] **Visuals**: If your project relies on screenshots, please ensure that you also add alt text to screenshots to ensure accessibility for those using screen readers or that have visual disabilities.
- [ ] Keep best practices in mind when using screenshots. Remember to obscure any API keys, secrets, or identifiers that could be exploited maliciously.
- [ ] **Contributors, maintainers, and other acknowledgements:** If you would like to include this section, it is a nice way to show appreciation for the individuals who contributed to your project.
- [ ] **Roadmap**: GitHub [project boards](https://docs.github.com/en/github/managing-your-work-on-github/about-project-boards) are a great way to showcase your roadmap for your extension. If you have one set up, it’s a good idea to link to it in your README.
- [ ] Make the steps to get started with your extension clear to understand for those that may not have a similar background to yourself.
---
## Reviewer expectations
### Reviewer expectations checklist
- [ ] Follow [Code of Conduct](/docs/CODE_OF_CONDUCT.MD)
- [ ] Review PRs assigned in a timely manner

Reviewers can be anyone who is interested in contributing to an extension. They are primarily responsible for reviewing open pull requests (PRs) in a project, are expected to leave helpful feedback where necessary, assign issue triage labels, ask clarifying questions, and to understand the inner workings of the extension whose pull requests they are reviewing. They are encouraged to review any open PRs on a regular basis, which is often determined by the extension's maintainer. 

Reviewers can also review open pull requests at any time that works for them outside of any set official issue triage time set by the extension's maintainer. If a maintainer wishes for an extension to be labeled as a stable community extension, they must agree to the following standards for pull request review and issue triage:

* Reviewers contributing to a `stable` Camunda community extension are expected to review open pull requests assigned to them in a timely manner
    * If a reviewer fails to respond, a PR may be reassigned to another reviewer after three attempts to contact the reviewer.
    * If you are a Camunda community extension reviewer, and you are going to be away for an extended period, or no longer have time to dedicate to issue review, please notify the project maintainer, and remove yourself from any existing documentation that lists you as an active reviewer.
    * Reviewers and maintainers are expected to adhere to our guidelines surrounding [issue triage and labelling](https://github.com/Camunda-Community-Hub/community/blob/main/issue-triage.md) for stable community extensions.

