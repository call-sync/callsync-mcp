# Installing the CallSync MCP server

CallSync is a hosted remote MCP server. There is nothing to clone, build or run locally: add its URL to your MCP settings and sign in.

## Steps

1. Add this server to the MCP settings file (for Cline, `cline_mcp_settings.json`):

   ```json
   {
     "mcpServers": {
       "callsync": {
         "type": "streamableHttp",
         "url": "https://mcp.callsyncapp.com/connect"
       }
     }
   }
   ```

2. Save the file. On the first connection the client opens a browser window: the user signs in to CallSync and authorizes their workspace (OAuth). Do not ask the user for a password in chat.

3. Check the connection by listing the tools: CallSync exposes 19 tools for calls, contacts, recordings, team activity and CRM follow-ups. A quick test is to ask for the five most recent calls.

## If the client cannot do OAuth

The server also accepts a CallSync workspace API key as a Bearer token. The workspace owner copies it from the [CallSync dashboard](https://dash.callsyncapp.com) under **API & Apps**. Ask the user to paste it into the settings file themselves, rather than into chat:

```json
{
  "mcpServers": {
    "callsync": {
      "type": "streamableHttp",
      "url": "https://mcp.callsyncapp.com/connect",
      "headers": { "Authorization": "Bearer <CallSync API key>" }
    }
  }
}
```

## Troubleshooting

- **401 Unauthorized:** the sign-in was not completed, the key is wrong, or integrations are off for the workspace in an active plan. Remove the server and add it again to restart sign-in.
- **No calls returned:** calls appear once a team member's Android phone has synced them with the CallSync app.

More help: https://help.callsyncapp.com/connect-ai-agent/
