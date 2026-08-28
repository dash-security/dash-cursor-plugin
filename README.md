# Dash Security

Dash secures the full agentic estate across discovery, posture, runtime detection, and governance. The Dash plugin connects the Cursor agents to the **Dash MCP** and includes skills that turn your Dash Security data into first-class agent workflows: discover your AI estate, assess supply-chain and shadow AI risk, investigate agent sessions, and track AI spend and usage.

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
| `agentic-estate-discovery`    | Discover every agent, harness, platform, extension, MCP, skill, hook and plugin installed and running in your environment. Observe all AI activity and usage trends, uncovering who is using agents and what they are using them for. |
| `supply-chain-risk`           | Surface the risky tools used by agents in your organization. Scan MCP servers, skills, plugins, and hooks to reveal their capabilities, access, and suspicious behavior. Get an evidence-backed risk assessment and blast radius for each one.                                |
| `shadow-ai-risk`              | Uncover the agentic platforms in use across your organization, on the endpoint and in the browser. Get a full registry of every shadow platform accessed or installed, attributed to specific users and devices, including users authenticating to AI platforms with personal or private identities.                                      |
| `agent-session-investigation` | Investigate agent sessions and security detections in depth. Review the full reconstructed agent flow - from user intent and agent reasoning, to tool calls, commands, and file access.       |
| `ai-spend`                    | Understand how AI is being used and what it is costing your organization. Analyze spend, token consumption, model usage, and adoption trends across teams, platforms, and users to identify top consumers, high-cost activity, and optimization opportunities.              |

Each skill orchestrates the Dash MCP tools. The agent selects a skill automatically from your request, or you can name one explicitly.

## Requirements

- A Dash Security account with access to the developer API.
- Cursor with plugin/MCP support.

## License

MIT
