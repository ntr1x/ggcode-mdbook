# Generate

You can test registered scroll using `ggcode generate` command. If executed without agruments, it will list the set of registered scrolls.

<div class="warning">

**Rare used**

This command allows you to `test` your scroll. It is a useful instrument for package makers. If you just an adopter, better use `ggcode run` command.

</div>

## Listing scrolls

Run generate command without arguments to list registered scrolls:

```bash
$ ggcode generate
Execute generation script from scroll

Usage: ggcode generate [COMMAND]

Commands:
  compose/compose     Casting a magical spell
  compose/haproxy     Casting a magical spell
  compose/kafka       Casting a magical spell
  compose/kafka_ui    Casting a magical spell
  compose/keycloak    Casting a magical spell
  compose/pgadmin     Casting a magical spell
  compose/postgres    Casting a magical spell
  compose/swagger_ui  Casting a magical spell
  spring/module_web   Casting a magical spell
  spring/project      Casting a magical spell
  spring/unit         Casting a magical spell
  spring/unit_ref     Casting a magical spell
  help                Print this message or the help of the given subcommand(s)

Options:
  -h, --help  Print help
```

## Executing scroll

Specify scroll name as an argument to run generation process.

```bash
# Generate files and place them into the registered `target`
$ ggcode generate @/scripts -t @target
[SUCCESS] Take care.

# Generate files and place them into the specified directory
$ ggcode generate @/scripts -p /tmp
[SUCCESS] Ciao.
```

## Getting help

### Display help about `generate` command itself

```bash
$ ggcode run --help
Run command

Usage: ggcode run [COMMAND]

Commands:
  @/record  Run record action
  help      Print this message or the help of the given subcommand(s)

Options:
  -h, --help  Print help
```

### Display help for the concrete scroll

```bash
ggcode generate @/scripts --help
Builds bash scripts

Usage: ggcode generate @/scripts [OPTIONS]

Options:
  -v, --variables <path>  Path to a file or directory containing variable overrides
  -d, --dry-run           Do not generate files; simply test the ability to render templates
  -h, --help              Print help

Target Options:
  -t, --target <target>  The name of a well-known target

Target:
  -p, --target-path <target-path>  The path to output directory
```
