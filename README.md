# Note

App is in review process, it will be released here for free

https://apps.apple.com/app/apple-store/id6746345658

# Task Management MCP Server

[![Auto Release](https://github.com/Aayush9029/mcp-server/actions/workflows/auto-release.yml/badge.svg)](https://github.com/Aayush9029/mcp-server/actions/workflows/auto-release.yml)
[![pages-build-deployment](https://github.com/Aayush9029/mcp-server/actions/workflows/pages/pages-build-deployment/badge.svg)](https://github.com/Aayush9029/mcp-server/actions/workflows/pages/pages-build-deployment)
[![PyPI version](https://badge.fury.io/py/mcp-server.svg)](https://badge.fury.io/py/mcp-server)
[![Python](https://img.shields.io/badge/python-3.8%2B-blue.svg)](https://www.python.org/downloads/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

![mcp](https://github.com/user-attachments/assets/d8810bcc-d5a0-40ba-b57d-af19b9045322)

## Task Management MCP Server

Bridge AI assistants with real-world task management

This MCP server connects Claude Desktop, Cursor, and other AI tools to a powerful task management API, enabling intelligent workflows that create, update, and track tasks automatically on your iPhone.

### What You Can Do

- Ask Claude to create tasks during coding sessions
- Let Cursor update task status as it completes work
- Get notifications on your iPhone when AI assistants finish tasks
- Track progress across multiple AI tools and automation scripts
- Manage priorities with AI-suggested urgency levels

Perfect for developers who want their AI assistants to collaborate on real projects with automatic task tracking and mobile notifications.

## Quick Start

### 1. Get Your API Key

Download the iOS app [here](https://apps.apple.com/app/apple-store/id6746345658)

### 2. Choose Your Setup

#### For Claude Desktop (Recommended)

Add this to `~/Library/Application Support/Claude/claude_desktop_config.json`:

```json
{
  "mcpServers": {
    "task-manager": {
      "command": "npx",
      "args": [
        "mcp-remote",
        "https://task-mcp-server.aayushpokharel9029.workers.dev/sse?apiKey=YOUR_API_KEY"
      ]
    }
  }
}
```

#### For Cursor or Other MCP Clients

```json
{
  "mcpServers": {
    "task-manager": {
      "url": "https://task-mcp-server.aayushpokharel9029.workers.dev/sse?apiKey=YOUR_API_KEY"
    }
  }
}
```

Replace `YOUR_API_KEY` with your actual API key.

### 3. Start Using It

Once configured, your AI assistant can:

- "Create a high-priority task to review the pull request"
- "Show me all pending tasks"
- "Mark the deployment task as completed"
- "Update the bug fix to urgent priority"

## Available Tools

The server provides these capabilities to AI assistants:

### `create_task`
Create new tasks with title, description, priority, and notification settings.

### `list_tasks`
View all tasks with optional filtering by status, priority, or date.

### `get_task`
Get detailed information about any specific task.

### `update_task`
Modify task properties including status, priority, and description.

### `delete_task`
Remove completed or cancelled tasks.

## Technical Details

- **REST API Server**: [Endpoint: https://mcpclient.lovedoingthings.com/docs](https://mcpclient.lovedoingthings.com/docs)
- **Authentication**: API key via `X-API-Key` header
- **Supported Priorities**: LOW, MEDIUM, HIGH, URGENT
- **Supported Statuses**: TODO, IN_PROGRESS, DONE, CANCELLED

## Security & Privacy

- **API Key Isolation**: Each key maintains completely separate task data
- **No Cross-Access**: Tasks are never shared between different API keys
- **Secure Communication**: All requests require authentication headers
- **Real-time Updates**: Changes sync instantly to your iPhone app

## Need Help?

If your AI assistant isn't connecting:

1. Check that your API key is correctly formatted
2. Verify the configuration file location
3. Restart your MCP client after configuration changes

For issues or feature requests, visit the [GitHub repository](https://github.com/Aayush9029/mcp-server).

---

Built by **Aayush Pokharel**  
GitHub: [@Aayush9029](https://github.com/Aayush9029) • Twitter: [@aayushbuilds](https://twitter.com/aayushbuilds)