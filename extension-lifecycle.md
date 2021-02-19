# The Extension Lifecycle
## Camunda community contributed extensions adhere to a project lifecycle that aims to balance the needs of the broader community with that of the Camunda ecosystem as a whole. This section will also detail the process for reporting abandoned extensions.

Community extensions will have the following labels applied to them in addition to the ‘Community Extension,’ label, designating where they are in terms of current usability, project stability, and overall lifecycle status:

### Proof-of-Concept <img src="https://img.shields.io/badge/Lifecycle-Proof%20of%20Concept-blueviolet">
* Proof-of-Concept/experimental extensions are just that, ideas that community members would like to explore further. 
* They offer little support, nor do they promise any stability. 
* This label is most often applied to extensions that are used to validate a Proof-of-Concept for working with Camunda Cloud or Camunda Platform, or for those interested in finding collaborators on a particular project that has the potential to grow into a Stable extension.

### Incubating <img src="https://img.shields.io/badge/Lifecycle-Incubating-blue">
* Extensions with the, ‘Incubating’ label provide some degree of stability which is defined and adhered to by the project’s maintainer, community support, and are actively maintained and updated. Documentation gaps, roadblocks, bugs, and other issues are to be expected. There is currently no set time limit for an extension to move out of incubation status.

### Stable <img src="https://img.shields.io/badge/Lifecycle-Stable-brightgreen">
* An extension with the, ‘Stable,’ label has an active, thriving community surrounding it. It releases updates on a regular basis, has active maintainers and community participants, and may be actively used at an organizational level.
* Maintainers of Stable extensions are actively in contact with the Camunda team, or may have one or more Camunda team members actively contributing to the extension.
* Stable extension maintainers and reviewers are expected to adhere to [our expectations] surrounding PR reviews, and communication
* Stable Community Extensions have agreed to follow the Camunda Community Extension [issue triage and pull request review process] outlined below.
* Having a Stable Community Extension means that much of the heavy lifting of building/maintenance surrounding releases is done for you with the ability to implement GitHub actions to automatically publish your extension to Maven Central!

### Deprecated <img src="https://img.shields.io/badge/Lifecycle-Deprecated-yellowgreen">
* An extension with the ‘Deprecated,’ label is no longer being maintained. While it may work on your machine just fine today, there is no guarantee that it will work in the future. **Use these extensions at your own risk.**

### Abandoned <img src="https://img.shields.io/badge/Lifecycle-Abandoned-lightgrey">
* Extensions are considered abandoned when the project’s owner is no longer updating the extension, or has not responded to open issues or pull requests within 30 days, or has notified a Camunda team member via [this template] that they are no longer actively maintaining the extension. 
* If you are interested in stepping up to maintain an abandoned extension, please open a new pull request using the Extension Review Template and complete the ‘New Maintainer Suggestion’ Section
* * If you are a Maintainer that is no longer able to Maintain your extension, you can add the 'Needs Maintainer' Shields.io badge to your extension's README file to help notify others that the extension is in need of a Maintainer. <img src="https://img.shields.io/badge/Lifecycle-Needs%20Maintainer%20-ff69b4">
* In your request, please be sure to detail as much as possible your plans for maintaining the extension moving forward, and please link to a discussion that shows you have made a good faith effort to contact the extension’s original developer.
* Requesting removal of a community extension
* When an extension has critical bugs and is not actively maintained, it may need to be removed from the Camunda Community Hub. To facilitate this process, please complete the following steps:
* Open an issue on the issue tracker for the extension
* Wait 30 days for a response from the project maintainer
* If no response is received, or a maintainer confirms that they no longer wish to maintain the project, follow the steps outlined in the Extension Review Template which will notify the Camunda team to remove the extension from the Community Hub and any existing Camunda documentation. 
