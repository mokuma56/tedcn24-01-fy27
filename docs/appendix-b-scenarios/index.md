# Appendix B: Scenarios

Want more hands-on time with AI Canvas? This appendix contains two optional practice scenarios. Each one drops you into a realistic operational situation at a branch site, and your goal is to use AI Canvas to investigate, find every active fault condition, and build a complete root cause analysis (RCA). There are no hints, prescribed steps, or suggested prompts — you decide how to approach the problem, which makes these a great way to sharpen your prompting skills. Work through them on your own or with a partner, at your own pace. When you're finished, or if you get stuck, Appendix C: Investigation Guide walks through one worked approach for each scenario.

## Scenario 1 — Buenos Aires

**The Situation**

It is Monday morning and the Buenos Aires branch is on fire. Complaints are flooding the helpdesk — users cannot reach internal applications, VoIP calls are dropping mid-session, and the NOC dashboard is lit with alerts. A change window ran over the weekend: a new access switch was added to the floor and a firewall policy update was pushed. Nothing has been formally verified since. You have full access to the Cisco Cloud Control environment — Meraki, ThousandEyes, Catalyst SD-WAN, and AI Canvas — and no one has touched a CLI. It is your job to figure out what happened.

---

**Your Goal**

Use AI Canvas in Cisco Cloud Control to investigate the Buenos Aires site, identify every active fault condition, and produce a complete Root Cause Analysis (RCA) that you could hand to a customer.

---

!!! warning "Active Fault Conditions"
    There are **6 active fault conditions** at this site. See if you can find all of them.

---

**What a Strong RCA Looks Like**

- **Problem statement** — what is happening and where
- **Contributing factors** — conditions that led to or worsened the issue
- **Root cause(s)** — the underlying reason the issue occurred
- **Impact assessment** — what is affected and how severely
- **Recommended remediation steps** — clear, actionable next steps

---

**Check Your Work**

When you have your RCA, ask yourself:

- Which prompts moved your investigation forward, and how did they change as you learned more?
- How are the fault conditions related, and did you connect them into one story?
- Does your RCA cover six fault conditions, with a clear root cause and remediation for each?
- How would you walk a customer through this investigation in a live demo?

---

*Stuck, or ready to compare your approach? See [Appendix C: Investigation Guide](../appendix-c-investigation-guide/) for a worked example of this scenario.*

## Scenario 2 — Mexico City

**The Situation**

It is Tuesday afternoon. The Mexico City branch is down — partially. The helpdesk queue is growing and the calls are frustrating because users cannot describe the problem consistently. Some things work. Some do not. Public internet is reachable. Internal applications are not. Nobody can get to the intranet. Internal hostnames are not resolving. Meanwhile, the NOC has a device that has been completely silent since last night — no management polling responses, no telemetry, nothing. Overnight, the access layer received a scheduled firmware upgrade as part of a maintenance window. Post-upgrade verification was never completed. Nobody signed off on a clean bill of health before the team went home. Now it is Tuesday afternoon, the branch is degraded, and the business is asking for answers. You have full access to Cisco Cloud Control — Meraki, ThousandEyes, and AI Canvas. No CLI access yet.

---

**Your Goal**

Use AI Canvas in Cisco Cloud Control to investigate the Mexico City site, identify every active fault condition, and produce a complete Root Cause Analysis that you could hand to a customer.

---

!!! warning "Active Fault Conditions"
    There are **3 active fault conditions** at this site. See if you can find all of them.

---

**What a Strong RCA Looks Like**

- **Problem statement** — what is happening and where
- **Contributing factors** — conditions that led to or worsened the issue
- **Root cause(s)** — the underlying reason the issue occurred
- **Impact assessment** — what is affected and how severely
- **Recommended remediation steps** — clear, actionable next steps

---

**Check Your Work**

When you have your RCA, ask yourself:

- Which prompts moved your investigation forward, and where did you change direction?
- What do the fault conditions have in common, and did you find the shared contributing factor?
- Does your RCA cover all three fault conditions, with a clear root cause and remediation for each?
- How would you walk a customer through this investigation in a live demo?

---

*Stuck, or ready to compare your approach? See [Appendix C: Investigation Guide](../appendix-c-investigation-guide/) for a worked example of this scenario.*
