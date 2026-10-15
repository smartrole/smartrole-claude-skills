# Smart Role Roleplay Skills

This plugin gives Claude a consistent, Smart Role approved way to build the content that powers roleplay training in [Smart Role](https://smartrole.ai): virtual customer personas, soft skills, and scenarios.

It is meant to be used alongside the Smart Role MCP connector, which gives Claude the tools to actually create and manage this content in your Smart Role workspace. The connector and this plugin are separate. The connector provides the tools. This plugin tells Claude how to use them well.

## What is in this plugin

**setup-smart-role-connector**
Checks whether the Smart Role connector is already connected, and if not, walks the user through adding it as a custom connector (`https://app.smartrole.ai/api/mcp`, with a Smart Role sign-in) before attempting anything else.

**create-smart-role-virtual-customer**
Defines how Claude should write a virtual customer persona: user name, description, behavior, age, email, and phone, in that order, as dense prose rather than bullet points.

**create-smart-role-soft-skills**
Defines how Claude should write a soft skill used to evaluate agent performance: name, description, and factors, with factors framed as evaluation questions.

**generate-smart-role-scenario**
Defines how Claude should write a roleplay scenario: name, description, a detailed default prompt for the AI to execute, and context information for the trainee. Context must only supply facts, never instructions.

## Why this exists

Without these skills, Claude can still call the Smart Role MCP tools directly, since the tools themselves enforce their required fields. What varies without this plugin is depth and consistency: how much detail goes into a persona's behavior, whether context accidentally turns into instructions, whether soft skill factors are phrased as checkable questions. This plugin removes that variance so every Smart Role customer gets the same quality bar when they ask Claude to build training content.

## Usage

Once the Smart Role connector is connected and this plugin is enabled, just ask Claude to create a virtual customer, a soft skill, a scorecard, or a scenario in natural language. Claude will follow the field order and format defined in the relevant skill before calling the Smart Role MCP tools.

## License

MIT, see LICENSE.
