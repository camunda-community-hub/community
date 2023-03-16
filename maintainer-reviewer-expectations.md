# Maintainer and reviewer expectations

- [Maintainer expectations](#maintainer-expectations)
  - [Maintainer expectations checklist](#maintainer-expectations-checklist)
  - [Extension lifecycle stages](#extension-lifecycle-stages)
    - [Proof-of-Concept](#proof-of-concept)
    - [Incubating](#incubating)
    - [Stable](#stable)
  - [Identifying a project maintainer](#identifying-a-project-maintainer)
- [Reviewer expectations](#reviewer-expectations)
  - [Reviewer expectations checklist](#reviewer-expectations-checklist)
- [What to include in your extension's README](#what-to-include-in-your-extensions-readme)
  - [Optional information to include in your README](#optional-information-to-include-in-your-readme)

## Maintainer expectations

### Maintainer expectations checklist
- [ ] Follow [Code of Conduct](https://github.com/camunda-community-hub/community/blob/8868732b30cabc28b9006a5285e54a53ad13cbc6/CODE_OF_CONDUCT.MD#L1)
- [ ] Determine [extension lifecycle stage](#extension-lifecycle-stages)
- [ ] Review pull requests regularly according to lifecycle stage

Maintainers are often the first point of contact that new contributors have with an open source project, and significantly impact the way that the community is perceived. As such, community extension maintainers are a crucial part of the Camunda open source community, and in shaping the Camunda Community Hub. 

Both extension maintainers and reviewers should remember to abide by the [Camunda Code of Conduct](https://github.com/camunda-community-hub/community/blob/8868732b30cabc28b9006a5285e54a53ad13cbc6/CODE_OF_CONDUCT.MD#L1) when communicating with community members. They should also strive to exceed expectations, exemplifying kindness, respectfulness, and collaboration.

### Extension lifecycle stages

Maintainers and reviewers are encouraged to review open pull requests on a cadence basis, determined by the project maintainer if a project is in the Proof-of-Concept or Incubation [extension lifecycle stage](https://github.com/Camunda-Community-Hub/community/blob/main/extension-lifecycle.md). 

#### Proof-of-Concept
* `Proof-of-Concept` extensions are just that, ideas that community members would like to explore further. 
* They offer little support, nor do they promise any stability. 
* This label is most often applied to extensions that are used to validate a Proof-of-Concept for working with Camunda Platform 7 or Camunda Plaform 8, or for those interested in finding collaborators on a particular project that has the potential to grow into a Stable extension.

#### Incubating
* Extensions with the `Incubating` label provide some degree of stability which is defined and adhered to by the project’s maintainer, community support, and are actively maintained and updated. Documentation gaps, roadblocks, bugs, and other issues are to be expected. There is currently no set time limit for an extension to move out of incubation status.

#### Stable
If an extension maintainer wishes for an extension to be listed as a `Stable` community extension, they must agree to the following standards for pull request review and issue triage:

* An extension with the `Stable` label has an active, thriving community surrounding it. It releases updates on a regular basis, has active maintainers and community participants, and may be actively used at an organizational level.
* Maintainers of a stable Camunda community extension are expected to review open pull requests and issues in their extension's repository within 30 days.
* Maintainers of stable extensions are actively in contact with the Camunda team, or may have one or more Camunda team members actively contributing to the extension.
* Stable extension maintainers and reviewers are expected to adhere to [our expectations](https://github.com/camunda-community-hub/community#maintainer-expectations) surrounding PR reviews, and communication.
* Stable Community Extensions have agreed to follow the Camunda Community Extension [issue triage and pull request review process](https://github.com/camunda-community-hub/community/blob/main/issue-triage.md).
* Your extension must contain and abide by the [Camunda Community Hub Code of Conduct ](https://github.com/camunda-community-hub/community/blob/main/CODE_OF_CONDUCT.MD).
* Your extension must have a [contributor guide ](https://github.com/camunda-community-hub/community/blob/main/CONTRIBUTING.MD).

If you are a contributor that would like to take over maintaining an extension in the Camunda Community Hub that has the Lifecycle: `Abandoned` or `Maintainer Wanted` labels, please review [becoming a Maintainer of an abandoned extension](https://github.com/camunda-community-hub/community/blob/main/abandoned-extension-maintainer-guidelines.MD).

### Identifying a project maintainer

Each Camunda community extension will have listed a maintainer whose responsibility it is to maintain the extension and drive its progression forward. Otherwise, it will be labeled as `Abandoned`.

## Reviewer expectations
### Reviewer expectations checklist
- [ ] Follow [Code of Conduct](https://github.com/camunda-community-hub/community/blob/8868732b30cabc28b9006a5285e54a53ad13cbc6/CODE_OF_CONDUCT.MD#L1)
- [ ] Review PRs assigned in a timely manner

Reviewers can be anyone who is interested in contributing to an extension. They are primarily responsible for reviewing open pull requests (PRs) in a project, are expected to leave helpful feedback where necessary, assign issue triage labels, ask clarifying questions, and to understand the inner workings of the extension whose pull requests they are reviewing. They are encouraged to review any open PRs on a regular basis, which is often determined by the extension's maintainer. 

Reviewers can also review open pull requests at any time that works for them outside of any set official issue triage time set by the extension's maintainer. If a maintainer wishes for an extension to be labeled as a stable community extension, they must agree to the following standards for pull request review and issue triage:

* Reviewers contributing to a stable Camunda community extension are expected to review open pull requests assigned to them in a timely manner
    * If a reviewer fails to respond, a PR may be reassigned to another reviewer after three attempts to contact the reviewer.
    * If you are a Camunda community extension reviewer, and you are going to be away for an extended period, or no longer have time to dedicate to issue review, please notify the project maintainer, and remove yourself from any existing documentation that lists you as an active reviewer.
    * Reviewers and maintainers are expected to adhere to our guidelines surrounding [issue triage and labelling](https://github.com/Camunda-Community-Hub/community/blob/main/issue-triage.md) for stable community extensions.


## What to include in your extension's README

- [ ] **Lifecycle labels**: Please review the [Camunda Community Hub extension lifecycle](https://github.com/Camunda-Community-Hub/community/blob/main/extension-lifecycle.md) and add a badge to your extension's README that indicates which area of the lifecycle it falls under.
- [ ]  Implement the [Camunda community extension badge](https://img.shields.io/badge/Community%20Extension-An%20open%20source%20community%20maintained%20project-FF4700) (optional).
- [ ] Include a [compataibility badge](https://github.com/Camunda-Community-Hub/community/blob/main/extension-lifecycle.md) to clarify which Camunda product(s) your extension is compatible with. 
- [ ] Follow our established [Style Guide](https://camunda.com/brand/writing-style-guide/) when writing documentation (optional)).
- [ ] A name that clearly identifies your project.
- [ ] **Installation**: If your project has certain dependencies that need to be installed, it is best practice to detail these in your README file
- [ ] **Using your extension**: Give examples of how one might use your extension. Example use cases are helpful, even if they are smaller in scope. For larger project implementation examples, provide links to these rather than having them in your README file.
- [ ] **Troubleshooting**: Clearly state the maintainer that users of your extension can contact with questions, or if they run into a problem. In most cases this is the extension’s Maintainer, but in some cases it may not be. 
- [ ] **Contributing**: If your extension is open to outside contributions from the community, here’s where you should state that, and what your requirements are for accepting/merging a pull request. 
- [ ] Document any commands needed to run CI/CD tests, and be sure to include instructions for running tests. 
- [ ] **Licensing information**: Please list the open source licenses your project is under here, for example, Apache 2.0.

### Optional information to include in your README

- [ ] **[Badges](https://github.com/Camunda-Community-Hub/community/blob/main/extension-lifecycle.md)**: These give community members a visual representation of your extension’s build status, lifecycle, release version, and other useful metadata.
- [ ] **Visuals**: If your project relies on screenshots, please ensure that you also add alt text to screenshots to ensure accessibility for those using screen readers or that have visual disabilities.
- [ ] Keep best practices in mind when using screenshots. Remember to obscure any API keys, secrets, or identifiers that could be exploited maliciously.
- [ ] **Contributors, maintainers, and other acknowledgements:** If you would like to include this section, it is a nice way to show appreciation for the individuals who contributed to your project.
- [ ] **Roadmap**: GitHub [project boards](https://docs.github.com/en/github/managing-your-work-on-github/about-project-boards) are a great way to showcase your roadmap for your extension. If you have one set up, it’s a good idea to link to it in your README.
- [ ] Make the steps to get started with your extension clear to understand for those that may not have a similar background to yourself.
