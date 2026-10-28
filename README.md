# CallSync MCP

![CallSync](https://mcp.callsyncapp.com/assets/branding/logo-icon.png)

**Turn business calls into clear insights and timely follow-ups.**

CallSync brings your business calls and CRM follow-ups into your AI workspace. Find recent calls, look up a contact’s conversation history, review available transcripts and summaries, and open recording links when you need more context.

Keep the next step moving: add call notes, update contacts, create follow-up tasks, and record CRM activities through natural-language requests. Sales and support teams can use CallSync to prepare for the next conversation and keep customer context close at hand.

Connect your CallSync account to get started. Works with compatible remote MCP clients, including Claude, ChatGPT, and Cursor.

## What you can do

- Find recent business calls and filter by date, team member, direction, or review status.
- Look up a contact’s call history and keep conversation context at hand.
- Review available transcripts and summaries, and retrieve recording links.
- Add call notes and keep contact details up to date.
- Create and update CRM follow-up tasks and record customer activities.

## Connect

CallSync runs as a hosted remote MCP server. Use this URL in your compatible client's custom connector settings:

```
https://mcp.callsyncapp.com/connect
```

Transport: Streamable HTTP. Sign in to CallSync through OAuth and authorize your workspace.

[Connection guide](https://help.callsyncapp.com/connect-ai-agent/) · [CallSync website](https://callsyncapp.com/) · [Support](https://callsyncapp.com/contact/)

### Cursor

Add this remote server to your MCP configuration, then complete the CallSync sign-in:

```json
{
  "mcpServers": {
    "callsync": {
      "url": "https://mcp.callsyncapp.com/connect"
    }
  }
}
```

### VS Code

Add it to `.vscode/mcp.json`, then complete the CallSync sign-in:

```json
{
  "servers": {
    "callsync": {
      "type": "http",
      "url": "https://mcp.callsyncapp.com/connect"
    }
  }
}
```

### Agent skill (OpenClaw, Hermes Agent and other skill-based agents)

For agents that use skills rather than remote MCP servers, [`skills/callsync`](skills/callsync/SKILL.md) works with the CallSync REST API and a workspace API key in `CALLSYNC_API_KEY` (CallSync dashboard → **API & Apps**). It is also on [ClawHub](https://clawhub.ai) as **CallSync**. In Hermes Agent:

```bash
hermes skills install digiheadway/callsync-mcp/skills/callsync
```

## Example prompts

- Show my five most recent calls.
- Show the available transcript and summary for my latest recorded call.
- Show my open CRM follow-up tasks.

A CallSync account with access to a workspace is required. Recording insights are available for calls that have the corresponding recording or analysis in that workspace.

## Tools

The connector exposes 19 call, contact, account, and CRM tools. See `tools.json` for their current schemas and annotations.

[Official MCP Registry listing](https://registry.modelcontextprotocol.io/?q=com.callsyncapp%2Fcallsync)

## Policies

[Privacy policy](https://callsyncapp.com/privacy/) · [Terms of service](https://callsyncapp.com/terms/)

The license in this repository applies to its documentation and connection metadata. The hosted CallSync service is governed by its Terms of Service; CallSync branding remains the property of CallSync.
