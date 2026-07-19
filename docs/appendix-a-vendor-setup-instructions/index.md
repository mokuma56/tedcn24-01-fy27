# Appendix A: Vendor Setup Instructions

This appendix covers what you need from each vendor’s platform to complete the credential form in Admin Console.

## Step 19: ServiceNow CMDB

Fields in Admin Console:

Host URL — https://your-instance.service-now.com

API Token — your-api-token

How to obtain:

To be added.

## Step 20: ServiceNow ITSM

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

## Step 21: ServiceNow ITOM

Fields in Admin Console:

Host URL — https://your-instance.service-now.com

API Token — your-api-token

How to obtain:

To be added.

## Step 22: Atlassian (Jira + Confluence)

Fields in Admin Console:

Email — your-atlassian-account@example.com

API Token — your-atlassian-api-token

How to obtain an Atlassian API token:

Log in to id.atlassian.com.

Go to Security → API tokens → Create API token.

Give it a label (e.g., “Cisco Agent Builder”) and copy the token value.

Use this token along with your Atlassian account email when filling in the Admin Console form.

Note: API token authentication must be enabled by your Atlassian org admin. The Atlassian MCP server defaults to OAuth 2.1 — confirm with your admin that API token auth is permitted for your org.

## Step 23: Infoblox DDI

Fields in Admin Console:

Host URL — https://your-infoblox-instance.example.com

API Token — your-api-token

How to obtain:

To be added.

## Step 24: BlueCat Integrity

Fields in Admin Console:

Host URL — https://your-bluecat-instance.example.com

Username — your-username

Password — your-password

How to obtain:

To be added.

## Step 25: BlueCat Edge

Fields in Admin Console:

Host URL — https://your-bluecat-edge-instance.example.com

API Token — your-api-token

How to obtain:

To be added.
