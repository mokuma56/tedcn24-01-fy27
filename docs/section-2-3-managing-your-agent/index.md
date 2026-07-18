# Section 2.3: Managing Your Agent

Promote, monitor, update, and manage agent versions using the agent detail page tabs.

## Step 1: Promote an agent to production

In the Configurations tab, find the Release History table. On the V1 row, click Promote to production under Actions. A confirmation pop-up will appear. Review the details, then click Promote to production to confirm, or Cancel to go back.

!!! success "Expected Result"
    The version is promoted instantly. A confirmation banner appears and the version badge in the Release History table updates to Production. The agent will now begin running on the schedule you configured.

!!! note
    When an agent is first created, it starts as Version 1 in Candidate state, visible in the Release History table on the Configurations tab.

## Step 2: Monitor and manage a production agent

Once in production, you can: update the config by editing the agent's profile or instructions to create a new version, test it, and promote it when ready; monitor runs by checking the Run tab to see execution history, outputs, and any errors; update the trigger by going to the Trigger tab to change the cadence or trigger prompt; roll back by promoting any previously published version from the Release History table; or delete the agent by removing it entirely from the agent detail page if it is no longer needed.

!!! success "Expected Result"
    Agent management actions are reflected in the respective tabs and the Release History table.

!!! note
    The agent detail page has four tabs for management.
