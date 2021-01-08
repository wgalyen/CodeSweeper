# CodeSweeper 🧹

Cleans unneeded directories and files from your system.

It will identify the disk space savings you would get from deleting temporary/unnecessary files from project directories, such as `target` from Cargo projects and `node_modules` from Node projects. Currently `codesweeper` doesn't actually delete any files.

Supports:

- Cargo projects
- Node projects
- Unity Projects
- Haskell Stack projects

## Roadmap

- Actually delete (with prompt)
- Handle Unity cache, editor cache

## Operation

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