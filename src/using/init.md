# Initialize project

You can initialize or update GGCode project using `ggcode init` command. This command will create a file named `ggcode-info.yaml` in the root of your project.

## Instructions

#### Step 1

```bash
# Make and enter project directory
$ mkdir example
$ cd example
```

#### Step 2

##### Option 1, Interactive mode

Initialize project by specifying options in interactive mode:

```bash
# Initialize project
$ ggcode init
✔ The name of your project · example
✔ Should we add central repository? · yes
✔ Should we add more repositories? · no
✔ Should we register working directory as `@` target? · yes
✔ Should we add more targets? · no
[SUCCESS] Take care.
```

#### Step 2

##### Option 2, Non-interactive mode

Initialize project by specifying options as command parameters:

```bash
ggcode init \
  --name example \
  --repository central:git@github.com:ntr1x/ggcode-repo-central.git \
  --target @:.
```

## Getting help

```bash
$ ggcode init --help

{{#include ../_bash_output/ggcode__init__--help.txt}}
```