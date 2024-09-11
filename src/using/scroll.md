# Manage scrolls

`Scroll` is a sub-package with a set of templates and default variables inside. You can manage the set of scrolls using the `ggcode scroll` command.

## Table of contents

- [Getting help](#getting-help)
- [Listing scrolls](#listing-scrolls)
- [Adding scroll](#adding-scroll)
- [Removing scroll](#removing-scroll)

## Getting help

```bash
$ ggcode scroll --help

Manage set of scrolls

Usage: ggcode scroll [COMMAND]

Commands:
  list    List scrolls
  add     Add a scroll
  remove  Remove a scroll
  help    Print this message or the help of the given subcommand(s)

Options:
  -h, --help  Print help
```

## Listing scrolls

```bash
$ ggcode scroll list

┌────┬────────────────────┬─────────┬────────────────────┐
│ #  │ Alias              │ Package │ Path               │
├────┼────────────────────┼─────────┼────────────────────┤
│ 1  │ @/readme           │ example │ scrolls/readme     │
├────┼────────────────────┼─────────┼────────────────────┤
│ 2  │ compose/compose    │ compose │ scrolls/compose    │
├────┼────────────────────┼─────────┼────────────────────┤
│ 3  │ compose/haproxy    │ compose │ scrolls/haproxy    │
├────┼────────────────────┼─────────┼────────────────────┤
│ 4  │ compose/kafka      │ compose │ scrolls/kafka      │
├────┼────────────────────┼─────────┼────────────────────┤
│ 5  │ compose/kafka_ui   │ compose │ scrolls/kafka_ui   │
├────┼────────────────────┼─────────┼────────────────────┤
│ 6  │ compose/pgadmin    │ compose │ scrolls/pgadmin    │
├────┼────────────────────┼─────────┼────────────────────┤
│ 7  │ compose/postgres   │ compose │ scrolls/postgres   │
├────┼────────────────────┼─────────┼────────────────────┤
│ 8  │ compose/swagger_ui │ compose │ scrolls/swagger_ui │
├────┼────────────────────┼─────────┼────────────────────┤
│ 9  │ spring/module_web  │ spring  │ scrolls/module_web │
├────┼────────────────────┼─────────┼────────────────────┤
│ 10 │ spring/project     │ spring  │ scrolls/project    │
├────┼────────────────────┼─────────┼────────────────────┤
│ 11 │ spring/unit        │ spring  │ scrolls/unit       │
├────┼────────────────────┼─────────┼────────────────────┤
│ 12 │ spring/unit_ref    │ spring  │ scrolls/unit_ref   │
└────┴────────────────────┴─────────┴────────────────────┘
```

## Adding scroll

##### Option 1, Interactive mode

Adding scroll in interactive mode:

```bash
$ ggcode scroll add

✔ Name of the scroll: · readme
✔ Relative inner path to the scroll directory: · scrolls/readme

[SUCCESS] Keep in touch.
```

##### Option 2, Non-interactive mode

Adding scroll by specifying options as command parameters:

```bash
$ ggcode scroll add \
  --name readme \
  --path scrolls/readme

[SUCCESS] Ciao.
```

## Removing scroll

##### Option 1, Interactive mode

```bash
$ ggcode scroll remove

✔ Name of the scroll to remove: · readme
✔ Remove also a scroll directory? · yes

[SUCCESS] Have a nice day!
```

##### Option 2, Non-interactive mode

```bash
# Keep scroll directory
$ ggcode scroll remove --name readme

[SUCCESS] Keep in touch.

# Also remove scroll directory
$ ggcode scroll remove --name readme --force

[SUCCESS] Take care.
```
