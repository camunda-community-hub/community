# Security and Dependency Management Policy
- [Security Tools in Place](#security-tools-in-place)
- [When should I report a vulnerability?](#when-should-i-report-a-vulnerability)
- [When should I **not** report a vulnerability?](#when-should-i-not-report-a-vulnerability)
- [Public disclosure timelines](#public-disclosure-timelines)
- [Publishing information on a vulnerability](#publishing-information-on-a-vulnerability)
- [Handling possible vulnerabilities](#handling-possible-vulnerabilities)
- [Dependency management policy](#dependency-management-policy)
- [Dependency issues](#dependency-issues)
  - [Who handles dependency management if a maintainer is away, or a project is unmaintained?](#who-handles-dependency-management-if-a-maintainer-is-away-or-a-project-is-unmaintained)
  - [Types of dependencies](#types-of-dependencies)
  - [Why dependency classifications matter](#why-dependency-classifications-matter)
  - [How to update open source dependencies](#how-to-update-open-source-dependencies)
  - [Potential consequences of using outdated dependencies](#potential-consequences-of-using-outdated-dependencies)
- [Inspiration](#inspiration)

This document provides help and advice to projects in the Camunda Community hub regarding security issues, and how to handle reporting of security vulnerabilities. 
As projects in the Camunda Community Hub are community maintained, security prevention is the responsibility of a project’s maintainer. 

In the Camunda Community Hub, we take security seriously.  As open source practitioners, it is our aim to empower those in this space to develop extensions with security best practices in mind. 

We aim to enable our community to work together to provide assistance to all of those involved in the community hub on the ongoing topic of 
DevSecOps, security, and dependency management. We encourage the community as a whole to work with maintainers, and to open issues that 
address any security vulnerabilities in a repository according to the guidelines listed in this documentation. 

## Security Tools in Place 

* [Dependabot](https://dependabot.com/) - Enabled at the Organization level
* [Renovate](https://github.com/renovatebot/renovate) - Opt in
* The [Community Action Maven Release](https://github.com/camunda-community-hub/community-action-maven-release#security-scanning) allows 
maintainers to opt-in to Aqua Security’s Trivy container security scanning tool, 
and uploads the results of HIGH and CRITICAL vulnerabilities to the GitHub Security tab


## When should I report a vulnerability?

* You think you have discovered a security vulnerability in a Camunda Community Hub extension
* You aren’t sure of, or if, a vulnerability impacts a Camunda Community Hub extension you are using
* You think you’ve discovered a security vulnerability in another project that a Camunda Community Hub extension is dependent on
* For projects that have their own vulnerability processes and disclosure policies, please report your vulnerability there, following that project’s 
stated guidelines

## When should I **not** report a vulnerability?

* You need help fine-tuning an extension in the Camunda Community Hub for adherence to security best practices
* You have a question about the security of an extension in the Camunda Community Hub
* Your question or issue isn’t related to the security of an extension in the Camunda Community Hub

## Public disclosure timelines

* Public disclosure dates will be discussed between the vulnerability reporter and the impacted project’s Maintainer. 
* When a fix is available, we will then disclose the bug to the public. 
* If a vulnerability is not fully understood or a fix is not yet implemented, a disclosure date may be modified or pushed back to allow for further research, 
* coordination, or additional time to fix the issue. The estimated time frame for disclosure ranges from immediate (in the case of vulnerabilities which are already known to the public) to a few weeks. 

## Publishing information on a vulnerability

Projects with known, published security vulnerabilities should provide information about those vulnerabilities on their repository’s GitHub Security 
page if they have the permissions to do so. If you do not have the permissions level needed, and would like to publish a security advisory, 
please open an issue in your repository, apply the waiting-for-camunda issue label and tag @celanthe. As an alternative, 
maintainers can opt to provide a clear link in their README or on the project’s website to their security information, current vulnerabilities, 
and their security, testing, and/or dependency management policies for their extension. 

When reporting a vulnerability or issue, please keep security best practices in mind, and try to eliminate publicly posting information 
that may result in the potential for an increased attack surface (e.g. by entering details in a public bug tracker, public-facing issue, or pull request).

## Handling possible vulnerabilities

Project maintainers in the Camunda Community Hub are responsible for ensuring that their extensions are secure and free from vulnerabilities 
to the best of their ability. For all potential vulnerabilities related to Apache-specific distributions, dependencies, tools, or services, 
please follow the Apache Software Foundation (ASF) [guidelines and procedures for reporting a vulnerability directly to the ASF](https://apache.org/security/#vulnerability-handling).

* If your potential vulnerability does not impact a tool handled by the Apache Security foundation or that falls under its umbrella, 
you may report it privately in a secure channel to the project’s maintainer, and email community@camunda.com 
* The impacted project’s maintainer will work with you as the reporter of the vulnerability to investigate it 
* The project’s maintainer and the issue reporter will work together to resolve the vulnerability
* The project maintainer and the issue reporter will work together to write documentation and a report on the vulnerability and its fix. This report and documentation should contain enough information that users will be able to assess the potential risks associated with the vulnerability for their own system/extension. This documentation does not include how to reproduce the vulnerability.
* The team agrees on an acceptable release timeline for the vulnerability to be resolved, or raises concerns on issues that may impact a proposed timeline before one is agreed upon
* The project maintainer publishes a new release of the extension with the dependencies/tools impacted by the vulnerability and delivers a fix
* The Camunda team publishes the new release if the extension is using the GitHub Actions Maven Release CI/CD workflow
* The maintainer announces the vulnerability publicly on the GitHub security page, and details how to apply the fix
  * This is the first point that any information about a vulnerability should be made public


## Dependency management policy


Dependencies are the files, libraries, packages, and/or plugins integrated into a project to complete a set of tasks.
These dependencies are the responsibility of project maintainers to manage and keep up to date. 
Projects that have vulnerable dependencies that are not resolved within 30 days may be removed from the Camunda Community Hub.

## Dependency issues

Applications can encounter dependency issues for a number of reasons:

* Usage of outdated third-party libraries
* Poorly implemented code
* Using third-party databases
* Using external, web-based services for a particular feature or functionality
* Implementation of untested libraries for metrics collection

External dependencies are often utilized in the open source community, and can lead to security issues. 
These can be the addition of malicious code, hidden cryptocurrency miners, performance issues, and more. 
In order to avoid these issues, extension dependencies need to be actively managed, maintained, and kept up-to-date. By keeping dependencies in the 
Camunda Community Hub up-to-date, we ensure that community extensions avoid security implications or issues that may arise from using outdated libraries, code, 
or services.

### Who handles dependency management if a maintainer is away, or a project is unmaintained?

Ideally, it is the responsibility of the community to help manage dependency management. If a project has multiple collaborators and the code owner 
will be unavailable for an extended period of time, outside collaborators should make an effort to update the project’s dependencies when needed. 

When needed, the Camunda DevRel team may update an unmaintained project’s dependencies if it is deemed necessary.

### Types of dependencies

* Direct dependencies - Libraries or plugins that directly integrate with an application.
* Development dependencies - These are included in a project’s package.json and are executed by files in the development phase. 
These can be used by remote hosts such as linters and presets.
* Transitive dependencies - A library called by a direct dependency. 
Conflicts and issues can arise when a direct dependency doesn’t support updated versions of its transitive dependencies. 
We recommend avoiding the use of implicit transitive dependencies, and suggest explicitly maintaining any transitive dependencies in use by 
your project’s direct dependencies.
* Runtime dependencies - These include frontend dependencies which run in the user’s browser, and backend dependencies which run in the backend for 
http communications with a server or database.

### Why dependency classifications matter 

Dependencies can be classified as mandatory, discrete, or external. 

* Mandatory dependencies are those that your project needs to function. Without this particular dependency, your application will not work as expected.
* Discrete dependencies are defined sequences between activities. This is a certain order of activities that happen based on the structure of a particular project and its codebase.
* External dependencies do not involve a project’s team. Internal dependencies, on the other hand, impact maintainers and any outside collaborators on a project.


### How to update open source dependencies

* Assign yourself as a reviewer of the pull request in question, if there is no CODEOWNERS file present to automatically assign reviewers.
* Review the changes in the pull request to better understand how the changes will impact the extension if applied
* Determine where this dependency is used in the code to ascertain its impact on the extension
* Conduct a regression test to ensure that the proposed changes do not break functionality of the existing application, plugin, or extension
* Merge automated dependency updates individually, rather than in bulk. By merging changes individually, if there is a problem, you can quickly determine the upgrade that caused the issue.

### Potential consequences of using outdated dependencies

Maintainers may delay updating dependencies out of fear that they will break their extension’s functionality, which may result in downtime for customers and end users. Using outdated or improperly configured dependencies exposes you to a variety of security risks such as:

* Security vulnerabilities
* Reduced extension, plugin, or application performance
* Conflicts in coupled processes
* Increased technical debt
* Increased project maintenance 
* Greater exposed attack surfaces

Open source tools such as Maven also pull in their own external third-party dependencies. 
While it can be challenging to update these dependencies, it is not impossible. 

* Ensure that your extensions comply with the license listed by the open source libraries integrated in your application. 
* Make use of open source tools such as Snyk, Trivy, JFrog X-Ray, and more to help ensure your Maven dependencies are up-to-date. 
* Perform regression tests
* Make regression tests and dependency management a part of your CI/CD workflow
* Using Dependabot and Renovate for dependency management: 

Repositories in the Camunda Community Hub have the automated dependency tool dependabot installed at the Organizational level. 
Dependabot is integrated with GitHub, and powers GitHub’s automated security update feature introduced in 2019. Repository Administrators can interact with Dependabot directly from the GitHub UI. To enable dependabot security updates, go to your repository’s Settings page, click the Security & Analysis tab, and then click Enable next to `Dependabot security updates.` 

Administrators have the following permissions when accessing security features in GitHub repositories within the Camunda Community Hub:

* Receive dependabot alerts for vulnerable dependencies
* Dismiss alerts from dependabot
* Designate additional teams/people to receive dependabot alerts
* Create security advisories
* Manage access to advanced security features on GitHub
* Enable dependency graphs for private repositories

Administrators and Maintainers have the following permissions when accessing security features in GitHub repositories within the Camunda Community Hub:

* View dependency reviews
* View code scanning alerts on open pull requests
* List, dismiss, or delete code scanning alerts
* View secret scan alerts in a repository*
** Repository writers and maintainers can only see alert information for their own commits.
* Resolve, revoke, or re-open secret scan alerts*
** Repository writers and maintainers can only see alert information for their own commits.


Maintainers are also able to request that renovate be added to their repository for dependency management.
At this time, we strongly recommend maintainers evaluate using renovate for dependency management in their repositories. 
Renovate offers maintainers fine-grained control and configuration when deciding when to auto-merge pull requests for dependencies. 
These are based on rules that a maintainer sets in their repository’s renovate configuration file. 

Renovate works with JavaScript, NPM, Yarn, Go, Bazel, Docker, Nugget, PHP, Python, and Ruby.

Ultimately, we leave this decision of which dependency management tool to use in the hands of extension maintainers and their communities. 
We look forward to steering the conversation surrounding these tools, and continuing to improve dependency management and the experience of developers in the
Camunda Community Hub moving forward.

## Inspiration

This documentation was inspired by the [Apache Security Team](https://apache.org/security), [Crowdbotics](https://blog.crowdbotics.com/how-to-ensure-that-your-dependencies-are-up-to-date/),
[The Diana Initiative Slack community](https://join.slack.com/t/dianainitiative/shared_invite/zt-t4m9w3zp-3bUr~WDv~GIRJkT8W0lXLg), and the [Kubernetes Security and Disclosure information](https://kubernetes.io/docs/reference/issues-security/security/#report-a-vulnerability).

