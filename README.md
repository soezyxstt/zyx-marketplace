# ZYX Tools Marketplace

Plugin marketplace/catalog for ZYX tooling across Claude Code and Codex-compatible hosts.

This repository is intentionally lightweight: it publishes marketplace metadata and points hosts to the upstream [`zyx-authoring-mcp`](https://github.com/soezyxstt/zyx-authoring-mcp) plugin. It does not contain or run the MCP server itself.

## Catalogs

- `.claude-plugin/marketplace.json` — Claude Code marketplace catalog
- `.agents/plugins/marketplace.json` — Codex-compatible marketplace catalog

The marketplace exposes production and staging variants of the Zyx Authoring plugin so changes can be validated before being promoted to production.

## Zyx Authoring plugin

The upstream plugin currently provides an end-to-end authoring pipeline plus four independently invocable specialist skills:

- `zyx-authoring-pipeline`
- `zyx-source-pack-mcp`
- `zyx-idea-bundle-mcp`
- `zyx-product-bundle-mcp`
- `zyx-question-authoring-mcp`

The remote MCP remains authoritative for authentication, workflow scope, validation, provenance, quality gates, staging, review, and supported lifecycle operations.

## Architecture

```text
Claude / Codex host
       │
       ▼
ZYX Tools Marketplace
       │
       ▼
zyx-authoring-mcp plugin
       │
       ▼
Remote Zyx Authoring MCP
```

This marketplace repository does **not** run application servers, databases, authentication services, or storage.

## Claude Code

Add this repository as a plugin marketplace, then install either the production or staging Zyx Authoring plugin from the catalog. Reload plugins after installation or marketplace updates.

## Codex-compatible hosts

Add the repository as a plugin marketplace and install the desired Zyx Authoring variant through the host's plugin browser or CLI workflow.

## Related repository

- [`soezyxstt/zyx-authoring-mcp`](https://github.com/soezyxstt/zyx-authoring-mcp) — plugin manifests, skills, and MCP client configuration
