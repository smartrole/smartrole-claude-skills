---
name: "setup-smart-role-connector"
description: "Guide the user through connecting the Smart Role MCP connector so the other skills in this plugin can create and manage personas, soft skills, scorecards, scenarios, and training paths"
---

This skill only applies when the user wants to use the other skills in this plugin (creating virtual customers, soft skills, or scenarios) and the Smart Role MCP tools are not yet available in the conversation.

Check whether Smart Role MCP tools are already available before doing anything else. If they are, skip this skill entirely and proceed with the user's request.

If the Smart Role MCP tools are not available, tell the user they need to connect Smart Role first. Smart Role is added as a custom connector, using this exact endpoint URL: `https://app.smartrole.ai/api/mcp`. Give them the steps for the app they are using:

- In Claude (web or desktop): open Settings, then Connectors, choose "Add custom connector", name it Smart Role, paste the endpoint URL, and click Connect. Claude opens a Smart Role sign-in page: they sign in to their Smart Role workspace and approve the access. On a Team or Enterprise plan, an owner may need to add the custom connector for the organization first.
- In Claude Code: run `claude mcp add --transport http smart-role https://app.smartrole.ai/api/mcp`, then run `/mcp` and choose Smart Role to sign in and approve the access.

Mention that the connection only sees the Smart Role workspace they approve, with their permissions in it. More details are on the MCP page of their Smart Role settings (https://app.smartrole.ai/settings/mcp).

Once the user confirms the connector is connected, or once Smart Role MCP tools appear in the available tools, proceed with their original request using the other skills in this plugin.

Do not attempt to call any Smart Role MCP tool before confirming it is available. Do not use any URL other than the endpoint above, and never ask for, guess, or handle access tokens, API keys, or passwords on the user's behalf.
