# CodeSweeper 🧹

![CodeSweeper Lints](https://github.com/wgalyen/codesweeper/workflows/CodeSweeper%20Lints/badge.svg)

Cleans unneeded directories and files from your system.

It will identify the disk space savings you would get from deleting temporary/unnecessary files from project directories, such as `target` from Cargo projects and `node_modules` from Node projects.

Supports:

- [Cargo](https://doc.rust-lang.org/cargo/) projects
- [Node](https://nodejs.org/) projects
- [Unity](https://unity.com/) Projects
- [SBT](https://www.scala-sbt.org/) projects
- [Haskell Stack](https://docs.haskellstack.org/) projects
- [Maven](https://maven.apache.org/) projects
- [Unreal Engine](https://www.unrealengine.com/) projects

## Installation

### Graphic User Interface

Windows and Mac builds are available on the [Releases](https://github.com/wgalyen/codesweeper/releases) page.

### Command line

Windows, Mac, and Linux builds are available on the [Releases](https://github.com/wgalyen/codesweeper/releases) page.

## Operation

### Graphic User Interface

Launch `codesweeper-ui`, select a directory to be scanned, evaluate & clean directories as needed.

### Command Line Interface

Running `codesweeper` without a directory specified will run in the current directory.

```
$ codesweeper
```

Supplying a path will tell `codesweeper` where to start. Multiple paths are supported..

```
$ codesweeper code/my_project code/my_project_2
```

## Example Output

```
$ codesweeper ~/code
/Users/warren/code/unity Cargo project
  └─ target (489.1KiB)
  delete above artifact directories? ([y]es, [n]o, [a]ll, [q]uit): y
  deleted 489.1KiB

/Users/warren/code/multiplayer-kit/generator Cargo project
  └─ target (874.3KiB)
  delete above artifact directories? ([y]es, [n]o, [a]ll, [q]uit): n

/Users/warren/code/chat Cargo project
  └─ target (37.2MiB)
  delete above artifact directories? ([y]es, [n]o, [a]ll, [q]uit): q

Total bytes deleted: 489.1KiB
```

## Building/Development

To build `codesweeper` you can run `cargo build` from the projects root directory.

To build `codesweeper-ui` you must first navigate into the `codesweeper-ui` directory, then you can run `cargo build`. Because we use [druid](https://github.com/xi-editor/druid) for the interface you'll need to satisfy druid's [platform specific dependencies](https://github.com/xi-editor/druid#platform-notes).