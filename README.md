# ZYX Tools Marketplace

Plugin catalog for ZYX tooling across Claude Code and Codex-compatible hosts.

This repository only publishes marketplace metadata and points hosts to [`zyx-authoring-mcp`](https://github.com/soezyxstt/zyx-authoring-mcp). It does not run the MCP server.

## Catalogs

- `.claude-plugin/marketplace.json`: Claude Code catalog
- `.agents/plugins/marketplace.json`: Codex-compatible catalog

Production and staging variants are available so plugin changes can be tested before promotion.

## Authoring plugin

The upstream plugin provides:

- `zyx-authoring-pipeline`
- `zyx-source-pack-mcp`
- `zyx-idea-bundle-mcp`
- `zyx-product-bundle-mcp`
- `zyx-question-authoring-mcp`

## Architecture

```text
Claude / Codex host
       │
       ▼
ZYX Tools Marketplace
       │
       ▼
zyx-authoring-mcp
       │
       ▼
Remote Zyx Authoring MCP
```

Related repository: [`soezyxstt/zyx-authoring-mcp`](https://github.com/soezyxstt/zyx-authoring-mcp)
