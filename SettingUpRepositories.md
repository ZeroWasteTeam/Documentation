# Setting up repository

This document explains how to set up a repository and CI system

* Example of setting up a repository that produces a maven (java) package and built by gradle is here
* Example of consuming a maven (java) package by a java library is here.
* Example of dockerized spring boot application build by gradle published as a helm chart is here
* Example of dockerized spring boot application build by maven published as a helm chart is here


* Create a git hub repository
* Clone the empty repository
* In the root of the repository, create a folder named .github
* Create a file named version.txt in the root of the repo. The contents of this file should be 0.1 without a new line
* Create a file named appType.txt, the contents of this file should be
  * for MavenJavaPackage - "MavenJava"
  * for JavaWebApplication -"WebJava"
* Copy the contents of zip in to the .github folder
  * For MavenJavaPackage built by gradle [this](https://wondertools.github.io/GitHubDownloader/#/home?url=https://github.com/ZeroWasteTeam/SampleJavaMavenPackage/tree/master/.github)
  * For JavaWebApplication built by gradle this
* Commit all changes till now and push to origin
* Create a new branch name 'firstbranch', in the branch add a file first.txt with contents 'hello'. Commit the changes and push
* Create a pull request for the newly created branch. (This pull request is a dummy pull request to ensure the checks are run and recognized)
Go to settings of the project repository, and ensure the following
* In features
  * Uncheck "Wikis"
  * Uncheck "Restrict editing to users in teams with push access only"
  * Uncheck "Issues"
  * Uncheck "Sponsorships"
  * Uncheck "Projects"
* In Data Services
  * Make sure "Security alerts" is checked
* Merge Button
  * Uncheck "Allow merge commits"
  * Make sure "Allow squash merging" is checked
  * Uncheck "Allow rebase merging"
  * Uncheck "Automatically delete head branches"
* In Settings page, go to branches, click on add rules
  * Enter the branch name as "master"
  * Check "Require pull request reviews before merging"
  * Check "Require status checks to pass before merging"
  * Check sub section "Require branches to be up to date before merging"
  * Check sub section "Java PR Build"
  * Check "Require linear history"
  * Check "Include administrators"
  * And then click on "Create"
* For Web applications
  * Add a new rule with the same details for the branch pattern named "rel-*"

## Examples

* A sample Maven package project in Java build using gradle is [here](https://github.com/ZeroWasteTeam/SampleJavaMavenPackage)
* A sample Maven package consuming Java project build using gradle is [here](https://github.com/ZeroWasteTeam/SampleMavenConsumingJava)
