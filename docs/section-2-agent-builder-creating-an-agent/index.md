# Section 2: Agent Builder — Creating an Agent

Build an autonomous agent by defining its profile, trigger, and cadence, then promote it to production.

## Step 1: Verify integrations before creating an agent

Before creating an agent, verify that all integrations the agent will need are already configured. Cisco product tools (Meraki, ThousandEyes, Catalyst SD-WAN, etc.) are available by default — no setup required. Third-party integrations (ServiceNow, Atlassian, Infoblox, BlueCat, etc.) must be configured in Admin Console before you can use them in an agent. See Section 1 for setup steps.

!!! success "Expected Result"
    All required integrations show ✓ Configured in the Integrations tab.

## Step 2: Start agent creation

Click the Agent Builder tab. If no agents have been created yet, you will see a Create Agent call to action in the center of the page, along with a + Create Agent button in the top right. Click either to start the agent creation flow. Agent creation has three steps: Agent Profile → Triggers → Review.

!!! success "Expected Result"
    The agent creation flow opens at Step 1: Agent Profile.

## Step 3: Step 1 — Complete the Agent Profile

Fill in the required Agent Profile fields including agent name, description, and instructions. Tips for writing good instructions: be specific about what data to pull and from which source; specify the output format (e.g., a table with specific columns); include thresholds or conditions to flag (e.g., 'flag any incident not updated in the last 4 hours'). Once the required fields are filled in, click Continue.

```
flag any incident not updated in the last 4 hours
```

!!! success "Expected Result"
    The Agent Profile form is completed and you advance to Step 2: Triggers.

## Step 4: Step 2 — Configure Triggers

Select a Trigger Mode from the drop-down. Currently, only Ambient mode is available. Set the Activation Cadence to determine how often the agent runs. Enter a Trigger Prompt — the specific request the agent executes on each run. The Instructions from Step 1 define how the agent behaves; the trigger prompt is the specific request it executes on each run. Keep it concise. Click Continue when done. You can click Back at any point to return to the previous step.

```
Fetch and summarize the current status of the incidents.
```

!!! success "Expected Result"
    The Triggers form shows Ambient mode selected, an activation cadence, and a trigger prompt entered.

## Step 5: Step 3 — Review and Create Agent

The Review page shows a summary of everything you configured — agent name, description, trigger mode, activation schedule, and trigger prompt. Verify the details look correct, then click Create Agent.

!!! success "Expected Result"
    Studio runs a series of automated steps: Validating inputs, Selecting tools, AI Defense reviewing, Building manifest, Validating configuration, Generating agent package, Saving configuration, Opening launch setup. Once complete, a confirmation page shows the agent name, description, and a summary of its configuration including status, version, trigger type, and AI Defense protection. Two buttons are available: View Agent and Test Agent.

!!! note
    The automated steps typically take one to a few minutes. Tool selection automatically identifies and scopes the MCP tools this agent needs based on its instructions and integrations — the agent only has access to tools relevant to its job, which improves accuracy, reduces token usage, and makes it faster. In a future release, you will be able to see and modify this tool scope directly.
