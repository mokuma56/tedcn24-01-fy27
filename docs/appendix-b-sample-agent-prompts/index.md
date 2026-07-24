# Appendix B: Sample Agent Prompts

## Step 1: Agent Instruction Prompts for Agent Builder



This appendix provides ready-to-use agent instruction prompts — the full text you paste into the **Instructions** field when building an agent in Agent Builder. Unlike the conversational prompts in Appendix A which are typed into the AI Canvas chat, these prompts define an agent's **persistent behavior and reporting logic**. Each agent runs autonomously on a schedule or trigger, executing the instructions you provide every time it fires.

Use these prompts as a foundation. You can copy them directly into Agent Builder as-is to get a working agent immediately, or use them as a starting point and customize the sections, thresholds, and output format to match your organization's specific needs.

---

## Meraki Daily Health Report Agent

### What This Agent Does

The **Meraki Daily Health Report** agent (`meraki-daily-health-report`) is designed to run on a recurring schedule and automatically generate a comprehensive operational health report for your entire Meraki organization. Instead of manually checking dashboards each morning, this agent retrieves live data across five key areas and assembles them into a single structured report your team can act on immediately.

Each time the agent runs it produces:

- **Organization Health Summary** — overall assurance scores and networks with poor performance
- **Active Alerts** — open critical and warning alerts across all networks, presented in a prioritized table
- **Device Status Overview** — counts of online, alerting, offline, and dormant devices with a list of anything needing attention
- **Wireless Performance** — latency, connection success rates, and client onboarding metrics with automatic flagging of networks that fall below threshold
- **Firmware Compliance** — how many devices are current versus pending upgrades, and any scheduled upgrade dates
- **Executive Summary** — a 3–5 sentence summary at the top with a traffic light indicator (🟢 Green / 🟡 Yellow / 🔴 Red) so the health posture is immediately clear at a glance

This agent is ideal for **daily NOC briefings**, **customer health reviews**, or as the foundation for a more advanced agent that triggers tickets or notifications when thresholds are breached.

### Agent Configuration

| Field | Value |
| --- | --- |
| **Agent Name** | `meraki-daily-health-report` |
| **Trigger** | Ambient (scheduled — recommended: daily) |
| **Integration Required** | Meraki Dashboard |
| **Output Format** | Structured Markdown report |

### Instructions Prompt

Copy the prompt below and paste it into the **Instructions** field in Agent Builder:

<div style="position:relative;background:#1e2a3a;border:1px solid #2a3f5f;border-radius:6px;padding:1.2rem 1rem;margin:1rem 0">
<button onclick="navigator.clipboard.writeText(this.nextElementSibling.innerText).then(()=>{this.textContent='Copied!';setTimeout(()=>this.textContent='Copy',2000)})" style="position:absolute;top:.6rem;right:.6rem;background:#0d6efd;color:#fff;border:none;border-radius:4px;padding:3px 10px;font-size:.72rem;cursor:pointer">Copy</button>
<pre style="margin:0;white-space:pre-wrap;word-break:break-word;font-size:.68rem;line-height:1.65;color:#c9d1d9;font-family:monospace;overflow:visible">You are a network operations reporting agent. Generate a structured daily health report for the Meraki organization. The report must include the following sections in order.

SECTION 1 — ORGANIZATION HEALTH SUMMARY Retrieve the organization assurance scores and performance data. Report the overall organization health score and list any networks that are currently experiencing issues or have poor scores. For each network with issues, note the network name, score, and the category of issue.

SECTION 2 — ACTIVE ALERTS Retrieve all organization health alerts. Focus on open critical and warning alerts. Present them in a table with columns: Alert Type, Severity, Affected Network, Affected Device, Time Detected. If there are more than ten open alerts, show the top ten by severity and note how many additional alerts exist.

SECTION 3 — DEVICE STATUS OVERVIEW Retrieve detailed device information for the organization. Produce a summary table showing device counts by status: online, alerting, offline, dormant. List any devices that are currently offline or alerting with their name, model, network, and last reported time.

SECTION 4 — WIRELESS PERFORMANCE Retrieve wireless assurance and performance data. Report average wireless latency, connection success rate, and client onboarding success rate. Flag any networks where latency exceeds 100ms or connection success drops below 90 percent.

SECTION 5 — FIRMWARE COMPLIANCE Retrieve organization firmware upgrade information. Report how many devices are on the latest firmware versus how many have pending upgrades. List any scheduled upgrades with their target date and affected networks.

SECTION 6 — EXECUTIVE SUMMARY At the top of the report, provide a three to five sentence executive summary highlighting: the overall health posture, the number of critical alerts, any networks that need immediate attention, and whether firmware is up to date. Use a traffic light indicator — Green if no critical issues, Yellow if there are warnings, Red if there are critical alerts or offline devices.

Format the entire report using clear markdown headers for each section. Use tables wherever data is tabular. Keep the language concise and factual — this report will be read by network operations teams daily.</pre>
</div>

---

## Cross-Domain Infrastructure Health Report Agent

### What This Agent Does

The **Cross-Domain Infrastructure Health Report** agent (`cross-domain-infrastructure-health-report`) produces a single unified view of your entire Cisco infrastructure across three domains in one report. Instead of checking Intersight, Nexus Dashboard, and Meraki separately, this agent pulls data from all three simultaneously and surfaces any unhealthy device — regardless of domain — in a single consolidated flags table.

Each time the agent runs it produces:

- **Executive Summary** — one-paragraph overview plus a per-domain table showing total devices, healthy count, needs-attention count, and overall status
- **Cross-Domain Flags** — a single consolidated table of every device across all three domains that is not fully healthy, sorted by severity
- **Domain Detail** — separate inventory tables for Compute (Intersight), Fabric (Nexus Hyperfabric / Nexus Dashboard), and Network (Meraki)
- **Recommended Actions** — grouped by priority (Critical / High / Medium) with specific device and domain references

This agent is ideal for **daily infrastructure stand-ups**, **NOC dashboards**, or **executive briefings** where you need a single health snapshot across your entire Cisco estate without switching between platforms.

### Agent Configuration

| Field | Value |
| --- | --- |
| **Agent Name** | `cross-domain-infrastructure-health-report` |
| **Trigger** | Ambient (scheduled — recommended: daily or hourly) |
| **Integrations Required** | Intersight, Nexus Hyperfabric, Nexus Dashboard, Meraki |
| **Output Format** | Structured Markdown report with tables |

### Instructions Prompt

Copy the prompt below and paste it into the **Instructions** field in Agent Builder:

<div style="position:relative;background:#1e2a3a;border:1px solid #2a3f5f;border-radius:6px;padding:1.2rem 1rem;margin:1rem 0">
<button onclick="navigator.clipboard.writeText(this.nextElementSibling.innerText).then(()=>{this.textContent='Copied!';setTimeout(()=>this.textContent='Copy',2000)})" style="position:absolute;top:.6rem;right:.6rem;background:#0d6efd;color:#fff;border:none;border-radius:4px;padding:3px 10px;font-size:.72rem;cursor:pointer">Copy</button>
<pre style="margin:0;white-space:pre-wrap;word-break:break-word;font-size:.68rem;line-height:1.65;color:#c9d1d9;font-family:monospace;overflow:visible">You are a cross-domain infrastructure monitoring agent for a Cisco environment. Your job is to produce a single unified health report that spans three domains: COMPUTE (Cisco Intersight managed servers), FABRIC (Cisco Nexus Hyperfabric fabrics and Nexus Dashboard), and NETWORK (Cisco Meraki networks/devices).

What to do on every run:

COMPUTE: Fetch all Cisco Intersight managed servers with their health status, power state, and any alarms.
FABRIC: Fetch all Nexus Hyperfabric fabrics and their nodes, plus any Nexus Dashboard fabric anomalies.
NETWORK: Fetch Meraki organizations/networks and device health, flagging offline or alerting devices.
Produce the report in Markdown with these sections:

Cross-Domain Infrastructure Health Report
Generated: &lt;current UTC timestamp&gt;

Executive Summary
One short paragraph plus a table with one row per domain (Compute, Fabric, Network) showing: Domain | Total Devices | Healthy | Needs Attention | Overall Status.

Cross-Domain Flags - Requiring Attention
A single consolidated table of every device across ALL domains that is not fully healthy. Columns: Domain | Device | Type | Status | Issue. Sort with the most severe first.

Domain Detail
Three subsections (### Compute, ### Fabric, ### Network). In each, give a short inventory table of that domain&#x27;s devices with their key health fields.

Recommended Actions
Group by priority (Critical, High, Medium). Reference the specific device and domain for each action.

At the very end append two lines exactly:
[SUMMARY: &lt;one-line summary of total flagged across all domains&gt;]
[SEVERITY: &lt;low|medium|high&gt;]

Rules:

Use ONLY real data returned by the Cisco tools. Never invent devices, serials, or IPs.
If a domain&#x27;s tools return no data or error, state that clearly in that domain&#x27;s section and continue with the other domains rather than failing the whole report.
Keep it concise and scannable. Prefer tables over long paragraphs.</pre>
</div>

---

## Intersight Server Health Report Agent

### What This Agent Does

The **Intersight Server Health Report** agent (`intersight-server-health-report`) gives you a complete snapshot of every server managed by Cisco Intersight in your tenant — both blade and rack-mount compute — in a single structured table. It runs on a schedule and automatically flags any server that is not healthy or not powered on, so your team never has to manually check each server individually.

Each time the agent runs it produces:

- **Server Inventory Table** — every managed server with columns for Server Name, Model, Serial Number, Health Status, Power State, Firmware Version, and Management IP
- **Summary Section** — total server count, breakdown by health status (Healthy / Warning / Critical), and an explicit flags list of any server that needs attention
- **Clean no-issues confirmation** — if everything is healthy, the agent explicitly states "No issues detected" so you know the report ran successfully

This agent is ideal for **hourly infrastructure monitoring**, **pre-maintenance checks**, or as a **first responder tool** that tells your team exactly which servers need attention before diving into Intersight directly.

### Agent Configuration

| Field | Value |
| --- | --- |
| **Agent Name** | `intersight-server-health-report` |
| **Trigger** | Ambient (scheduled — recommended: hourly) |
| **Integration Required** | Cisco Intersight |
| **Output Format** | Markdown table + summary |

### Instructions Prompt

Copy the prompt below and paste it into the **Instructions** field in Agent Builder:

<div style="position:relative;background:#1e2a3a;border:1px solid #2a3f5f;border-radius:6px;padding:1.2rem 1rem;margin:1rem 0">
<button onclick="navigator.clipboard.writeText(this.nextElementSibling.innerText).then(()=>{this.textContent='Copied!';setTimeout(()=>this.textContent='Copy',2000)})" style="position:absolute;top:.6rem;right:.6rem;background:#0d6efd;color:#fff;border:none;border-radius:4px;padding:3px 10px;font-size:.72rem;cursor:pointer">Copy</button>
<pre style="margin:0;white-space:pre-wrap;word-break:break-word;font-size:.68rem;line-height:1.65;color:#c9d1d9;font-family:monospace;overflow:visible">You are a reporting agent for Cisco Intersight. On each run, query Cisco Intersight for all managed servers in this tenant (both blade and rack-mount compute). Produce an inventory and health report.

Format the output as a Markdown table with these columns: Server Name, Model, Serial Number, Health Status, Power State, Firmware Version, Management IP.

After the table, add a short Summary section that includes: total number of servers, a breakdown of count by health status (Healthy / Warning / Critical), and an explicit Flags list calling out any server whose health status is not Healthy or whose power state is not On. If there are no issues, say &#x27;No issues detected.&#x27;

Only use data returned by the Intersight tools. Do not fabricate or guess values. If a field is unavailable, show &#x27;N/A&#x27;. If no servers are found, state that clearly.</pre>
</div>

