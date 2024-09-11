# About

GGCode is a configuration distribution manager and a code generation tool. With this tool you can generate a source code, Kubernetes manifests, Compose descriptors, Ansible playbooks, Helm charts, etc. We use it to distribute our coding and configuration patterns across our projects.

GGCode is a CLI application written in Rust. It integrates the Roblox Luau scripting engine and the Tera template engine with numerous helpful extensions.

## Features

**1. Package manager**

You can build and distribute your configurations and templates as packages.

**2. Config trees**

You can organize your configurations by nesting them within directories. This way, all configurations will be merged into a configuration tree based on their file paths.

**3. Text-based and Script-based templates**

You can use both text-based and script-based templates together depending on your needs. Use Tera (a Jinja-like template engine) to generate code fragments, or Lua (specifically the Roblox Luau dialect) to generate structured configurations or complex output.

**4. Pre-defined templates**

You can find a lot of useful repositories to boost your productivity. With our repository collection you can Generate Java code, Maven artifacts, Compose and Kubernetes Manifests, etc.

**5. Pre-defined helpers**

Didn't find a suitable template package or need some overrides for an existing one? Not a big deal! Most of our repositories contain not only templates and configs but also Lua models and functions organized in libraries.

**6. Numerous configuration formats**

You can write your configs in YAML, JSON or Luau scripts.

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
- name: core
  uri: git@github.com:ntr1x/ggcode-repo-core.git
- name: compose
  uri: git@github.com:ntr1x/ggcode-repo-compose.git
targets:
- name: '@app'
  path: app
```

#### Step 2

Add an action script `actions/generate.luau` into your project:

```lua
local ggcode = require("core/ggcode")
local Project = require('core/Project')
local Postgres = require('compose/Postgres')
local Pgadmin = require('compose/Pgadmin')
local Keycloak = require('compose/Keycloak')

local project = Project:from('starter')

local datasource_keycloak = {
  uri = 'jdbc:postgresql://env-postgres:5432/keycloak',
  username = 'keycloak',
  password = 'keycloak'
}

ggcode.generate "compose/compose" {
  target = '@app',
  variables = {
    project = project:unwrap_project(),
    config = {
      include = {
        { path = "compose/env/env-postgres.compose.yaml" },
        { path = "compose/env/env-pgadmin.compose.yaml" },
        { path = "compose/env/env-keycloak.compose.yaml" },
      }
    }
  }
}

ggcode.generate "compose/postgres" {
  target = '@app',
  variables = Postgres
    :from(project)
    :with_rules({
      Postgres.Database:from_datasource(datasource_keycloak),
    })
    :unwrap()
}

ggcode.generate "compose/pgadmin" {
  target = '@app',
  variables = Pgadmin
    :from(project)
    :with_rules({
      Pgadmin.Server:from_datasource(datasource_keycloak),
    })
    :unwrap()
}

ggcode.generate "compose/keycloak" {
  target = '@app',
  variables = Keycloak
    :from(project, datasource_keycloak)
    :unwrap()
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

## Other examples

### Online Store

This example demonstrates how to use GGCode Spring, Compose, and Core repositories together. Use it to bootstrap a local environment with Postgres, PGAdmin, Kafka, KafkaUI, and HaProxy, along with a multi-module Spring Boot project featuring Product Catalog, Customer Database, Customer Basket, and specialized Payments microservices.

[Developing Online Store](./guide/store.md)
