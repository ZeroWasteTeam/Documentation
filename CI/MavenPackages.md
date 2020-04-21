# Publishing and Consuming Maven Packages

With the help of git hub packages. It would be easy to publish and consume maven packages. [JitPack](https://jitpack.io/) would be another way to do this. At this point JitPack is not explored enough. In this document, we will stick with Github packages. There are couple of ways we could do this with GitHub packages.

## Stratergies

### Organization Wide Maven Repository
* It would be ideal if there is an organization with Maven repository
* All publishing repositories could publish the to the organization wide maven repository
* All consumer could consume fromthe organiation wide maven repository
* Unfortunately GitHub doesn't support this at this point of time. It would be good, it git hub start supporting this

### One Code Repository with Maven Repository in the organizaiton.
* We could create a code repository with maven repository
* All publishing repositories could publish the aritfact to this repository
* All consuming repositories could consume the artifacts from this repositories
* This model looks perfect at first. On exploring the problems are 
  * To publish the artifact, a token it needed. Github action provides a token for the initiating user by default. With this token it is not possible to publish to another repository. To workaround this we might need to create a secret user name and token that could do this. In that case we also need create a github user for this.

### Maven Repository Per Code repository
* we could easily have a maven repository per code repository
* The code when build publishes to this repository
* The consuming application should list all the repositories from where they are consuming packages. This is less than ideal and is verbose.

## Decision
* In zero waste team, we will adopt maven repository per code repository model
* It would be better than creating a new user to publish maven packages
* One more thing to be noted is there can no two packages with the same groupId and artifactId in the same organization even if they are in separate maven repositories.
