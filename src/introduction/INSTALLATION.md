# Installing GGCode

## From source codes

### On Ubuntu Linux, using bash

```bash
# Clone GGCode repository:
git clone git@github.com:ntr1x/ggcode-app.git
cd ./ggcode-app

# Build using cargo:
cargo build --release

# Make a simbolic link:
ln -s $(realpath ./target/release/ggcode) ~/.local/bin/ggcode

# Generate and install bash autocomplete file:
BASH_COMPLETION_TARGET_DIR=${BASH_COMPLETION_USER_DIR:-${XDG_DATA_HOME:-$HOME/.local/share}/bash-completion}/completions
mkdirp ${BASH_COMPLETION_TARGET_DIR}/completions
ggcode autocomplete --generator bash >> ${BASH_COMPLETION_TARGET_DIR}/completions/ggcode.bash

# Restart your terminal session
exec bash
```
