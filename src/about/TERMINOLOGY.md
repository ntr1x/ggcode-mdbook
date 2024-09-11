# Terminology

We conceptualize the application development process as a superposition of code and configuration blocks. Some of them are huge, and sometimes it is not so trivial to reproduce these blocks manually. In this case we roll them down in archives called `scrolls`. Later you can read and apply the content of these archives just like a fairy tale wizard reading spells from his magical scrolls.

Reading our documentation, you will encounter several concepts described in the list below.

## Thesaurus

### CLI

A Command Line Interface of a GGCode application. You can discover it using the `ggcode --help` command.

### Package

A directory containing a `ggcode-info.yaml` file that describes the contents of the directory for the GGCode application.

### Repository

A Git repository of a package. Each repository may become a dependency. Each dependant repository should be registered in `ggcode-info.yaml` file. You can manage the set of referenced repositories using the `ggcode repository` command.

### Target

The GGCode application may contain multiple generation targets. Each target should be registered in `ggcode-info.yaml` file. You can manage the set of targets using the `ggcode target` command. You will use target name running the `ggcode run` or `ggcode generate` commands.

### Action

The GGCode application may contain multiple declarations of entry points named "actions". Each action should be registered in `ggcode-info.yaml` file. You can manage the set of actions using the `ggcode action` command. You can execute an action using the `ggcode run` command.

### Scroll

We organize configurations and templates in sub-packages named *scrolls*. Each scroll is a directory with `templates/` and `variables/` sub-directories. Each scroll should be registered in `ggcode-info.yaml` file. You can manage the set of scrolls using the `ggcode scroll` command. You can execute a scroll using the `ggcode generate` command.

### Config

YAML or Luau file (with .yaml or .luau file extension) inside the `variables/` sub-directory of your scroll.

### Template

Tera or Luau file (with .tera or .luau file extension) inside the `templates/` sub-directory of your scroll.
