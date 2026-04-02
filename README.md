# WordPress AI Agent Bridge (Claude Code + MCP)

This repository serves as the local environment for an AI-driven WordPress development workflow. It uses the **Model Context Protocol (MCP)** to allow a Claude AI Agent to interact directly with a live WordPress server for theme development, ACF configuration, and Elementor layout generation.

---

## 🚀 How It Works
Instead of manual coding, we connect **Claude Code** (an agentic CLI) to the WordPress **REST API** using an MCP Server plugin. This allows the AI to:
1. **Read/Write Files:** Edit your theme's PHP, CSS, and JS directly on the live server.
2. **Manage Content:** Create pages and posts via natural language prompts.
3. **Handle ACF Pro:** Generate templates based on your custom field groups.
4. **Elementor Integration:** Push JSON layouts directly into the Elementor builder.

---

## 🛠️ Required Tools

### 1. The WordPress "Bridge" (Plugin)
You must install an MCP-compatible plugin on your live site to act as the server.
* **Recommended Plugin:** [AI Engine by Meow Apps](https://wordpress.org/plugins/ai-engine/) (2026 Version)
* **Alternative:** [MCP Adapter for WordPress](https://github.com/InstaWP/mcp-wp)

### 2. The AI Agent (Claude)
* **Tool:** [Claude Code CLI](https://claude.ai/download) or the **Claude Dev VS Code Extension**.
* **Connection Protocol:** MCP (Model Context Protocol).

---

## 💰 Free vs. Paid (2026 Pricing)

| Component | Free Tier | Paid Tier (Recommended) |
| :--- | :--- | :--- |
| **Claude AI** | **Web Chat Only.** (No Agentic CLI access, must copy-paste code manually). | **Claude Pro ($20/mo):** Required for the terminal agent and VS Code integration. |
| **WordPress Plugin** | **Basic MCP Server.** Can read/write simple posts and pages. | **Pro Version ($29+/yr):** Required for advanced ACF, WooCommerce, and Theme file editing. |
| **API Costs** | **$5 Free Credits** for new Anthropic accounts (good for testing). | **Pay-as-you-go:** Usually costs <$1 per complex development session. |

---

## 🔌 Integration Steps

1. **In WordPress:**
   - Install **AI Engine**.
   - Go to `Settings > MCP` and enable the **MCP Server**.
   - Generate a **Bearer Token** or a **WordPress Application Password** (Users > Profile).

2. **In your Terminal / VS Code:**
   - Install Claude Code: `npm install -g @anthropic-ai/claude-code`
   - Run the connection command:
   ```bash
   claude mcp add wp-live --transport http --env WP_API_URL="[https://yourdomain.com/wp-json/mcp/v1](https://yourdomain.com/wp-json/mcp/v1)" --header "Authorization: Bearer YOUR_TOKEN"
