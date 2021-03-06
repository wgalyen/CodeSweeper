# 0.4

- Remove all options and subcommands to re-focus the intent of Kondo
- Default is now interactive mode, allowing users to choose options on a per-project basis
- Update `druid` dependency to 0.6, this means we no longer rely on `cairo` on MacOS

# 0.3

- Add basic graphic user interface
- Rewrite project discovery phase for a massive 97.5% runtime reduction. This includes a correctness fix, projects within the artifacts of other projects will not be listed and therefore will not be included more than once in the size total (previously they were).
- Break project into cargo workspace
- Improve path handling, skip folders that don't exist
- Add Unreal 4 project support 

# 0.2

- Added Haskell Stack project support
- Added Github actions for testing, linting, and deployment
- Added SBT project support
- Add command line options
  - Support passing multiple paths to scan
  - Support outputting just a list of artifact directories, this list is usually used to pipe into another program to delete
  - Support running a command for each artifact directory
- Add Maven project support