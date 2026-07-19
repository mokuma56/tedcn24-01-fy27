#  (TEDC24) Unlock the Potential of Cisco’s Agentic Ops Framework

**Version:** 0.4 Draft  |  **Author:** Unknown  |  **Date:** 2026-07-18  |  **Difficulty:** Intermediate  |  **Duration:** 60 min

**Tags:** agent-builder, cisco, ai-canvas, mcp, integrations, automation, cloud-control, studio

## Prerequisites

- Cisco SSO credentials and access to your Cloud Control tenant
- Admin Console access within your tenant
- API credentials for the third-party tools you want to connect (see Appendix A)

## Introduction

## The Vision: Cisco Cloud Control

Enterprise IT runs on specialized products, each built to solve a different operational challenge. Cisco has spent decades building deep capabilities across networking, security, compute, observability, and collaboration. That depth matters — but the hardest operational problems rarely stay within one product or IT domain. Issues spill across boundaries, context gets lost, and teams spend more time coordinating than resolving.

Cisco Cloud Control was built to change that. It connects the full Cisco estate and third-party systems into one unified operational environment, giving teams a single place to manage infrastructure, carry context across products, and move from issue to resolution — without giving up the specialized tools they already rely on.

As AI agents become a practical part of IT operations, teams will increasingly work alongside agents that investigate issues, recommend changes, and take action. This new operating model is **AgenticOps**. Cisco Cloud Control is the platform that makes it practical — providing the trusted access, live operational context, authorized tools, and safeguards that agents need to act with confidence.

Built on this foundation, **AI Canvas** brings operators and AI agents together to investigate and resolve cross-domain issues in real time. **Agent Builder** lets organizations build their own custom agents, encode their expertise, and connect the tools they already use — such as ServiceNow, Meraki, and more.

Cisco Cloud Control delivers three foundational capabilities:

- **Manage** — One control plane to manage the Cisco estate and connected third-party systems.
- **Resolve** — Find and fix issues across products and IT domains with shared operational context.
- **Extend** — Build custom apps and agents, connect existing tools, and add Cisco and ecosystem capabilities.

---

## What You Will Do in This Lab

In this hands-on lab you will experience Cisco Cloud Control end-to-end across its key platform areas:

1. **Explore the Platform** — Navigate Cisco Cloud Control and understand its capabilities across Platform Services, getting familiar with the unified operational environment.

2. **Discover Your Meraki Organization** — Connect to your Meraki org and explore the network infrastructure available in your POD, seeing how Cisco Cloud Control surfaces real device and topology context.

3. **Experience the Agentic AI Canvas** — Work with the AI Canvas to see how operators and AI agents collaborate to investigate and resolve cross-domain issues across your infrastructure.

4. **Build an Agent with Agent Builder** — Leverage a ServiceNow integration to construct a working AI agent from scratch, defining its tools, context, and behavior.

5. **Troubleshoot a Network Issue** — Diagnose and resolve a connectivity problem between the two switches in your POD, using the platform's operational context to identify root cause and take action.

## Learning Objectives

- Navigate to Agent Builder via the Cloud Control Studio interface
- Configure third-party integrations (ServiceNow, Atlassian, Infoblox, BlueCat) in Admin Console
- Verify integration connections and use them in AI Canvas with natural language queries
- Create an autonomous agent with a profile, trigger, and cadence
- Test an agent using the Test tab before promoting to production
- Promote, monitor, and manage agent versions in production

## Navigating to Agent Builder

### Step 1: Overview

Log in to Cloud Control at cloud.cisco.com.

Click the nine-dots menu in the top header.

Under Platform Services, click Studio. If it is not visible, click Show more to expand the list.

This opens the Agent Builder Overview page. The top navigation bar has four tabs: Overview, Integrations, Agent Builder, and Observability.

On a fresh setup, the Overview page shows two calls to action: Browse Integrations and Create an Agent. It also shows three summary cards — agents currently running, total active agents, and number of connected integrations — along with a Recent Agent Activity section and a Connected Integrations section.

## TEST

this is a test section

## Section 1: Third-Party Integrations

### Step 2: What Are Integrations?

Integrations connect Agent Builder to your third-party tools — ServiceNow, Atlassian, Infoblox, BlueCat, and others. Each integration is backed by an MCP server that exposes the vendor’s API as callable tools. Once connected, AI Canvas can use those tools to query data and take actions in that vendor’s platform on your behalf.

### Step 3: Browse the Integration Catalog

Click the Integrations tab. You will see a tile catalog with one tile per available MCP server. Each tile shows the vendor name, product description, and either a + Configure button (not yet connected) or a ✓ Configured checkmark (already connected) in the bottom right corner.

### Step 4: 1.2 Configure an Integration

Clicking + Configure on a tile cross-launches you into the Integrations section of the Admin Console. You can also navigate there directly:

Click the nine-dots menu → Admin Console (under Platform Services; click Show more if not visible) → Integrations.

Click + Create Integration in the top right.

In the pop-up, click the Integration Name drop-down and select the integration you want to set up.

After selecting an integration, additional fields appear specific to that vendor. Enter your credentials.

See Appendix A for what each vendor requires and where to find those values.

Click Save.

The integration appears in the table on the Admin Console Integrations page with the name and date created. You can Edit or Delete it from that table. Only one active credential entry is supported per integration — to update credentials, edit the existing entry.

Each user configures their own credentials. Repeat this process for every integration you want to connect.

### Step 5: 1.3 Verify the Connection

Return to the Integrations tab in Studio. Each integration you configured will now show a ✓ Configured checkmark instead of + Configure.

### Step 6: 1.4 Use Your Integrations in Canvas

Go to AI Canvas and enter a natural language query. Canvas routes the query to the appropriate integration based on context.

What you can ask depends on which tools that vendor’s MCP server exposes. Canvas fetches the relevant data and returns a structured result.

See Appendix B for the full tool list per integration.

Sample queries:

“Fetch details for ServiceNow ticket INC0012345”

“Show me all open P1 incidents in ServiceNow”

“What are the open Jira issues in the NETOPS project?”

“Check DHCP utilization for the 10.150.28.0/24 subnet”

## Section 2: Agent Builder

### Step 7: 2.1 Creating an Agent

Before creating an agent, verify that all integrations the agent will need are already configured:

Cisco product tools (Meraki, ThousandEyes, Catalyst SD-WAN, etc.) are available by default — no setup required.

Third-party integrations (ServiceNow, Atlassian, Infoblox, BlueCat, etc.) must be configured in Admin Console before you can use them in an agent. See Section 1 for setup steps.

Click the Agent Builder tab. If no agents have been created yet, you will see a Create Agent call to action in the center of the page, along with a + Create Agent button in the top right.

Click either to start the agent creation flow. Agent creation has three steps: Agent Profile → Triggers → Review.

### Step 8: Step 1: Agent Profile

Tips for writing good instructions:

Be specific about what data to pull and from which source

Specify the output format (e.g., a table with specific columns)

Include thresholds or conditions to flag (e.g., “flag any incident not updated in the last 4 hours”)

Once the required fields are filled in, click Continue.

### Step 9: Step 2: Triggers

Trigger Mode determines how the agent is activated. Select a mode from the drop-down:

Currently, only Ambient mode is available.

Activation Cadence — Set how often the agent runs:

Trigger Prompt — Enter the prompt sent to the agent each time it wakes up. The Instructions from Step 1 define how the agent behaves; the trigger prompt is the specific request it executes on each run. Keep it concise.

Example:

“Fetch and summarize the current status of the incidents.”

Click Continue when done. You can click Back at any point to return to the previous step.

### Step 10: Step 3: Review

The Review page shows a summary of everything you configured — agent name, description, trigger mode, activation schedule, and trigger prompt. Verify the details look correct, then click Create Agent.

### Step 11: What Happens When You Click Create Agent

Studio runs through a series of automated steps that typically take one to a few minutes:

Validating inputs — Checks that all required fields are present and correctly formatted

Selecting tools — Automatically identifies and scopes the MCP tools this agent needs based on its instructions and integrations. The agent only has access to the tools relevant to its job, which improves accuracy, reduces token usage, and makes it faster. In a future release, you will be able to see and modify this tool scope directly.

AI Defense reviewing — Scans the agent configuration for safety and security issues

Building manifest — Assembles the agent’s runtime manifest

Validating configuration — Validates the full configuration package

Generating agent package — Generates the deployable agent artifact

Saving configuration — Persists the agent configuration

Opening launch setup — Initializes the agent and opens the confirmation page

Once complete, a confirmation page shows the agent name, description, and a summary of its configuration including status, version, trigger type, and AI Defense protection.

Two buttons are available:

### Step 12: 2.2 Testing Your Agent

The Test tab provides a live test environment where you can chat directly with the agent to verify it responds correctly before promoting it to production.

Pre-canned prompts at the top let you run common checks with a single click:

Summarize configuration — Agent summarizes its own setup

Explain guardrails — Agent describes its safety constraints

Run readiness check — Agent confirms it can reach its configured integrations and tools

You can also type anything directly into the prompt box. A good starting point is to enter the trigger prompt you configured and verify the agent returns the expected output.

### Step 13: 2.3 Managing Your Agent

The agent detail page has four tabs:

### Step 14: Versions and Promoting to Production

When an agent is first created, it starts as Version 1 in Candidate state, visible in the Release History table on the Configurations tab.

To promote an agent to production:

In the Configurations tab, find the Release History table.

On the V1 row, click Promote to production under Actions.

A confirmation pop-up will appear. Review the details, then click Promote to production to confirm, or Cancel to go back.

The version is promoted instantly. A confirmation banner appears and the version badge in the Release History table updates to Production. The agent will now begin running on the schedule you configured.

Once in production, you can:

Update the config — Edit the agent’s profile or instructions to create a new version, test it, and promote it when ready

Monitor runs — Check the Run tab to see execution history, outputs, and any errors

Update the trigger — Go to the Trigger tab to change the cadence or trigger prompt

Roll back — Promote any previously published version from the Release History table

Delete the agent — Remove the agent entirely from the agent detail page if it is no longer needed

### Step 15: 2.4 Observability

Each time an ambient agent completes a run, its output appears in the Notifications pane in the Cloud Control header — one notification per run. To view results:

Click the notifications icon in the Cloud Control header.

Find the notification for the run you want to review and click on it.

The full output produced by that run will be displayed.

Use the Download option to export the output if needed.

## Troubleshooting

## Appendix A: Vendor Setup Instructions

This appendix covers what you need from each vendor’s platform to complete the credential form in Admin Console.

### Step 16: ServiceNow CMDB

Fields in Admin Console:

Host URL — https://your-instance.service-now.com

API Token — your-api-token

How to obtain:

To be added.

### Step 17: ServiceNow ITSM

Fields in Admin Console:

Host URL — https://your-instance.service-now.com

Client ID — your-oauth-client-id

Client Secret — your-oauth-client-secret

How to obtain:

ServiceNow ITSM uses OAuth 2.0. You will need oauth_admin, mi_admin, or admin role in your ServiceNow instance.

In ServiceNow, navigate to All → Machine Identity Console → Inbound integrations.

Create a new integration, select OAuth - Authorization code grant, and set Token Format to JWT under Advanced Options.

Provide the redirect URL shown in the Admin Console integration form.

Complete the OAuth flow using a dedicated integration user account created for this purpose.

Requirement: ServiceNow Zurich or later with a Now Assist SKU and Now Assist for ITSM installed.

### Step 18: ServiceNow ITOM

Fields in Admin Console:

Host URL — https://your-instance.service-now.com

API Token — your-api-token

How to obtain:

To be added.

### Step 19: Atlassian (Jira + Confluence)

Fields in Admin Console:

Email — your-atlassian-account@example.com

API Token — your-atlassian-api-token

How to obtain an Atlassian API token:

Log in to id.atlassian.com.

Go to Security → API tokens → Create API token.

Give it a label (e.g., “Cisco Agent Builder”) and copy the token value.

Use this token along with your Atlassian account email when filling in the Admin Console form.

Note: API token authentication must be enabled by your Atlassian org admin. The Atlassian MCP server defaults to OAuth 2.1 — confirm with your admin that API token auth is permitted for your org.

### Step 20: Infoblox DDI

Fields in Admin Console:

Host URL — https://your-infoblox-instance.example.com

API Token — your-api-token

How to obtain:

To be added.

### Step 21: BlueCat Integrity

Fields in Admin Console:

Host URL — https://your-bluecat-instance.example.com

Username — your-username

Password — your-password

How to obtain:

To be added.

### Step 22: BlueCat Edge

Fields in Admin Console:

Host URL — https://your-bluecat-edge-instance.example.com

API Token — your-api-token

How to obtain:

To be added.

## Appendix B: Available Tools by Integration

What Canvas can do via each integration is determined by the tools that vendor exposes through their MCP server.

### Step 23: Atlassian — Jira



### Step 24: Atlassian — Confluence



### Step 25: ServiceNow ITSM

Note: Incident creation is not in the confirmed tool set for ITSM and may require additional configuration. Contact your Cisco representative.

### Step 26: ServiceNow CMDB, ITOM, Infoblox, BlueCat

Tool lists to be added — pending confirmation.

Document version: 0.4 Draft — All sections and screenshots complete. Appendix A vendor instructions partially complete.

## Conclusion

You have now set up integrations, created and tested an agent, and promoted it to production. Use the Observability tab and Notifications pane to monitor ongoing agent runs. Refer to Appendix A for vendor-specific credential setup and Appendix B for the full list of available tools per integration. For issues not covered in the Troubleshooting section, contact your Cisco representative.
