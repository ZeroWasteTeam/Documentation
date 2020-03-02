# Expectation of the CI system (Build)
- The system should builds the code as quickly as possible when code is commited to the repository
- There has to be clear convention that decides which commits are builded and which are not
- When a new repository is created, it must be extremely easy for the developer to set up the build.
- The process of setting up the build has to be clearly documented
- The build should produce binaries that could be used by the deployments which out much of documentation. It would not be clear how to deploy a zip file. However it would be very clear how to deploy a Helm Chart or docker image
- The build system should ensure that the "master" branch at all point of time contains deployable code
- The build system should automate the execution of the unit tests.

- The repo name is same as the maven artifact
- The maven artifact is published to Git binaHub packages through Git Hub Actions
- The build tool used is gradle (groovy)
- The project is unit tested by Junit4
- The master branch is protected. (Direct commits are not possible)
- New version of the artifact is generated when a any pull request is merged to the master branch
- When a feature branch is pushed, a alpha/beta version of the artifact is produced if the commit is tagged with alpha*

