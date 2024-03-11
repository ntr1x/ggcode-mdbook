# About

GGCode is a template-based and framework agnostic source code generation tool. It is written in Rust and created by developers for developers. It is inspired by Terraform and Helm, but not limited to clouds and Kubernetes.

It is primarily a code and configuration generation tool, regardless of how you intend to utilize the resulting code and configurations. It is also a package manager that allow you to share your code and configurations between your projects and your community members. With GGCode, you can generate various elements such as your code, Kubernetes manifests, Compose descriptors, Ansible playbooks, Helm charts, etc. We use it to distribute and standardize our configuration patterns across tens of our projects.

GGCode is a CLI application written in Rust. It integrates the Roblox Luau scripting engine and the Tera template engine with numerous helpful extensions.

## Features

**1. YAML and Luau configs**

You can write your configs in YAML files or Luau scripts.

**2. Config trees**

You can organize your configurations by nesting them within directories. This way, all configurations will be merged into a configuration tree based on their file paths.

**3. Text-based and Script-based templates**

You can use both text-based and script-based templates together depending on your needs. Use Tera (a Jinja-like template engine) to generate code fragments, or Lua (specifically the Roblox Luau dialect) to generate structured configurations or complex output.

**4. Pre-defined templates**

You can find a lot of useful repositories to boost your productivity. With our repository collection you can Generate Java code, Maven artifacts, Compose and Kubernetes Manifests, etc.

**5. Pre-defined helpers**

Didn't find a suitable template package or need some overrides for an existing one? Not a big deal! Most of our repositories contain not only templates and configs but also Lua models and functions organized in libraries.

## Trivial example

This is a trivial example of how to bootstrap and configure PostgreSQL and pgAdmin with suitable defaults and some overrides:

#### Step 1

Add to your project `ggcode-info.yaml` file with this content:

```yaml
name: example
actions:
- name: generate
  path: actions/generate.luau
repositories:
- name: central
  uri: git@github.com:ntr1x/ggcode-repo-central.git
- name: compose
  uri: git@github.com:ntr1x/ggcode-repo-compose.git
targets:
- name: '@app'
  path: app
```

#### Step 2

Add an action script `actions/generate.luau` into your project:

```lua
local ggcode = require('ggcode')
local pg = require('compose/postgres')
local pgadmin = require('compose/pgadmin')
local keycloak = require('compose/keycloak')

local database_keycloak = {
  name = 'keycloak',
  username = 'keycloak',
  password = 'keycloak'
}

ggcode.generate 'compose/keycloak' {
  target = '@app',
  variables = {
    database = keycloak.database:from(database_keycloak)
  }
}

ggcode.generate 'compose/postgres' {
  target = '@app',
  variables = {
    databases = {
      pg.database:from(database_keycloak),
    }
  }
}

ggcode.generate 'compose/pgadmin' {
  target = '@app',
  variables = {
    servers = {
      pgadmin.server:from(database_keycloak),
    }
  }
}

ggcode.generate 'compose/compose' {
    target = '@app',
    variables = {
        config = {
            include = {
                { path = 'compose/env/env_postgres.compose.yaml' },
                { path = 'compose/env/env_pgadmin.compose.yaml' },
                { path = 'compose/env/env_keycloak.compose.yaml' },
            }
        }
    }
}
```

#### Step 3

Execute action to bootstrap your environment

```bash
# Install dependencies
ggcode install

# Generate compose manifests
ggcode run @/generate
```
