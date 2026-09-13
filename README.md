# Arcangel Cursor plugin

Connect Cursor or Grok to the live Arcangel MCP so friends can list patents and trademarks and draft IP matters. This plugin points at the hosted API. It does not reimplement it.

## Install

Marketplace listing is pending review. After it is published, install **Arcangel** from the Cursor Marketplace, set your bot token, and ask the agent to connect Arcangel.

### Test locally

1. Copy or symlink this repo to `~/.cursor/plugins/local/arcangel`:

   ```bash
   mkdir -p ~/.cursor/plugins/local
   ln -s /path/to/arcangel-cursor-plugin ~/.cursor/plugins/local/arcangel
   ```

2. Reload the Cursor window (`Developer: Reload Window`).
3. Open Customize and confirm the Arcangel plugin, skill, and MCP server loaded.

## Set your token

1. Open [https://www.arcangel.ai/connect-bot](https://www.arcangel.ai/connect-bot).
2. Sign in with Arcangel, or create a token under Settings, Connect a Grok Bot.
3. In Cursor, set `ARCANGEL_BOT_TOKEN` on the plugin (Plugins, Configure).

The token starts with `arcb_`. It authorizes read and draft only. It cannot pay or file.

## Try it

Ask: `list my Arcangel patents`

The agent should use the hosted MCP at `https://www.arcangel.ai/api/mcp`.

## Hosted endpoints

| What | URL |
| --- | --- |
| MCP (Streamable HTTP) | `https://www.arcangel.ai/api/mcp` |
| Auth | `Authorization: Bearer <arcb_… bot token>` |
| User docs | [https://www.arcangel.ai/connect-bot](https://www.arcangel.ai/connect-bot) |
| OAuth discovery | `https://www.arcangel.ai/.well-known/oauth-authorization-server` |

## What a bot can and cannot do

**Can:** read the account, patents, and trademarks; create and edit drafts if draft write is enabled.

**Cannot:** pay, checkout, or spend Halo Tokens; file or submit to the USPTO.

## Publish

Submit this repository at [https://cursor.com/marketplace/publish](https://cursor.com/marketplace/publish).

## License

MIT. See [LICENSE](LICENSE).
