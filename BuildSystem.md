# Build System (CI)

This document explains the build system designed and incorporated in Zero Waste Team Project. The document is structured as below
* The vision of the CI system
* The tools that make the system
* The Git branching stratergy using in the project
* Versioning stratergy
* Steps involved in setting up a new repo

## Vision

The code is versioned in Git repositories by the Zero Waste Team. The CI system is envisioned to be build around the git repositories that has the following goals met. 
* On checkin/push/merge in to specific branches, the solution is build, unit tested and artifact is published
* The most important customer of the CI system is the developement team. And the CI system should serve the development team by meeting the following
  * The CI system would be set up every time a new repo is created. It must be very easy to set it up. The setup should take utmost 10 mins.
  * The builds should be fast and unwanted tasks should not happen in the build
  * The builds would be more frequent in the working hours and less in the non working hours. So the infrastructure should be elastic
  * The system should give clear version numbers for the artifacts
  * There should be traceability between the artifact and git commit
  * There should be good dash board that gives the overall picture of various projects in the organization
  

### Setup friendly
Dev team being the major customer, this system is designed to enable the developers. When a new repository is created, the developers have to configure the build system for it. The build system is so designed, that the developer should be able to get the build system up for a new repository with in 10 minutes

### Consumption friendly
When the build system produces artifacts such as folder or zip files, it not evident for the operation team how these artifacts need to used. On the other hand, when the build system produces artifacts such as maven, nuget, npm, docker or helm artificats, it's extremely clear for the operations team (or the dev team) on how to consume them. To facilitate easy consumption of the build artifacts, the build system shall produce standard artifacts such as maven, nuget, npm, docker or helm artifacts.

## Tools
* **Repo:** The source code is maintained in git repositories that are hosted in GitHub
* **Build Tool:** The build tool used in [GitHub Actions](https://help.github.com/en/actions) 
* **Artifactory:** The artifactory used is [GitHub packages](https://help.github.com/en/packages/publishing-and-managing-packages/about-github-packages). It supports Maven, Npm, Nuget, Docker and many more. However it does not support Helm Charts. A custom helm chart repository can be however easily created github repository.

**Note 1**: Circle CI and Travis CI are better and more mature than Git Hub actions in many aspects. The lack of organization level secrets is a limitation to be over come in git hub actions. Git hub actions is choosen as it provides easy integration to git hub packages and git hub repositories. Effective dashboarding mechanism is also not available in GitHub Actions.

**Note 2**: JFrog Artifactory and ProGet are better than GitHub Packages in many aspects. The choice of GitHub packages is due to the integration with other build tools. It also provides an easy mechanism to download these packages for local developement. As it's integrated with the repository, there is no need to have separate credentials. The Git Hub packages are per repository. This when used as is creates many binary repositories. This has to be worked around


## Branching Stratergy

When using a git repository, its important have a proper branching stratery in place. There are many popular branching stratergies such as Git Flow, Github Flow, GitLab Flow, Release Flow, etc...

* **Library Projects:** GitHub flow will be adopted for library projects (that produce artifacts such as maven, nuget, npm packages)
* **Web Application Project:** Release flow will be adopted for web application projects (these projects will produce docker images and helm chats as artifacts) 
