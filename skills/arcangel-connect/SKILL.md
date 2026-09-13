---
name: arcangel-connect
description: >
  Connect Arcangel and use the hosted MCP to list the user's patents and
  trademarks or draft IP matters. Use when the user asks to connect Arcangel,
  work on their Arcangel patents or trademarks, or list Arcangel IP.
---

# Connect Arcangel

When the user asks to connect Arcangel or work on their Arcangel patents or trademarks, use the Arcangel MCP tools on the hosted server. Do not reimplement the Arcangel API.

## When to use

- The user asks to connect Arcangel
- The user wants to list, review, or draft Arcangel patents or trademarks
- A previous Arcangel MCP call failed because the bot is unauthorized

## Instructions

1. Call the Arcangel MCP tools from this plugin. The server is Streamable HTTP at `https://www.arcangel.ai/api/mcp`. Auth is `Authorization: Bearer` with `ARCANGEL_BOT_TOKEN`.
2. If the tools are missing, return unauthorized, HTTP 401, or a missing-token error, guide the user to [https://www.arcangel.ai/connect-bot](https://www.arcangel.ai/connect-bot). They can Sign in with Arcangel, or create a token under Settings, Connect a Grok Bot, then set `ARCANGEL_BOT_TOKEN` on this plugin (Plugins, Configure).
3. After the token is set, retry the MCP tools. A working first request is: list my Arcangel patents.
4. Stay within read and draft. The bot can list account patents and trademarks, and can create or edit drafts if draft write was allowed. It cannot pay, checkout, spend Halo Tokens, or file or submit to the USPTO.

## Limits

- Read plus draft only
- No pay, checkout, or Halo Token spend
- No USPTO filing or submission
