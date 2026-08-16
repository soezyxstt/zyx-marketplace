# ZYX Tools Marketplace

Repository ini adalah marketplace/catalog untuk Claude Code dan ChatGPT/Codex. Marketplace ini mendaftarkan plugin ZYX yang dapat ditemukan dan dipasang melalui host masing-masing.

Katalog Claude Code berada di `.claude-plugin/marketplace.json`. Katalog native Codex berada di `.agents/plugins/marketplace.json`. Keduanya menunjuk ke repository plugin upstream yang sama; repository ini tetap hanya berisi katalog.

## Plugin

Plugin sebenarnya berada di repository [zyx-authoring-mcp](https://github.com/soezyxstt/zyx-authoring-mcp). Repository plugin upstream menyediakan manifest Claude Code dan Codex. Repository marketplace ini tidak mengubah, menyalin, atau menjalankan source plugin.

Plugin menyediakan tiga skill:

- `zyx-source-pack-mcp`
- `zyx-idea-bundle-mcp`
- `zyx-product-bundle-mcp`

Marketplace ini tidak menjalankan server, database, autentikasi, storage, atau MCP HTTP server. Server MCP plugin tetap berjalan pada endpoint remote staging yang dikonfigurasi oleh plugin. Autentikasi plugin menggunakan session OAuth atau connection token sementara.

## Instalasi melalui Claude Code

Ganti `<MARKETPLACE_REPO_URL>` dengan URL atau sumber repository marketplace ini setelah repository baru dibuat.

Di dalam Claude Code, jalankan:

```text
/plugin marketplace add <MARKETPLACE_REPO_URL>
/plugin install zyx-authoring-mcp@zyx-tools
/reload-plugins
```

Atau gunakan CLI Claude Code:

```text
claude plugin marketplace add <MARKETPLACE_REPO_URL>
claude plugin install zyx-authoring-mcp@zyx-tools
```

## Instalasi melalui ChatGPT/Codex

Ganti `<MARKETPLACE_REPO_URL>` dengan URL atau sumber repository marketplace ini setelah repository baru dibuat.

Untuk Codex CLI, tambahkan marketplace lalu buka plugin browser:

```text
codex plugin marketplace add <MARKETPLACE_REPO_URL>
codex
```

Di dalam Codex, jalankan:

```text
/plugins
```

Untuk ChatGPT Desktop, buka Plugins Directory, pilih marketplace `ZYX Tools`, lalu instal `zyx-authoring-mcp`. Setelah instalasi, mulai chat atau sesi Codex baru agar skill dan MCP tools plugin dimuat.

## Skill plugin

Setelah terpasang di Claude Code, skill plugin dapat digunakan dengan namespace plugin masing-masing:

```text
/zyx-authoring-mcp:zyx-source-pack-mcp
/zyx-authoring-mcp:zyx-idea-bundle-mcp
/zyx-authoring-mcp:zyx-product-bundle-mcp
```

Di ChatGPT/Codex, plugin dapat dipilih dari plugin browser atau skill selector sesuai host yang digunakan.
