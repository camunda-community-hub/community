# The extension lifecycle
Camunda community extensions adhere to a project lifecycle that aims to balance the needs of the broader community with that of the Camunda ecosystem as a whole. This section will also detail the process for reporting abandoned extensions.

Community extensions will have the following labels and Shields.io badges applied to them in addition to the `Community Extension` label/badge, designating where they are in terms of current usability, project stability, and overall lifecycle status.

To use one of the Shields.io badges in your extension's README, copy the <code>img src</code> code and the accompanying image URL with the extension lifecycle label you'd like to use into your README and paste it at the top of the README.

## Community Extension <img src="https://img.shields.io/badge/Community%20Extension-An%20open%20source%20community%20maintained%20project-FF4700" alt="an orange badge that reads 'Community Extension: An open source community maintained project">

* This badge designates that an extension is maintained by the open source community
* To add this badge to your repository, add the following code at the top of your extension's README file ```[![](https://img.shields.io/badge/Community%20Extension-An%20open%20source%20community%20maintained%20project-FF4700)](https://github.com/camunda-community-hub/community)```

## Compatiblilty 
<img src="https://img.shields.io/badge/Compatible%20with-Camunda%208-0072CE">

* This badge indicates that your extension is compatible with Camunda 8
* To add this badge to your repo, add the following code in your extension's README file ```![Compatible with: Camunda 8](https://img.shields.io/badge/Compatible%20with-Camunda%208-0072Ce)```

<img src="https://img.shields.io/badge/Compatible%20with-Camunda%207-26d07c"> 

* This badge indicates that your extension is compatible with Camunda 7
* To add this badge to your repo, add the following code in your extension's README file ```![Compatible with: Camunda 7](https://img.shields.io/badge/Compatible%20with-Camunda%207-26d07c)```

## Educational Tooling <img src="https://img.shields.io/badge/Educational%20Tooling-Project%20for%20getting%20started%20with%20Camunda%20for%20educators-%239F2B68" alt="a purple badge that reads 'Educational Tooling - Project for getting started with Camunda for educators'">

* This badge designates that an extension is used for getting started with Camunda for educators and university programs
* To add this badge to your repository, add the following code at the top of your extension's README file ```[![](https://img.shields.io/badge/Educational%20Tooling-Project%20for%20getting%20started%20with%20Camunda%20for%20educators-%239F2B68)```

## Tutorial Reference Project <img src="https://img.shields.io/badge/Tutorial%20Reference%20Project-Tutorials%20for%20getting%20started%20with%20Camunda-%2338A3E1" alt="A blue badge that reads: 'Tutorial Reference Project - Tutorials for getting started with Camunda'">

* This badge designates that an extension is a tutorial or part of a video tutorial series used for getting started with Camunda

## Proof-of-Concept <img src="https://img.shields.io/badge/Lifecycle-Proof%20of%20Concept-blueviolet" alt="Violet purple Shields.io badge that reads Lifecycle: Proof of Concept">
* Proof-of-Concept/experimental extensions are just that, ideas that community members would like to explore further. 
* They offer little support, nor do they promise any stability. 
* This label is most often applied to extensions that are used to validate a Proof-of-Concept for working with Camunda 7 or Camunda 8, or for those interested in finding collaborators on a particular project that has the potential to grow into a Stable extension.
* To add this badge to your repository, add the following code at the top of your extension's README file: ```[![](https://img.shields.io/badge/Lifecycle-Proof%20of%20Concept-blueviolet)](https://github.com/Camunda-Community-Hub/community/blob/main/extension-lifecycle.md#proof-of-concept-)```

### Incubating <img src="https://img.shields.io/badge/Lifecycle-Incubating-blue" alt="Blue Shields.io badge that reads Lifecycle: Incubating">
* Extensions with the ‘Incubating’ label provide some degree of stability which is defined and adhered to by the project’s maintainer, community support, and are actively maintained and updated. Documentation gaps, roadblocks, bugs, and other issues are to be expected. There is currently no set time limit for an extension to move out of incubation status.
* To add this badge to your repository, add the following code at the top of your extension's README file: ```[![](https://img.shields.io/badge/Lifecycle-Incubating-blue)](https://github.com/Camunda-Community-Hub/community/blob/main/extension-lifecycle.md#incubating-)```

## Stable <img src="https://img.shields.io/badge/Lifecycle-Stable-brightgreen" alt="Green Shields.io badge that reads Lifecycle: Stable">
* An extension with the `Stable` label has an active, thriving community surrounding it. It releases updates on a regular basis, has active maintainers and community participants, and may be actively used at an organizational level.
* Maintainers of stable extensions are actively in contact with the Camunda team, or may have one or more Camunda team members actively contributing to the extension.
* Stable extension maintainers and reviewers are expected to adhere to [our expectations](https://github.com/camunda-community-hub/community#maintainer-expectations) surrounding PR reviews, and communication
* Stable Community Extensions have agreed to follow the Camunda Community Extension [issue triage and pull request review process](https://github.com/camunda-community-hub/community/blob/main/issue-triage.md)
* Your extension must contain and abide by the [Camunda Community Hub Code of Conduct ](https://github.com/camunda-community-hub/community/blob/main/CODE_OF_CONDUCT.MD)
* Your extension must have a [contributor guide ](https://github.com/camunda-community-hub/community/blob/main/CONTRIBUTING.MD)
* Having a stable community extension means that much of the heavy lifting of building/maintenance surrounding releases is done for you with the ability to implement GitHub actions to automatically publish your extension to [Maven Central](https://github.com/camunda-community-hub/community-action-maven-release) if applicable to your extension. Initially, by utilizing the above GitHub Workflow, maintainers of Java-based extensions can implement to automate the publishing of new artifacts to Maven Central. We plan to introduce further GitHub workflows in the future for automating release management for other frameworks and libraries, in addition to Maven and Java. 
* To add this badge to your repository, add the following code at the top of your extension's README file: ```[![](https://img.shields.io/badge/Lifecycle-Stable-brightgreen)](https://github.com/Camunda-Community-Hub/community/blob/main/extension-lifecycle.md#stable-)```

## Deprecated <img src="https://img.shields.io/badge/Lifecycle-Deprecated-yellowgreen" alt="Yellow Shields.io badge that reads Lifecycle: Deprecated">
* An extension with the `Deprecated` label is no longer being maintained. While it may work on your machine just fine today, there is no guarantee that it will work in the future. **Use these extensions at your own risk.**
* To add this badge to your repository, add the following code at the top of your extension's README file: ```[![](https://img.shields.io/badge/Lifecycle-Deprecated-yellowgreen)](https://github.com/Camunda-Community-Hub/community/blob/main/extension-lifecycle.md#deprecated-)```

## Unmaintained <img src="https://img.shields.io/badge/Lifecycle-unmaintained-lightgrey" alt="Light gray Shields.io badge that reads Lifecycle: Unmaintained">
* Extensions are considered unmaintained when the project’s owner is no longer updating the extension, or has not responded to open issues or pull requests within 30 days, or has notified a Camunda team member via [this template] that they are no longer actively maintaining the extension.
* To add this badge to your repository, add the following code at the top of your extension's README file: ```[![](https://img.shields.io/badge/Lifecycle-Unmaintained-lightgrey)](https://github.com/Camunda-Community-Hub/community/blob/main/extension-lifecycle.md#Unmaintained-)```
* If you are interested in stepping up to maintain a previously unmaintained extension, please [open a new issue using the Extension Review Template](https://github.com/camunda-community-hub/community/issues/new/choose) and complete the ‘New Maintainer Suggestion’ Section
  * In your request, please be sure to detail as much as possible your plans for maintaining the extension moving forward, and please link to a discussion that shows you have made a good faith effort to contact the extension’s original developer.
* If you are a maintainer that is no longer able to maintain your extension, you can add the 'Needs  Maintainer' Shields.io badge to your extension's README file to help notify others that the extension is in need of a maintainer. <img src="https://img.shields.io/badge/Lifecycle-Needs%20Maintainer%20-ff69b4" alt="Hot pink Shields.io badge that reads Lifecycle: Needs Maintainer">
  * To add this badge to your repository, add the following code at the top of your extension's README file: ```[![](https://img.shields.io/badge/Maintainer%20Wanted-This%20extension%20is%20in%20search%20of%20a%20Maintainer-ff69b4)```

Note: If you no longer wish to maintain your extension, please follow the instructions for opening a pull request using the template provided, and apply the `Lifecycle - Maintainer Wanted` badge and Probot labels to your extension’s repository, issues, and open PRs.

### Requesting removal of a community extension
When an extension has critical bugs and is not actively maintained, it may need to be removed from the Camunda Community Hub. To facilitate this process, please complete the following steps:
1. Open an issue on the issue tracker for the extension.
2. Wait 30 days for a response from the project maintainer.
3. If no response is received, or a maintainer confirms that they no longer wish to maintain the project, follow the steps outlined in the [Extension Review Template](https://github.com/camunda-community-hub/community/issues/new/choose) which will notify the Camunda team to remove the extension from the Community Hub and any existing Camunda documentation. 
