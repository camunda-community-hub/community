# Maintainer and Reviewer Expectations

- [Maintainer expectations](#maintainer-expectations)
  - [Identifying a project maintainer](#identifying-a-project-maintainer)
- [Reviewer expectations](#reviewer-expectations)
- [What to include in your extension's README file](#what-to-include-in-your-extensions-readme-file)
  - [Optional information to include in your README file](#optional-information-to-include-in-your-readme-file)

## Maintainer expectations

Maintainers are often the first point of contact that new contributors have with an open source project, and significantly impact the way that the community is perceived. As such, Community Extension Maintainers are a crucial part of the Camunda open source community, and in shaping the Camunda Community Extension Hub. Both extension maintainers and reviewers should remember to abide by the Camunda Code of Conduct when communicating with community members. They should also strive to exceed expectations, exemplifying kindness, respectfulness, and collaboration.

- Maintainers and reviewers are encouraged to review open pull requests on a cadence basis, determined by the project maintainer if a project is in the Proof-of-Concept or Incubation [extension lifecycle stage](https://github.com/Camunda-Community-Hub/community/blob/main/extension-lifecycle.md). 

If an extension maintainer wishes for an extension to be listed as a Stable Community Extension, they must agree to the following standards for pull request review and issue triage:

- Maintainers of a Stable Camunda Community Extension are expected to review open pull requests and issues in their extension's repository within 30 days.
- Follow the [guidelines](https://github.com/Camunda-Community-Hub/community/blob/main/issue-triage.md) for open issue and pull request triage.

If you are a contributor that would like to take over maintaining an extension in the Camunda Community hub that has the Lifecycle: `Abandoned` or `Maintainer Wanted` labels, please review [becoming a Maintainer of an abandoned extension](https://github.com/camunda-community-hub/community/blob/main/abandoned-extension-maintainer-guidelines.MD)

### Identifying a project maintainer

Each Camunda community extension will have listed a Maintainer whose responsibility it is to maintain the extension and drive its progression forward. Otherwise, it will be labelled as `Abandoned`.

## Reviewer expectations

Reviewers can be anyone who is interested in contributing to an extension. They are primarily responsible for reviewing open pull requests (PRs) in a project, are expected to leave helpful feedback where necessary, assign issue triage labels, ask clarifying questions, and to understand the inner workings of the extension whose pull requests they are reviewing. They are encouraged to review any open PRs on a regular basis, which is often determined by the extension's maintainer. 

Reviewers can also review open pull requests at any time that works for them outside of any set official issue triage time set by the extension's maintainer. If a maintainer wishes for an extension to be labelled as a Stable Community Extension, they must agree to the following standards for pull request review and issue triage:

* Reviewers contributing to a Stable Camunda Community Extension are expected to review open pull requests assigned to them in a timely manner
    * If a reviewer fails to respond, a PR may be reassigned to another reviewer after three attempts to contact the reviewer
    * If you are a Camunda Community Extension reviewer, and you are going to be away for an extended period, or no longer have time to dedicate to issue review, please notify the project Maintainer, and remove yourself from any existing documentation that lists you as an active reviewer
    * Reviewers and Maintainers are expected to adhere to our guidelines surrounding [issue triage and labelling](https://github.com/Camunda-Community-Hub/community/blob/main/issue-triage.md) for Stable Community Extensions.


## What to include in your extension's README file

* Lifecycle labels -- Please review the [Camunda Community Hub extension lifecycle](https://github.com/Camunda-Community-Hub/community/blob/main/extension-lifecycle.md) and add a [Shields.io badge](https://shields.io/) to your extension's README that indicates which area of the lifecycle it falls under.
    * Note: If you no longer wish to maintain your extension, please follow the instructions for opening a pull request using the template provided, and apply the Lifecycle - Maintainer Wanted Shield badge and Probot labels to your extension’s repository, issues, and open PRs.
* We highly suggest that all Camunda community extensions follow our established [Style Guide](https://camunda.com/brand/writing-style-guide/) when writing documentation
* A name that clearly identifies your project
    *  Implement the [Camunda community extension badge](https://img.shields.io/badge/Community%20Extension-An%20open%20source%20community%20maintained%20project-FF4700) if you so choose (optional)
* Installation -- If your project has certain dependencies that need to be installed, it is best practice to detail these in your README file
* Using your extension -- Give examples of how one might use your extension. Example use cases are helpful, even if they are smaller in scope. For larger project implementation examples, provide links to these rather than having them in your README file.
* Troubleshooting -- Clearly state the DRI (Directly Responsible Individual) that users of your extension can contact with questions, or if they run into a problem. In most cases this is the extension’s Maintainer, but in some cases it may not be. 
* While we encourage you to create a general discussion thread on our forums about your extension, please direct users that are having trouble working with your extension for any reason to open an issue on GitHub
* Contributing -- If your extension is open to outside contributions from the community, here’s where you should state that, and what your requirements are for accepting/merging a pull request. 
* Document any commands needed to run CI/CD tests, and be sure to include instructions for running tests. 
* Licensing information -- Please list the open source licenses your project is under here. For example, Apache 2.0.

### Optional information to include in your README file

* Badges -- These are created using Shields.io, and give community members a visual representation of your extension’s build status, lifecycle, release version, and other useful metadata
* Visuals -- If your project relies on screenshots, please ensure that you also add alt text to screenshots to ensure accessibility for those using screen readers or that have visual disabilities
* Keep best practices in mind when using screenshots. Remember to obscure any API keys, secrets, or identifiers that could be exploited maliciously
* Authors, maintainers, and other acknowledgements -- If you would like to include this section, it is a nice way to show appreciation for the individuals who contributed to your project
* Roadmap -- GitHub [project boards](https://docs.github.com/en/github/managing-your-work-on-github/about-project-boards) are a great way to showcase your roadmap for your extension. If you have one set up, it’s a good idea to link to it in your README.
* Make the steps to get started with your extension clear to understand for those that may not have a similar background to yourself
