# GEN for Gemini CLI

GEN is the auto-content engine for ads, cartoons, AI UGC, and microdramas, with a free video editor. It researches what’s working, makes the video, and posts it over MCP.

This extension connects Gemini CLI to GEN’s hosted MCP server at https://mcp.gen.pro.

## Install and sign in

```bash
gemini extensions install https://github.com/poweredbyGEN/gen-gemini-extension
```

Then run `/mcp auth gen` in Gemini CLI and sign in through OAuth.

## Personal Access Token (PAT)

For a headless client, define the same `gen` server in `~/.gemini/settings.json`. A settings server of the same name takes precedence over the extension:

```json
{
  "mcpServers": {
    "gen": {
      "httpUrl": "https://mcp.gen.pro",
      "headers": { "Authorization": "Bearer $GEN_PAT" }
    }
  }
}
```

Set `GEN_PAT` securely in the client's environment. Gemini CLI expands it when connecting. GEN also accepts `X-API-Key` where a client cannot set `Authorization`.

AI agents can register their own account and receive a PAT. Follow the [official skill](https://gen.pro/skill.md) for registration and workflows, or read the [AI agents documentation](https://gen.pro/docs#ai-agents).

This repository distributes the hosted connection configuration from GEN’s canonical MCP source. Source release: `6979f72146dc3db9488f1ec3f5450902b440804b` (Gitea PR316). The manifest was validated with Gemini CLI 0.62.0, including a real PAT connection and tool discovery.
