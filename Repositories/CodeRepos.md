# Code And Repositories

* The code is managed in git repositories hosted by GitHub
* As the project is a microservices project, there would be many GitHub repositories
* As the number of services and maven packages increases, the number of git repos will increase
* Managing multiple repos will become difficult. The relative repo structures will be different for developers making composite builds and docker compose difficult.
* As a solution git-meta is adopted
* Git-meta helps in cloning multiple repos in one command, when cloned with git-meta, the relative structure of repos are manitained.
* References
  * https://www.npmjs.com/package/meta-git
  * https://www.npmjs.com/package/meta
* Installing
  * Install npm
  * Run the command “npm I –g meta”
* Setting up Meta repo
  * Create a new git repo and clone it
  * Run “meta init”
  * Add projects by running “meta project create [folder] [repo url]”
  * Run “meta git update” to clone all the repositories
  * Commit meta repo & push meta repo
* Run “meta git update” to clone all the repositories
* The git is a excellent version control system. It doesn't have a great ui. Without UI for git, the learning curve could be a bit high for developers. So solve this problem a git UI client such as SourceTree could be used.

