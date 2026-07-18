# Section 2.2: Testing Your Agent

Use the Test tab to verify the agent responds correctly before promoting it to production.

## Step 1: Open the Test tab

From the agent confirmation page, click Test Agent, or navigate to the Test tab on the agent detail page.

!!! success "Expected Result"
    The Test tab opens showing pre-canned prompt options and a live test chat interface.

## Step 2: Run pre-canned prompts or enter a custom prompt

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

!!! success "Expected Result"
    Each pre-canned prompt returns a substantive, accurate response as described above. The trigger prompt entered as a custom test returns data from the correct integration in the format and with the conditions specified in the agent instructions. All tests must pass before the agent is promoted to production.
