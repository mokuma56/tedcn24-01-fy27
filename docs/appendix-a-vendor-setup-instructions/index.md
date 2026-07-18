# Appendix A: Vendor Setup Instructions

Credential requirements for each supported third-party integration.

## Step 1: ServiceNow CMDB credentials

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

!!! success "Expected Result"
    ServiceNow CMDB integration is saved in Admin Console.

## Step 2: ServiceNow ITSM credentials

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

!!! success "Expected Result"
    ServiceNow ITSM integration is saved in Admin Console with OAuth credentials.

!!! note
    Requires ServiceNow Zurich or later with a Now Assist SKU and Now Assist for ITSM installed.

## Step 3: ServiceNow ITOM credentials

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

!!! success "Expected Result"
    ServiceNow ITOM integration is saved in Admin Console.

## Step 4: Atlassian (Jira + Confluence) credentials

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

!!! success "Expected Result"
    Atlassian integration is saved in Admin Console.

!!! note
    API token authentication must be enabled by your Atlassian org admin. The Atlassian MCP server defaults to OAuth 2.1 — confirm with your admin that API token auth is permitted for your org.

## Step 5: Infoblox DDI credentials

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

!!! success "Expected Result"
    Infoblox DDI integration is saved in Admin Console.

## Step 6: BlueCat Integrity credentials

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

!!! success "Expected Result"
    BlueCat Integrity integration is saved in Admin Console.

## Step 7: BlueCat Edge credentials

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

!!! success "Expected Result"
    BlueCat Edge integration is saved in Admin Console.
