# Manage targets

`Target` is a place where the results of code generation will be located. You can manage the set of targets using the `ggcode target` command.

## Table of contents

- [Getting help](#getting-help)
- [Listing targets](#listing-targets)
- [Adding target](#adding-target)
- [Removing target](#removing-target)

## Getting help

```bash
$ ggcode target --help

Manage set of targets

Usage: ggcode target [COMMAND]

Commands:
  add     Add a target
  remove  Remove a target
  list    List targets
  help    Print this message or the help of the given subcommand(s)

Options:
  -h, --help  Print help
```

## Listing targets

```bash
$ ggcode target list

┌───┬───────────┬──────────┐
│ # │ Name      │ Path     │
├───┼───────────┼──────────┤
│ 1 │ @         │ .        │
├───┼───────────┼──────────┤
│ 2 │ @examples │ examples │
└───┴───────────┴──────────┘
```

## Adding target

##### Option 1, Interactive mode

Adding target in interactive mode:

```bash
$ ggcode target add

✔ Name of the target: · @target
✔ Path to the target: · generation/results

[SUCCESS] Have fun!
```

##### Option 2, Non-interactive mode

Add target by specifying options as command parameters:

```bash
$ ggcode target add \
  --name @target \
  --path generation/results

[SUCCESS] Have fun!
```

## Removing target

##### Option 1, Interactive mode

```bash
$ ggcode target remove

✔ Name of the target: · @target

[SUCCESS] Good seeing you!
```

##### Option 2, Non-interactive mode

```bash
$ ggcode target remove --name @target

[SUCCESS] Bye for now.
```
