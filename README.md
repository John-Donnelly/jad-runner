# JAD Runner

The desktop companion for [jadapps.app](https://jadapps.app) — runs the platform's file tools **entirely on your machine**, with local HTTP + MCP endpoints for scripts and AI agents.

**File contents and filenames never leave your machine.** The runner reports only usage statistics (counts, bytes, durations, outcomes) — this is enforced in code and by tests, not policy.

## Download

Grab the latest Windows installer or portable exe from [Releases](https://github.com/John-Donnelly/jad-runner/releases).

> **Note:** current builds are unsigned (code-signing certificates are in progress) — Windows SmartScreen will warn on first run. Choose "More info" → "Run anyway" if you trust the source.

## What it does

- Runs 550+ of the platform's tools locally: images, PDF, audio, video, Excel, archives, 3D, SVG, markdown, security tools and more
- Pairs with your jadapps.app account for orchestrator dispatch and encrypted tool bundles
- Exposes `http://127.0.0.1:9789` (HTTP API) and an MCP server so Claude Desktop, Cursor, and your scripts can drive the same tools
- Full GUI: drag-and-drop tool runner, jobs history, usage meter, webhooks, and a telemetry pane showing exactly what left the machine

## MCP quick start (Windows)

```json
{
  "mcpServers": {
    "jad-runner": {
      "command": "node",
      "args": ["C:\\Program Files\\JAD Runner\\resources\\bin\\mcp-stdio-bridge.cjs"]
    }
  }
}
```

Start JAD Runner first (it serves on launch), then restart your MCP client.

## Source

The runner is developed inside the JAD Apps platform monorepo. This repository hosts release artifacts and documentation.

---
A [JAD Apps](https://jadapps.app) product.
