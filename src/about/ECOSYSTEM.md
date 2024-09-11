# Ecosystem

As you know, GGCode is not only an application but also a package manager and distribution system. You can find a lot of awesome packages and examples here:

## Examples

### Online Store

This example demonstrates how to use GGCode Spring, Compose, and Core repositories together. Use it to bootstrap a local environment with Postgres, PGAdmin, Kafka, KafkaUI, and HaProxy, along with a multi-module Spring Boot project featuring Product Catalog, Customer Database, Customer Basket, and specialized Payments microservices.

Read the step-by-step guide here:

[Developing Online Store](../guide/store.md)

Find the source code here:

[Online Store Example on GitHub](https://github.com/ntr1x/ggcode-example-store)

## Repositories

### GGCode Core

It is the place where our standard library is located. Use it as a dependency in your projects.

Find the source code here:

[Core Library on GitHub](https://github.com/ntr1x/ggcode-repo-core)

### GGCode Compose

A collection of scrolls with docker compose manifests. It contains a DSL that will help you to bootstrap databases, message brokers, monitoring tools, proxies in a few rows. Use it as a dependency if you need to generate Docker Compose artifacts.

Find the source code here:

[Compose Library on GitHub](https://github.com/ntr1x/ggcode-repo-compose)

### GGCode Spring

A collection of scripts and a DSL to bootstrap a Spring Boot application with WebMVC, Kafka, and JPA support. It can generate Maven artifacts, controllers, services, repositories, entities, models, and converters from a single declaration named Unit. Use it as a dependency if you need to generate Spring Boot applicaitons.

Find the source code here:

[Spring Library on GitHub](https://github.com/ntr1x/ggcode-repo-spring)

### GGCode Vue

A collection of scripts and a DSL to bootstrap a CRM application implemented in Vue 3 and Typescript.

Find the source code here:

[Vue Library on GitHub](https://github.com/ntr1x/ggcode-repo-vue)

### GGCode Migrate

A collection of scripts and a DSL to bootstrap a Liquibase change set.

Find the source code here:

[Vue Library on GitHub](https://github.com/ntr1x/ggcode-repo-migrate)
