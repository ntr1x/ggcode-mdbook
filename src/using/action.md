# Manage actions

`Action` is a runnable entry point inside GGCode package. All actions are written in Luau. You can manage the set of scrolls using the `ggcode scroll` command.

## Table of contents

- [Getting help](#getting-help)
- [Listing actions](#listing-actions)
- [Adding action](#adding-action)
- [Removing action](#removing-action)

## Getting help

```bash
$ ggcode action --help

Manage set of runnable actions

Usage: ggcode action [COMMAND]

Commands:
  list    List runnable actions
  add     Add an action
  remove  Remove a runnable action
  help    Print this message or the help of the given subcommand(s)

Options:
  -h, --help  Print help
```

## Listing actions

```bash
$ ggcode action list

┌───┬────────┬───────────────────┐
│ # │ Name   │ Path              │
├───┼────────┼───────────────────┤
│ 1 │ @/run  │ actions/run.luau  │
├───┼────────┼───────────────────┤
│ 2 │ @/test │ actions/test.luau │
└───┴────────┴───────────────────┘
```

## Adding action

##### Option 1, Interactive mode

Adding action in interactive mode:

```bash
ggcode action add

✔ Name of the runnable action · test
✔ Relative inner path to the runnable action file · actions/test

[SUCCESS] Bye for now.
```

##### Option 2, Non-interactive mode

Adding action by specifying options as command parameters:

```bash
$ ggcode action add \
  --name test \
  --path actions/test

[SUCCESS] Ciao.
```

## Removing action

##### Option 1, Interactive mode

```bash
$ ggcode action remove

✔ Name of the runnable action: · test

[SUCCESS] Take care.
```

##### Option 2, Non-interactive mode

```bash
$ ggcode action remove --name test

[SUCCESS] Bye for now.
```
