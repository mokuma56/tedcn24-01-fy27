# Agent Builder — Getting Started Guide

**Version:** 0.4 Draft  |  **Author:** Unknown  |  **Date:** 2026-07-18  |  **Difficulty:** Intermediate  |  **Duration:** 60 min

**Tags:** agent-builder, cisco, ai-canvas, mcp, integrations, automation, cloud-control, studio

## Prerequisites

- Cisco SSO credentials and access to your Cloud Control tenant
- Admin Console access within your tenant
- API credentials for the third-party tools you want to connect (see Appendix A)

## Introduction

Agent Builder is Cisco's platform for connecting third-party tools to AI Canvas and building autonomous agents that run on a schedule. This guide walks through setup, connecting integrations, and building agents.

## Learning Objectives

- Navigate to Agent Builder via the Cloud Control Studio interface
- Configure third-party integrations (ServiceNow, Atlassian, Infoblox, BlueCat) in Admin Console
- Verify integration connections and use them in AI Canvas with natural language queries
- Create an autonomous agent with a profile, trigger, and cadence
- Test an agent using the Test tab before promoting to production
- Promote, monitor, and manage agent versions in production

## Navigating to Agent Builder

Access the Agent Builder platform through the Cloud Control Studio interface.

### Step 1: Log in to Cloud Control

Log in to Cloud Control at cloud.cisco.com.

```
cloud.cisco.com
```

> **Expected Result:** You are logged in to the Cloud Control portal.

### Step 2: Open the nine-dots menu

Click the nine-dots menu in the top header.

> **Expected Result:** The application menu expands.

### Step 3: Navigate to Studio

Under Platform Services, click Studio. If Studio is not immediately visible in the menu, click Show more to expand the full list of platform services and then click Studio.

> **Expected Result:** The Agent Builder Overview page opens. The top navigation bar shows four tabs: Overview, Integrations, Agent Builder, and Observability. On a fresh setup, the Overview page shows two calls to action: Browse Integrations and Create an Agent. It also shows three summary cards — agents currently running, total active agents, and number of connected integrations — along with a Recent Agent Activity section and a Connected Integrations section.

## Section 1: Third-Party Integrations

Connect third-party tools such as ServiceNow, Atlassian, Infoblox, and BlueCat to Agent Builder via MCP-backed integrations.

### Step 1: Browse the Integration Catalog

Click the Integrations tab. You will see a tile catalog with one tile per available MCP server. Each tile shows the vendor name, product description, and either a + Configure button (not yet connected) or a ✓ Configured checkmark (already connected) in the bottom right corner.

> **Expected Result:** The Integrations catalog is visible showing available MCP server tiles.

### Step 2: Open the Configure Integration flow

Click + Configure on a tile. This cross-launches you into the Integrations section of the Admin Console, where you can enter and save the credentials required to connect that integration. You can also navigate to the Admin Console Integrations page directly: click the nine-dots menu → Admin Console (listed under Platform Services; click Show more if it is not immediately visible) → Integrations.

> **Expected Result:** The Admin Console Integrations page is displayed showing the list of configured integrations.

### Step 3: Create a new integration

Click + Create Integration in the top right. In the pop-up, click the Integration Name drop-down and select the integration you want to set up. After selecting an integration, additional fields appear specific to that vendor. Enter your credentials. See Appendix A for what each vendor requires and where to find those values.

> **Expected Result:** The Create Integration form shows vendor-specific fields such as Host URL and API Token.

!!! note
    Only one active credential entry is supported per integration — to update credentials, edit the existing entry. Each user configures their own credentials. Repeat this process for every integration you want to connect.

### Step 4: Save the integration

Click Save.

> **Expected Result:** The integration appears in the table on the Admin Console Integrations page with the name and date created. You can Edit or Delete it from that table.

### Step 5: Verify the connection

Return to the Integrations tab in Studio. Each integration you configured will now show a ✓ Configured checkmark instead of + Configure.

> **Expected Result:** Configured integrations display a ✓ Configured checkmark on their tiles.

### Step 6: Use integrations in AI Canvas

Go to AI Canvas and enter a natural language query. Canvas routes the query to the appropriate integration based on context. What you can ask depends on which tools that vendor's MCP server exposes. Canvas fetches the relevant data and returns a structured result. See Appendix B for the full tool list per integration.

```
Fetch details for ServiceNow ticket INC0012345
```

```
Show me all open P1 incidents in ServiceNow
```

```
What are the open Jira issues in the NETOPS project?
```

```
Check DHCP utilization for the 10.150.28.0/24 subnet
```

> **Expected Result:** Canvas displays fetched data such as ticket details including summary, timestamps, and assignment information.

## Section 2: Agent Builder — Creating an Agent

Build an autonomous agent by defining its profile, trigger, and cadence, then promote it to production.

### Step 1: Verify integrations before creating an agent

Before creating an agent, verify that all integrations the agent will need are already configured. Cisco product tools (Meraki, ThousandEyes, Catalyst SD-WAN, etc.) are available by default — no setup required. Third-party integrations (ServiceNow, Atlassian, Infoblox, BlueCat, etc.) must be configured in Admin Console before you can use them in an agent. See Section 1 for setup steps.

> **Expected Result:** All required integrations show ✓ Configured in the Integrations tab.

### Step 2: Start agent creation

Click the Agent Builder tab. If no agents have been created yet, you will see a Create Agent call to action in the center of the page, along with a + Create Agent button in the top right. Click either to start the agent creation flow. Agent creation has three steps: Agent Profile → Triggers → Review.

> **Expected Result:** The agent creation flow opens at Step 1: Agent Profile.

### Step 3: Step 1 — Complete the Agent Profile

Fill in the required Agent Profile fields including agent name, description, and instructions. Tips for writing good instructions: be specific about what data to pull and from which source; specify the output format (e.g., a table with specific columns); include thresholds or conditions to flag (e.g., 'flag any incident not updated in the last 4 hours'). Once the required fields are filled in, click Continue.

```
flag any incident not updated in the last 4 hours
```

> **Expected Result:** The Agent Profile form is completed and you advance to Step 2: Triggers.

### Step 4: Step 2 — Configure Triggers

Select a Trigger Mode from the drop-down. Currently, only Ambient mode is available. Set the Activation Cadence to determine how often the agent runs. Enter a Trigger Prompt — the specific request the agent executes on each run. The Instructions from Step 1 define how the agent behaves; the trigger prompt is the specific request it executes on each run. Keep it concise. Click Continue when done. You can click Back at any point to return to the previous step.

```
Fetch and summarize the current status of the incidents.
```

> **Expected Result:** The Triggers form shows Ambient mode selected, an activation cadence, and a trigger prompt entered.

### Step 5: Step 3 — Review and Create Agent

The Review page shows a summary of everything you configured — agent name, description, trigger mode, activation schedule, and trigger prompt. Verify the details look correct, then click Create Agent.

> **Expected Result:** Studio runs a series of automated steps: Validating inputs, Selecting tools, AI Defense reviewing, Building manifest, Validating configuration, Generating agent package, Saving configuration, Opening launch setup. Once complete, a confirmation page shows the agent name, description, and a summary of its configuration including status, version, trigger type, and AI Defense protection. Two buttons are available: View Agent and Test Agent.

!!! note
    The automated steps typically take one to a few minutes. Tool selection automatically identifies and scopes the MCP tools this agent needs based on its instructions and integrations — the agent only has access to tools relevant to its job, which improves accuracy, reduces token usage, and makes it faster. In a future release, you will be able to see and modify this tool scope directly.

## Section 2.2: Testing Your Agent

Use the Test tab to verify the agent responds correctly before promoting it to production.

### Step 1: Open the Test tab

From the agent confirmation page, click Test Agent, or navigate to the Test tab on the agent detail page.

> **Expected Result:** The Test tab opens showing pre-canned prompt options and a live test chat interface.

### Step 2: Run pre-canned prompts or enter a custom prompt

Pre-canned prompts at the top let you run common checks with a single click: 'Summarize configuration' (agent summarizes its own setup), 'Explain guardrails' (agent describes its safety constraints), 'Run readiness check' (agent confirms it can reach its configured integrations and tools). You can also type anything directly into the prompt box. A good starting point is to enter the trigger prompt you configured and verify the agent returns the expected output.

For each pre-canned prompt, use the following criteria to determine whether the test passed:
- Summarize configuration: The agent returns a plain-language summary that includes the agent name, its stated purpose or instructions, the trigger mode (Ambient), and the activation cadence. If any of these are missing or incorrect, the test has failed — revisit the Agent Profile and Triggers steps.
- Explain guardrails: The agent returns a description of its AI Defense constraints, such as content policies or scope restrictions. An acceptable response names at least one specific guardrail. A generic or empty response indicates a configuration problem.
- Run readiness check: The agent explicitly confirms it can reach each configured integration and tool. A passing response lists each integration by name with a reachable or connected status. Any integration reported as unreachable or unavailable is a failure — return to Section 1 to verify that integration's credentials.

When entering your trigger prompt as a custom test, a passing response must: (1) return data from the correct integration or tool, (2) follow the output format specified in your agent instructions (e.g., a table with the columns you defined), and (3) apply any conditions or thresholds you specified (e.g., flagging incidents not updated in the last 4 hours). If the response is empty, returns an error, pulls data from the wrong source, or ignores your formatting or threshold instructions, the test has failed — review your trigger prompt and agent instructions before promoting to production.

```
Summarize configuration
```

```
Explain guardrails
```

```
Run readiness check
```

> **Expected Result:** Each pre-canned prompt returns a substantive, accurate response as described above. The trigger prompt entered as a custom test returns data from the correct integration in the format and with the conditions specified in the agent instructions. All tests must pass before the agent is promoted to production.

## Section 2.3: Managing Your Agent

Promote, monitor, update, and manage agent versions using the agent detail page tabs.

### Step 1: Promote an agent to production

In the Configurations tab, find the Release History table. On the V1 row, click Promote to production under Actions. A confirmation pop-up will appear. Review the details, then click Promote to production to confirm, or Cancel to go back.

> **Expected Result:** The version is promoted instantly. A confirmation banner appears and the version badge in the Release History table updates to Production. The agent will now begin running on the schedule you configured.

!!! note
    When an agent is first created, it starts as Version 1 in Candidate state, visible in the Release History table on the Configurations tab.

### Step 2: Monitor and manage a production agent

Once in production, you can: update the config by editing the agent's profile or instructions to create a new version, test it, and promote it when ready; monitor runs by checking the Run tab to see execution history, outputs, and any errors; update the trigger by going to the Trigger tab to change the cadence or trigger prompt; roll back by promoting any previously published version from the Release History table; or delete the agent by removing it entirely from the agent detail page if it is no longer needed.

> **Expected Result:** Agent management actions are reflected in the respective tabs and the Release History table.

!!! note
    The agent detail page has four tabs for management.

## Section 2.4: Observability

Review ambient agent run outputs via the Notifications pane in Cloud Control.

### Step 1: View agent run output from Notifications

Each time an ambient agent completes a run, its output appears in the Notifications pane in the Cloud Control header — one notification per run. To view results: click the notifications icon in the Cloud Control header, find the notification for the run you want to review and click on it. The full output produced by that run will be displayed. Use the Download option to export the output if needed.

> **Expected Result:** The full output for the selected agent run is displayed in the Notifications pane.

## Appendix A: Vendor Setup Instructions

Credential requirements for each supported third-party integration.

### Step 1: ServiceNow CMDB credentials

Configure the following fields in Admin Console for ServiceNow CMDB:
- Host URL: https://your-instance.service-now.com
- API Token: your-api-token

How to obtain: To be added.

```
Host URL: https://your-instance.service-now.com
```

```
API Token: your-api-token
```

> **Expected Result:** ServiceNow CMDB integration is saved in Admin Console.

### Step 2: ServiceNow ITSM credentials

Configure the following fields in Admin Console for ServiceNow ITSM:
- Host URL: https://your-instance.service-now.com
- Client ID: your-oauth-client-id
- Client Secret: your-oauth-client-secret

ServiceNow ITSM uses OAuth 2.0. You will need oauth_admin, mi_admin, or admin role in your ServiceNow instance.
1. In ServiceNow, navigate to All → Machine Identity Console → Inbound integrations.
2. Create a new integration, select OAuth - Authorization code grant, and set Token Format to JWT under Advanced Options.
3. Provide the redirect URL shown in the Admin Console integration form.
4. Complete the OAuth flow using a dedicated integration user account created for this purpose.

Requirement: ServiceNow Zurich or later with a Now Assist SKU and Now Assist for ITSM installed.

```
Host URL: https://your-instance.service-now.com
```

```
Client ID: your-oauth-client-id
```

```
Client Secret: your-oauth-client-secret
```

> **Expected Result:** ServiceNow ITSM integration is saved in Admin Console with OAuth credentials.

!!! note
    Requires ServiceNow Zurich or later with a Now Assist SKU and Now Assist for ITSM installed.

### Step 3: ServiceNow ITOM credentials

Configure the following fields in Admin Console for ServiceNow ITOM:
- Host URL: https://your-instance.service-now.com
- API Token: your-api-token

How to obtain: To be added.

```
Host URL: https://your-instance.service-now.com
```

```
API Token: your-api-token
```

> **Expected Result:** ServiceNow ITOM integration is saved in Admin Console.

### Step 4: Atlassian (Jira + Confluence) credentials

Configure the following fields in Admin Console for Atlassian:
- Email: your-atlassian-account@example.com
- API Token: your-atlassian-api-token

How to obtain an Atlassian API token:
1. Log in to id.atlassian.com.
2. Go to Security → API tokens → Create API token.
3. Give it a label (e.g., 'Cisco Agent Builder') and copy the token value.
4. Use this token along with your Atlassian account email when filling in the Admin Console form.

```
Email: your-atlassian-account@example.com
```

```
API Token: your-atlassian-api-token
```

> **Expected Result:** Atlassian integration is saved in Admin Console.

!!! note
    API token authentication must be enabled by your Atlassian org admin. The Atlassian MCP server defaults to OAuth 2.1 — confirm with your admin that API token auth is permitted for your org.

### Step 5: Infoblox DDI credentials

Configure the following fields in Admin Console for Infoblox DDI:
- Host URL: https://your-infoblox-instance.example.com
- API Token: your-api-token

How to obtain: To be added.

```
Host URL: https://your-infoblox-instance.example.com
```

```
API Token: your-api-token
```

> **Expected Result:** Infoblox DDI integration is saved in Admin Console.

### Step 6: BlueCat Integrity credentials

Configure the following fields in Admin Console for BlueCat Integrity:
- Host URL: https://your-bluecat-instance.example.com
- Username: your-username
- Password: your-password

How to obtain: To be added.

```
Host URL: https://your-bluecat-instance.example.com
```

```
Username: your-username
```

```
Password: your-password
```

> **Expected Result:** BlueCat Integrity integration is saved in Admin Console.

### Step 7: BlueCat Edge credentials

Configure the following fields in Admin Console for BlueCat Edge:
- Host URL: https://your-bluecat-edge-instance.example.com
- API Token: your-api-token

How to obtain: To be added.

```
Host URL: https://your-bluecat-edge-instance.example.com
```

```
API Token: your-api-token
```

> **Expected Result:** BlueCat Edge integration is saved in Admin Console.

## Conclusion

You have now set up integrations, created and tested an agent, and promoted it to production. Use the Observability tab and Notifications pane to monitor ongoing agent runs. Refer to Appendix A for vendor-specific credential setup and Appendix B for the full list of available tools per integration. For issues not covered in the Troubleshooting section, contact your Cisco representative.
