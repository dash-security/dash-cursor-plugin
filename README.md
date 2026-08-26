# Dash Security

Agentic security for Cursor. The Dash plugin connects the agent to the **Dash MCP** and ships five skills that turn your Dash Security data into first-class agent workflows: discover your AI estate, assess supply-chain and shadow AI risk, investigate agent sessions, and track AI spend - all from chat.

## Install

1. Open **Cursor Settings -> Plugins**.
2. Search for **Dash Security**.
3. Click **Install**, then complete the Dash sign-in prompt.

Or run `/add-plugin dash` in chat.

## MCP

```json
{
  "mcpServers": {
    "dash": {
      "type": "http",
      "url": "https://mcp.dash.security/mcp"
    }
  }
}
```

Auth is OAuth 2.0 against Dash. Cursor prompts for Dash sign-in when the plugin connects - no token needs to be placed in the client config. If your account belongs to multiple Dash tenants, the agent will ask which tenant to use (via the MCP `list_tenants` tool).

## Skills

| Skill                         | Use it for                                                                                                                                 |
| ----------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------ |
| `agentic-estate-discovery`    | Front-door overview of the whole agentic environment: platforms, devices, users, MCP servers, managed vs shadow, and what needs attention. |
| `supply-chain-risk`           | Trust, provenance, and integrity of the MCP servers, tools, connectors, and packages your agents depend on.                                |
| `shadow-ai-risk`              | Find and govern unsanctioned, unmanaged, or out-of-policy AI usage and the governance gap it creates.                                      |
| `agent-session-investigation` | Depth-first dive on one runtime session or detection: timeline, intent drift, data exposure, blast radius, and an incident write-up.       |
| `ai-spend`                    | AI cost and consumption metrics - spend, token usage, model mix, trends - org-wide or scoped to a user, group, or department.              |

Each skill orchestrates the Dash MCP tools; the agent selects a skill automatically from your request, or you can name one explicitly.

## Requirements

- A Dash Security account with access to the customer API.
- Cursor with plugin/MCP support.

## License

MIT
