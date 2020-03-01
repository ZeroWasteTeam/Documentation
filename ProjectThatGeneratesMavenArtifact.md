# Expectation for repos that generate maven artifacts
- The repo name is same as the maven artifact
- The maven artifact is published to Git Hub packages through Git Hub Actions
- The build tool used is gradle (groovy)
- The project is unit tested by Junit4
- The master branch is protected. (Direct commits are not possible)
- New version of the artifact is generated when a any pull request is merged to the master branch
- When a feature branch is pushed, a alpha/beta version of the artifact is produced if the commit is tagged with alpha*

