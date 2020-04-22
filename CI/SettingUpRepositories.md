# Setting up repository
The way a repository is set up is hugely dependent on the type of the repository (library or application)

## Setting up a Library Project Repository

### Expectation of the CI system (Build)
 1. A master build is triggered when a pull request to master branch is completed. The master build publishes the library artifact.
 2. A Repository Dispatch is triggered when the a build is triggered through the [tool](https://zerowasteteam.github.io/build-requestor/). The build publishes the library artifact.
 3. A PR build should be mergable only when the below conditions are met
   1. When the PR build runs successfully (versioning rule and unit tests are met)
   2. When the PR is review at least by one developer
   3. The PR branch is based on the lastest version of master   
 4. The master branch should support linear version history 

### Setting up of a library Project
 1. Create a empty repository
 2. Add version file (version.txt) to the repository. The content of the file has to be "<major-version>.<minor-version>"
 3. Add app-type file (app-type.txt) to the repository. The content of the file has to be "lib"
 4. Add scripts files to the repository
   1. scripts-build.sh - This script will be called by workflows to build the project.
   2. scripts-test.sh - This script will be called by the workflows to unit test the project.
   3. scripts-package.sh - This script will be called by the workflows to publish the project artifacts.
 5. Add Master Build workflow. How to add a work flow can be found [here](https://help.github.com/en/actions/configuring-and-managing-workflows/configuring-a-workflow)
 6. Add PR build workflow
 7. Add Repository dispatch workflow
 8. Create a dummy branch and a dummy pull request. This is done to so that the system searches for the workflows.
 9. Create a branch protection rule for "master" branch as detailed [here](BranchProtectionRuleSetup.md)
 10. There is a bit of tradeoff in consuming maven packages. More information is available [here](MavenPackages.md)

 ### Examples
 * This [example](https://github.com/ZeroWasteTeam/SampleJavaMavenPackage) produces a maven package.
 * This [example](https://github.com/ZeroWasteTeam/SampleMavenConsumingJava) produces a maven package and also consumes another maven package


## Setting up a Application Project Repository

### Expectation of the CI system (Build)
 1. A master build is triggered when a pull request to master/rel-* branch is completed. The master build publishes the artifact.
 2. A Repository Dispatch is triggered when the a build is triggered through the [tool](https://zerowasteteam.github.io/build-requestor/). The build publishes the artifact.
 3. A PR to master/rel-* should be mergable only when the below conditions are met
   1. When the PR build runs successfully (versioning rule and unit tests are met)
   2. When the PR is review at least by one developer
   3. The PR branch is based on the lastest version of master   
 4. The master branch should support linear version history 

### Setting up of a Application Project
 1. Create a empty repository
 2. Add version file (version.txt) to the repository. The content of the file has to be "<major-version>.<minor-version>"
 3. Add app-type file (app-type.txt) to the repository. The content of the file has to be "app"
 4. Add scripts files to the repository
   1. scripts-build.sh - This script will be called by workflows to build the project.
   2. scripts-test.sh - This script will be called by the workflows to unit test the project.
   3. scripts-package.sh - This script will be called by the workflows to publish the project artifacts.
 5. Add Master Build workflow. How to add a work flow can be found [here](https://help.github.com/en/actions/configuring-and-managing-workflows/configuring-a-workflow)
 6. Add PR build workflow
 7. Add Repository dispatch workflow
 8. Create a dummy branch and a dummy pull request. This is done to so that the system searches for the workflows.
 9. Create a branch protection rule for "master" and "rel-*" branches as detailed [here](BranchProtectionRuleSetup.md)
 10. There is a bit of tradeoff in consuming maven packages. More information is available [here](MavenPackages.md)

 ### Examples
 * TBD

