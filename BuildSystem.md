# Build System (CI)

The system is in place to create binaries that are used for releases and testing.

## Vision

### Setup friendly
Dev team being the major customer, this system is designed to enable the developers. When a new repository is created, the developers have to configure the build system for it. The build system is so designed, that the developer should be able to get the build system up for a new repository with in 10 minutes

### Consumption friendly
When the build system produces artifacts such as folder or zip files, it not evident for the operation team how these artifacts need to used. On the other hand, when the build system produces artifacts such as maven, nuget, npm, docker or helm artificats, it's extremely clear for the operations team (or the dev team) on how to consume them. To facilitate easy consumption of the build artifacts, the build system shall produce standard artifacts such as maven, nuget, npm, docker or helm artifacts.


