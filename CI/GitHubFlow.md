# GitHub Flow

There are many articles in the internet that explains about the branching model. The core of it is captured here. For more descriptive or elaborative information please refer other articles.

* The master is the the deployable branch. Any commit in master is deployable
* For a new feature (or bug fix), a branch is created. The relevent code is commited in one or more commits.
* Once the feature developement is completed in the feature branch, then branch is merged to master by a pull request after review
![One Featue Git Hub Flow](/images/git-feature-branch.png)
* When multiple features (say feature1 and feature2) are developed parallely, when we try to merge feature2, feature1 might be already merged. At this point, we need to merge master in to feature2 and then raise a pull request from feature2 to master. (There are many others ways to do this such as rebase, and direct merge in case of no conflict. - not followed in this project)
![Multiple Featues Git Hub Flow](/images/git-multiple-feature-branch.png)
