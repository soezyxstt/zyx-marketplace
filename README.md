# ZYX Tools Marketplace

Plugin catalog for ZYX tooling across Claude Code and Codex-compatible hosts.

This repository publishes marketplace metadata for Zyx authoring and visual content plugins. It does not run an MCP server.

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

## Content design plugin

[Zyx Content Design](https://github.com/soezyxstt/zyx-content-design) provides four skills:

- `zyx-content-pipeline`
- `zyx-content-brief`
- `zyx-visual-design`
- `zyx-design-review`

It bundles a shared brand design system, 108 assets, fonts, React components, and local render/review tools. The plugin uses its own Zyx logo icon and requires no MCP server or API key. Local rendering requires Python and Chromium.

The source repository is public. This marketplace contains metadata and points hosts to the plugin source.

Claude Code installation:

```text
/plugin marketplace add soezyxstt/zyx-marketplace
/plugin install zyx-content-design@zyx-tools
```

In a Codex-compatible host, add this marketplace and select **Zyx Content Design**. Installation UI depends on the host version.
