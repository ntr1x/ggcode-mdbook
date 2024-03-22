# Run action

As you've read before: actions are Luau scripts. You can run an action using `ggcode run` command. If executed without agruments, it will list the set of registered actions.

## Listing actions

Run this command without arguments to list registered actions:

```bash
$ ggcode run
Run command

Usage: ggcode run [COMMAND]

Commands:
  @/generate-compose  Run generate-compose action
  @/generate-spring   Run generate-spring action
  help                Print this message or the help of the given subcommand(s)

Options:
  -h, --help  Print help
```

## Executing action

Specify command (action) name as an argument to run registered action.

```bash
$ ggcode run @/generate-compose
[SUCCESS] Bye for now.
```

## Getting help

### Display help about `run` command itself

```bash
$ ggcode run

Run command

Usage: ggcode run [COMMAND]

Commands:
  @/record  Run record action
  help      Print this message or the help of the given subcommand(s)

Options:
  -h, --help  Print help
```

### Display help for the concrete action

```bash
$ ggcode run @/record --help

Run record action

Usage: ggcode run @/record

Options:
  -h, --help  Print help
```
