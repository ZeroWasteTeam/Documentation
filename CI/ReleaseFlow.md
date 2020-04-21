# Release Flow

* Release flow is similar to GitHub flow in most aspects
* This flow was crafted by VSTS team in Microsoft
* The difference between GitHub Flow and Release Flow: In GitHub Flow, the releases are made from master. In Release Flow, a new release branch is created for every release and release is made from that branch.
* This gives the ability to deploy different code base to different simultaneous releases for different customers
* In GitHub flow, it's very important to maintain the master branch deployable always. This rule could be relaxed a bit here.
* If there is any bug in the release branch, then the bug could be fixed in the a branch off the release branch and then merged. Or we could cherry pick a commit to the release branch
* We could also merge the release branch in to master, and delete the release branch once a newer version is deployed to the customers using that release.
![Release Flow](/images/release-flow.png)
