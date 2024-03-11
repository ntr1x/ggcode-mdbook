# Manage repositories

You can manage dependencies using `ggcode repository` command.

## Table of contents

- [Listing repositories](#listing-repositories)
- [Adding repository](#adding-repository)
- [Removing repository](#removing-repository)
- [Getting help](#getting-help)

## Listing repositories

```bash
$ ggcode repository list

┌───┬─────────┬──────────────────────────────────────────────┐
│ # │ Name    │ URI                                          │
├───┼─────────┼──────────────────────────────────────────────┤
│ 1 │ central │ git@github.com:ntr1x/ggcode-repo-central.git │
└───┴─────────┴──────────────────────────────────────────────┘
```

## Adding repository

#### Step 1

Add a repository:

##### Option 1, Interactive mode

Adding repository in interactive mode:

```bash
# Initialize project
$ ggcode repository add
✔ Name of the repository: · compose
✔ URI of the repository: · git@github.com:ntr1x/ggcode-repo-compose.git
[SUCCESS] Good seeing you!
```

##### Option 2, Non-interactive mode

Add reposuitory by specifying options as command parameters:

```bash
ggcode repository add \
  --name compose \
  --uri git@github.com:ntr1x/ggcode-repo-compose.git
```

#### Step 2

Install new repository using `ggcode install` command:

```bash
$ ggcode install

▪▪▪▪▪ [DONE] Repository `git@github.com:ntr1x/ggcode-repo-central.git` cloned into the `ggcode_modules/central` directory.
▪▪▪▪▪ [DONE] Repository `git@github.com:ntr1x/ggcode-repo-compose.git` cloned into the `ggcode_modules/compose` directory.
[SUCCESS] Have a nice day!
```

## Removing repository

##### Option 1, Interactive mode

```bash
ggcode repository remove
✔ Name of the repository: · compose
[SUCCESS] Have fun!
```

##### Option 2, Non-interactive mode

```bash
ggcode repository remove --name compose
[SUCCESS] Have a nice day!
```

## Getting help

```bash
$ ggcode init --help

{{#include ../_bash_output/ggcode__repository__--help.txt}}
```