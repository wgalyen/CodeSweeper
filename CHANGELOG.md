# 0.3

- Add basic graphic user interface
- Rewrite project discovery phase for a massive 97.5% runtime reduction. This includes a correctness fix, projects within the artifacts of other projects will not be listed and therefore will not be included more than once in the size total (previously they were).
- Break project into cargo workspace
- Improve path handling, skip folders that don't exist

# 0.2

- Added Haskell Stack project support
- Added Github actions for testing, linting, and deployment
- Added SBT project support
- Add command line options
  - Support passing multiple paths to scan
  - Support outputting just a list of artifact directories, this list is usually used to pipe into another program to delete
  - Support running a command for each artifact directory
- Add Maven project support