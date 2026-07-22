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


