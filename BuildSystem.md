# Build System (CI)

The system is in place to create binaries that are used for releases and testing.

## Vision

### Setup friendly
Dev team being the major customer, this system is designed to enable the developers. When a new repository is created, the developers have to configure the build system for it. The build system is so designed, that the developer should be able to get the build system up for a new repository with in 10 minutes

### Consumption friendly
When the build system produces artifacts such as folder or zip files, it not evident for the operation team how these artifacts need to used. On the other hand, when the build system produces artifacts such as maven, nuget, npm, docker or helm artificats, it's extremely clear for the operations team (or the dev team) on how to consume them. To facilitate easy consumption of the build artifacts, the build system shall produce standard artifacts such as maven, nuget, npm, docker or helm artifacts.

## Tools
* **Repo:** The source code is maintained in git repositories that are hosted in GitHub
* **Build Tool:** The build tool used in GitHub Actions 
* **Artifactory:** The artifactory used is GitHub packages. It supports Maven, Npm, Nuget, Docker and many more. However it does not support Helm Charts. A custom helm chart repository can be however easily created github repository.

**Note 1**: Circle CI and Travis CI are better and more mature than Git Hub actions in many aspects. The lack of organization level secrets is a limitation to be over come in git hub actions. Git hub actions is choosen as it provides easy integration to git hub packages and git hub repositories. Effective dashboarding mechanism is also not available in GitHub Actions.

**Note 2**: JFron Artifactory and ProGet are better than GitHub Packages in many aspects. The choice of GitHub packages is due to the integration with other build tools. It also provides an easy mechanism to download these packages for local developement. As it's integrated with the repository, there is no need to have separate credentials. The Git Hub packages are per repository. This when used as is creates many binary repositories. This has to be worked around
