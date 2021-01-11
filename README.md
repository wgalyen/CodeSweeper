# CodeSweeper 🧹

![CodeSweeper Tests](https://github.com/wgalyen/codesweeper/workflows/CodeSweeper%20Tests/badge.svg) ![CodeSweeper Lints](https://github.com/wgalyen/codesweeper/workflows/CodeSweeper%20Lints/badge.svg)

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

Supplying an argument will tell `codesweeper` where to start.

```
$ codesweeper code/my_project
```

## Example Output

```
$ codesweeper ~
Scanning "C:/Users/Warren"
3 projects found
Calculating savings per project
  (redacted 1000~ lines)
  385.6MB UnityTestApp (Unity) C:\Users\Warren\code\UnityTestApp
  458.7MB tokio (Cargo) C:\Users\Warren\code\tokio
    1.5GB ui-testing (Node) C:\Users\Warren\code\ui-testing
    4.0GB rust-analyzer (Cargo) C:\Users\Warren\code\rust-analyzer
9.5GB possible savings
```

## Options/Flags

### Artifact Dirs

`codesweeper -a` will output a line-separated list of artifact directories you can delete to reclaim space.

```
$ codesweeper test_dir -a
C:\Users\Warren\code\codesweeper\test_dir\node_project\node_modules
C:\Users\Warren\code\codesweeper\test_dir\rust_project\target
C:\Users\Warren\code\codesweeper\test_dir\health-dots\Temp
C:\Users\Warren\code\codesweeper\test_dir\health-dots\Obj
C:\Users\Warren\code\codesweeper\test_dir\health-dots\MemoryCaptures
C:\Users\Warren\code\codesweeper\test_dir\health-dots\Build
```

### Command

`codesweeper -c <COMMAND>` will run your supplied command for each artifact directory.

```
$ codesweeper test_dir -c echo
C:\Users\Warren\code\codesweeper\test_dir\node_project\node_modules
C:\Users\Warren\code\codesweeper\test_dir\rust_project\target
C:\Users\Warren\code\codesweeper\test_dir\health-dots\Temp
C:\Users\Warren\code\codesweeper\test_dir\health-dots\Obj
C:\Users\Warren\code\codesweeper\test_dir\health-dots\MemoryCaptures
C:\Users\Warren\code\codesweeper\test_dir\health-dots\Build
```

## Building/Development

To build `codesweeper` you can run `cargo build` from the projects root directory.

To build `codesweeper-ui` you must first navigate into the `codesweeper-ui` directory, then you can run `cargo build`. Because we use [druid](https://github.com/xi-editor/druid) for the interface you'll need to satisfy druid's [platform specific dependencies](https://github.com/xi-editor/druid#platform-notes).