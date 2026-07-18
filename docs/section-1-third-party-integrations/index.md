# Section 1: Third-Party Integrations

Connect third-party tools such as ServiceNow, Atlassian, Infoblox, and BlueCat to Agent Builder via MCP-backed integrations.

## Step 1: Browse the Integration Catalog

Click the Integrations tab. You will see a tile catalog with one tile per available MCP server. Each tile shows the vendor name, product description, and either a + Configure button (not yet connected) or a ✓ Configured checkmark (already connected) in the bottom right corner.

!!! success "Expected Result"
    The Integrations catalog is visible showing available MCP server tiles.

## Step 2: Open the Configure Integration flow

Click + Configure on a tile. This cross-launches you into the Integrations section of the Admin Console, where you can enter and save the credentials required to connect that integration. You can also navigate to the Admin Console Integrations page directly: click the nine-dots menu → Admin Console (listed under Platform Services; click Show more if it is not immediately visible) → Integrations.

!!! success "Expected Result"
    The Admin Console Integrations page is displayed showing the list of configured integrations.

## Step 3: Create a new integration

Click + Create Integration in the top right. In the pop-up, click the Integration Name drop-down and select the integration you want to set up. After selecting an integration, additional fields appear specific to that vendor. Enter your credentials. See Appendix A for what each vendor requires and where to find those values.

!!! success "Expected Result"
    The Create Integration form shows vendor-specific fields such as Host URL and API Token.

!!! note
    Only one active credential entry is supported per integration — to update credentials, edit the existing entry. Each user configures their own credentials. Repeat this process for every integration you want to connect.

## Step 4: Save the integration

Click Save.

!!! success "Expected Result"
    The integration appears in the table on the Admin Console Integrations page with the name and date created. You can Edit or Delete it from that table.

## Step 5: Verify the connection

Return to the Integrations tab in Studio. Each integration you configured will now show a ✓ Configured checkmark instead of + Configure.

!!! success "Expected Result"
    Configured integrations display a ✓ Configured checkmark on their tiles.

## Step 6: Use integrations in AI Canvas

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

!!! success "Expected Result"
    Canvas displays fetched data such as ticket details including summary, timestamps, and assignment information.
