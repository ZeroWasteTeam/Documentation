# Branch protection rule setup

Information on how to setup branch protection can be found [here](https://help.github.com/en/enterprise/2.16/admin/developer-workflow/configuring-protected-branches-and-required-status-checks)

## Rules that need to be setup
 * Require pull request reviews before merging : yes
   * Required approving review : 1
   * Dismiss stale pull request approvals when new commits are pushed : no
   * Require review from Code Owners : no
   * Restrict who can dismiss pull request reviews : no
 * Require status checks to pass before merging : yes
   * Require branches to be up to date before merging : yes
   * PR Build : yes
   * Require signed commits : no
   * Require linear history : yes
   * Restrict who can push to matching branches : yes
   * Include administrators : no
 * Allow force pushes : no
 * Allow deletions : no
