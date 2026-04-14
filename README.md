# UmbHost.GreenStack.Umbraco.UmBootstrap (v13)

A dotnet new template for Umbraco 13 LTS with UmBootstrap preconfigured for [GreenStack](https://umbhost.net/sustainable-cloud-hosting/modern-umbraco-hosting) hosting.

> This is the **v13 LTS** branch of the template, which targets Umbraco 13 (the long-term support release). For the latest Umbraco version, install the template without a version constraint.

## Installation

```bash
dotnet new install UmbHost.GreenStack.Umbraco.UmBootstrap::13.*
```

## Usage

```bash
dotnet new greenstack-umbraco-umbootstrap -n MyProject
```

This creates a new Umbraco 13 LTS project with [UmBootstrap](https://marketplace.umbraco.com/package/umbraco.community.templates.umbootstrap) and:

- Forwarded headers middleware for Traefik proxy
- HTTPS runtime validator removed (SSL terminated by GreenStack)
- Data protection keys persisted to `/app/keys` in production
- Multi-stage Dockerfile exposing port 8080
- Docker launch profile (HTTP)

## Getting started

Follow the [Getting Started with Umbraco on GreenStack](https://umbhost.net/gb/blog/2026/01/getting-started-with-umbraco-17-on-greenstack-with-github) guide (concepts apply to Umbraco 13 LTS as well).

## Source

The template content comes from [GreenStack.Umbraco.UmBootstrap-v13](https://github.com/UmbHost/GreenStack.Umbraco.UmBootstrap-v13), which is also available as a GitHub template repository.

## GreenStack

- [Purchase GreenStack hosting](https://umbhost.net/sustainable-cloud-hosting/modern-umbraco-hosting)
- [GreenStack documentation](https://my.umbhost.net/knowledgebase/17/GreenStack)
- [GreenStack CI/CD samples](https://github.com/UmbHost/GreenStack.CICD.Samples)

## License

MIT
