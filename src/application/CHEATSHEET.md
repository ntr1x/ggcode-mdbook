# Cheat Sheet

## Get help

```bash
# Display help
ggcode --help
```

## Bootstrap project

```bash
# Init project (interactive)
ggcode init

# Install dependencies
ggcode install
```

## Generate smth.

```bash
# Getting help (it will also list available scrolls as a commands)
ggcode generate --help

# Getting help for inner scroll
ggcode generate @/scrolls/my-scroll --help

# Getting help for scroll from registered repository
ggcode generate docker/scrolls/haproxy --help

# Getting help for scroll from registered repository
ggcode generate docker/scrolls/haproxy install
```

## Manage repositories

```bash
# Getting help
ggcode repository --help

# List registered repositories
ggcode repository list

# Add a repository (interactive)
ggcode repository add

# Add a repository (one-liner)
ggcode repository add --name core --uri git@github.com:ntr1x/ggcode-repo-core.git

# Remove known repository (one-liner)
ggcode repository remove --name core

# Do not forget to refresh deps at the end
ggcode install
```

## Manage targets

```bash
# Getting help
ggcode target --help

# List registered targets
ggcode target list

# Add a target (interactive)
ggcode target add

# Add a target (one-liner)
ggcode target add --name @ --path relative/path/to/target

# Remove known target (one-liner)
ggcode target remove --name @
```

## Manage scrolls

```bash
# Getting help
ggcode scroll --help

# List registered scrolls
ggcode scroll list

# Add a scroll (interactive)
ggcode scroll add

# Add a scroll (one-liner)
ggcode scroll add --name @ --path relative/path/to/target

# Remove known target (one-liner)
ggcode scroll remove --name @
```
