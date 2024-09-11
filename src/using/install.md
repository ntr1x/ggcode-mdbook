# Install dependencies

You can install the dependencies using the `ggcode install` command. This command will retrieve the list of repositories from the `ggcode-info.yaml` file and then fetch these repositories and their dependencies recursively.

It will also create the `ggcode_modules` directory at the root of your project. This is where all the dependencies will be located.

You will have to call `ggcode install` sometimes.

## Instructions

```bash
$ ggcode install

▪▪▪▪▪ [DONE] Repository `git@github.com:ntr1x/ggcode-repo-core.git` cloned into the `ggcode_modules/core` directory.

[SUCCESS] Have a nice day!
```

## Getting help

```bash
$ ggcode install --help

Recursively fetches dependent repositories

Usage: ggcode install

Options:
  -h, --help  Print help
```