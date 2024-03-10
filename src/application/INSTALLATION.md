# Installing GGCode

**Source Code**

[GGCode Tool on a GitHub](https://github.com/ntr1x/ggcode-app)

**Download Links**

[GGCode for GNU/Linux on x86_64](../_distributions/linux_x86_64/ggcode)

## Installing from binaries

You can download and install `ggcode` tool from binaries. It is a pretty tiny application (~15 MB).

### On Linux x64:

```bash
# Download
curl -O http://ntr1x.github.io/ggcode-mdbook/_distributions/linux_x86_64/ggcode

# Grant appropriate permissions
chmod 775 ggcode

# Move to your bin directory
sudo mv ggcode /usr/local/bin
```

## Installing using Cargo

```bash
cargo install --git https://github.com/ntr1x/ggcode-app.git
```

## Building from source code

### On Linux

```bash
# Clone GGCode repository:
git clone git@github.com:ntr1x/ggcode-app.git
cd ./ggcode-app

# Build using cargo:
cargo build --release

# Make a simbolic link:
ln -s $(realpath ./target/release/ggcode) ~/.local/bin/ggcode
```

## Post installation steps

It is also recommended to generate and install autocomplete files for your shell.

### On Ubuntu Linux:

```bash
# Generate and install bash autocomplete file:
BASH_COMPLETION_TARGET_DIR=${BASH_COMPLETION_USER_DIR:-${XDG_DATA_HOME:-$HOME/.local/share}/bash-completion}/completions
mkdirp ${BASH_COMPLETION_TARGET_DIR}/completions
ggcode completions --generator bash >> ${BASH_COMPLETION_TARGET_DIR}/completions/ggcode.bash

# Restart your terminal session
exec bash
```
