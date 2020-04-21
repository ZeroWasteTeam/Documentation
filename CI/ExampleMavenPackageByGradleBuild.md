### Repo setup for a repo coded in Java that is producing a Maven package and build by gradle

 * Create a empty repository
 * Add version file to the repo
 * Add app-type file to the repo
 * Add three workflows (PR, Master, Repository Dispatch) to the repo. The work flows are added by adding a yaml file in .github/workflows directory. You can download the yaml files from here (TODO)
 * Create a branch, and raise a pull request. (This pull request is a dummy pull request to search of workflows at PR)
 * Create a branch protection rule for "master" branch as detailed here (TODO)
 
 ### Examples
 * This [example](https://github.com/ZeroWasteTeam/SampleJavaMavenPackage) produces a maven package
 * This [example](https://github.com/ZeroWasteTeam/SampleMavenConsumingJava) produces a maven package and also consumes another maven package
  
