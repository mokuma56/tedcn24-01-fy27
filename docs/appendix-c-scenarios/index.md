# Appendix C: Scenarios

This appendix contains the two scenario briefs for the Section 4 Team Challenge. Each scenario places your team inside a real operational situation at a specific branch site — your job is to use AI Canvas to investigate, identify every active fault condition, and build a complete root cause analysis. No hints, no prescribed steps, no suggested prompts: your team decides how to approach it, and you'll be evaluated on the quality of your RCA and the creativity of your prompt engineering. If you get stuck or want to compare your approach after the challenge, Appendix D: Investigation Guide contains a worked example for each scenario.

## Scenario 1 — Buenos Aires

**The Situation**

It is Monday morning and the Buenos Aires branch is on fire. Complaints are flooding the helpdesk — users cannot reach internal applications, VoIP calls are dropping mid-session, and the NOC dashboard is lit with alerts. A change window ran over the weekend: a new access switch was added to the floor and a firewall policy update was pushed. Nothing has been formally verified since. Your team has full access to the Cisco Cloud Control environment — Meraki, ThousandEyes, Catalyst SD-WAN, and AI Canvas — and no one has touched a CLI. It is your job to figure out what happened.

---

**Your Mission**

Use AI Canvas in Cisco Cloud Control to investigate the Buenos Aires site, identify every active fault condition, and produce a complete Root Cause Analysis (RCA) ready to present to your proctor.

---

!!! warning "Active Fault Conditions"
    There are **6 active fault conditions** at this site. Your team must identify all of them.

---

**What a Strong RCA Looks Like**

- **Problem statement** — what is happening and where
- **Contributing factors** — conditions that led to or worsened the issue
- **Root cause(s)** — the underlying reason the issue occurred
- **Impact assessment** — what is affected and how severely
- **Recommended remediation steps** — clear, actionable next steps

---

**Proctor Presentation**

When you are ready to present, your proctor will ask you to:

- Walk through the prompts you used and explain how your investigation evolved across iterations
- Describe the relationships you found between fault conditions and how you connected them
- Present your complete RCA covering all six fault conditions
- Explain how you would deliver this investigation to a customer in a live demo

---

*If your team gets stuck, refer to [Appendix D: Investigation Guide](../appendix-d-investigation-guide/) for a worked example using this scenario.*

## Scenario 2 — Mexico City

**The Situation**

It is Tuesday afternoon. The Mexico City branch is down — partially. The helpdesk queue is growing and the calls are frustrating because users cannot describe the problem consistently. Some things work. Some do not. Public internet is reachable. Internal applications are not. Nobody can get to the intranet. Internal hostnames are not resolving. Meanwhile, the NOC has a device that has been completely silent since last night — no management polling responses, no telemetry, nothing. Overnight, the access layer received a scheduled firmware upgrade as part of a maintenance window. Post-upgrade verification was never completed. Nobody signed off on a clean bill of health before the team went home. Now it is Tuesday afternoon, the branch is degraded, and the business is asking for answers. Your team has full access to Cisco Cloud Control — Meraki, ThousandEyes, and AI Canvas. No CLI access yet.

---

**Your Mission**

Use AI Canvas in Cisco Cloud Control to investigate the Mexico City site, identify every active fault condition, and produce a complete Root Cause Analysis ready to present to your proctor.

---

!!! warning "Active Fault Conditions"
    There are **3 active fault conditions** at this site. Your team must identify all of them.

---

**What a Strong RCA Looks Like**

- **Problem statement** — what is happening and where
- **Contributing factors** — conditions that led to or worsened the issue
- **Root cause(s)** — the underlying reason the issue occurred
- **Impact assessment** — what is affected and how severely
- **Recommended remediation steps** — clear, actionable next steps

---

**Proctor Presentation**

When you are ready to present, your proctor will ask you to:

- Walk through your prompt approach and explain any iterations or pivots you made during the investigation
- Describe the relationships you found between the fault conditions
- Present your complete RCA covering all fault conditions
- Explain how you would walk a customer through this investigation in a live demo context

---

*If your team gets stuck, refer to [Appendix D: Investigation Guide](../appendix-d-investigation-guide/) for a worked example using this scenario.*
