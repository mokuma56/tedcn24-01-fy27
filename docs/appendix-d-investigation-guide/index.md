# Appendix D: Investigation Guide

This appendix contains a worked example investigation for each Appendix C scenario. Use it if your team gets stuck during the Team Challenge, or after the challenge to compare your approach against one possible path. Each guide shows a sample prompt sequence, explains the reasoning behind each step, and walks through how the fault conditions can be surfaced and correlated into a complete RCA. These are not the only valid approaches — your team's own prompt strategy may be equally effective or better. Return to Appendix C: Scenarios for the original challenge briefs.

## Investigation Guide — Scenario 1: Buenos Aires

**Investigation Guide — Scenario 1: Buenos Aires**

*Return to the challenge brief: [Appendix C — Scenario 1: Buenos Aires](../appendix-c-scenarios/)*

---

!!! warning "Note"
    This guide shows one effective path through the investigation. It is not the only valid approach — your team may have found the same faults through a different sequence. Use this to compare strategies, not to check a single right answer.

---

**Overview**

The Buenos Aires scenario involves six fault conditions that cascade from a single weekend change window. The key insight is that the STP instability (faults 2–4) and the ACL change (fault 1) are independent failures introduced at the same time, which makes the situation appear more complex than any single fault would. DNS (fault 5) and packet fragmentation (fault 6) are background issues that compound the user experience. A strong investigation surfaces all six and explains the relationships between them.

---

**Sample Prompt Sequence**

Start broad to establish the site's overall health posture, then narrow systematically toward each fault domain.

**Prompt 1 — Establish baseline**
```
Are there any issues currently affecting the Buenos Aires site?
```
*What to look for:* A summary of active alerts and issues. This should surface multiple problems simultaneously and give you the shape of what you are dealing with before going deep on any one thing.

**Prompt 2 — Check network reachability and WAN health**
```
Give me a summary of my SD-WAN network and application health.
```
*What to look for:* SD-WAN site availability, application SLA violations, and WAN link statistics. Packet fragmentation on the WAN handoff may appear here as elevated error rates or MTU-related anomalies.

**Prompt 3 — Surface switching and STP events**
```
Are there any critical alerts affecting the Buenos Aires network?
```
*What to look for:* STP topology change notifications, Root Guard events, and port state transitions. The unmanaged switch triggering TCNs and the Root Guard activation should appear in Meraki alert history.

**Prompt 4 — Validate end-to-end reachability with ThousandEyes**
```
Are there any anomalies in my ThousandEyes tests for the Buenos Aires site?
```
*What to look for:* Packet loss, latency spikes, and path changes from the Buenos Aires enterprise agent. ThousandEyes will show where in the path traffic is being dropped — helping you separate the STP discard issue (local, access layer) from the WAN fragmentation issue (egress path).

**Prompt 5 — Investigate the access policy fault**
```
Show me the Meraki appliance uplink status for the Buenos Aires network.
```
*What to look for:* Uplink state and any firewall or ACL policy events logged around the change window. The ACL blocking traffic on the distribution device should be visible as a policy change event or as dropped traffic in flow logs.

**Prompt 6 — Surface the DNS fault**
```
Are there any outages affecting my monitored services right now?
```
*What to look for:* DNS test failures or resolution timeouts from the Buenos Aires vantage point. A ThousandEyes DNS server test will show the misconfigured resolver returning no results for internal hostnames.

**Follow-up correlation prompt**
```
Correlate the STP topology changes, Root Guard activation, and port discard events at Buenos Aires and explain the relationship between them.
```
*What to look for:* The AI should connect the unmanaged switch → superior BPDU → Root Guard trigger → port root-inconsistent state → STP discarding chain. This is the core causal thread of the scenario.

---

**The Six Fault Conditions**

| # | Fault | How it surfaces |
|---|---|---|
| 1 | Port not forwarding — access policy | ACL policy event / dropped traffic in Meraki logs around the change window |
| 2 | Root guard activated | Meraki alert: Root Guard triggered on distribution uplink port |
| 3 | STP discarding packets | Port state shown as root-inconsistent / discarding in switching alerts |
| 4 | STP topology changes | Repeated TCN events logged; spanning tree reconvergence activity |
| 5 | Misconfigured DNS | ThousandEyes DNS test failures; internal hostname resolution timing out |
| 6 | Packet fragments detected | WAN link error counters; MTU mismatch on MPLS handoff interface |

---

**RCA Summary — Key Points**

- **Root cause thread:** The weekend change window introduced two independent faults simultaneously — an unmanaged switch that destabilised spanning tree, and an ACL misconfiguration that blocked user traffic. Neither was verified post-change.
- **STP cascade:** Unmanaged switch → superior BPDU advertisement → Root Guard activated → port enters root-inconsistent/discarding state → user traffic on VLAN 10 blocked.
- **DNS:** DHCP scope still points to a decommissioned server — all name resolution fails silently for hosts on the affected segment.
- **Fragmentation:** MTU mismatch on the WAN handoff causes large packets to fragment on egress, degrading application performance independently of the other faults.
- **Connecting thread:** All faults share a single contributing factor — the change window lacked any post-change verification process.

---

*Return to the challenge: [Appendix C — Scenario 1: Buenos Aires](../appendix-c-scenarios/)*

## Investigation Guide — Scenario 2: Mexico City

**Investigation Guide — Scenario 2: Mexico City**

*Return to the challenge brief: [Appendix C — Scenario 2: Mexico City](../appendix-c-scenarios/)*

---

!!! warning "Note"
    This guide shows one effective path through the investigation. It is not the only valid approach — your team may have found the same faults through a different sequence. Use this to compare strategies, not to check a single right answer.

---

**Overview**

The Mexico City scenario is deceptively simple: three faults, one maintenance window, one shared contributing factor. The challenge is that the symptom pattern — public internet works, internal resources do not — naturally steers teams toward a firewall or WAN hypothesis. A strong investigation pivots quickly away from that false lead by establishing device reachability first, then working inward through the access layer before arriving at DNS as the explanation for the partial-vs-full connectivity split.

The C9300-X-Leaf-1 switch explored in Section 1 of the lab is the unreachable device at the centre of this scenario.

---

**Sample Prompt Sequence**

**Prompt 1 — Inventory and reachability baseline**
```
Show me my Mexico City devices.
```
*What to look for:* The full device list for the site. The C9300-X-Leaf-1 should appear but will show as unreachable or have stale telemetry timestamps. This is your first fault signal and your entry point into the investigation.

**Prompt 2 — Establish what is and is not working**
```
Are there any outages affecting my monitored services right now?
```
*What to look for:* ThousandEyes test results from the Mexico City enterprise agent. External tests (public DNS, internet HTTP) will show healthy. Internal service tests will show failures. This pattern is the key diagnostic signal that points away from WAN/firewall and toward a local DNS issue.

**Prompt 3 — Triage active alerts**
```
Are there any critical alerts affecting the Mexico City network?
```
*What to look for:* Alert timestamps relative to the maintenance window. Access port state alerts (err-disabled ports, policy violations) and device offline events will appear here. Cross-referencing timestamps confirms these faults appeared after the firmware upgrade completed.

**Prompt 4 — Check uplink health to eliminate WAN hypothesis**
```
Meraki appliance uplink status for the Mexico City network.
```
*What to look for:* Uplink state. If uplinks are active and healthy, this definitively steers the investigation away from WAN and firewall as root causes and toward the local access layer and DHCP/DNS configuration.

**Prompt 5 — Surface the DNS fault**
```
Are there any anomalies in my ThousandEyes tests?
```
*What to look for:* DNS resolution failures specifically for internal hostnames. The ThousandEyes DNS server test from the Mexico City agent will show the DHCP-assigned resolver failing to answer queries for internal domains while public DNS resolves normally. This explains the partial connectivity pattern completely.

**Follow-up correlation prompt**
```
The Mexico City C9300-X-Leaf-1 went unreachable after an overnight firmware upgrade. Can you describe its last known state and help me determine whether this is a device failure or a post-upgrade configuration issue?
```
*What to look for:* Last-seen timestamps, configuration state before and after the upgrade, and whether the device is physically reachable but management-unreachable (configuration loss) versus fully offline (hardware/power failure). The distinction matters for how the remediation is prioritised.

---

**The Three Fault Conditions**

| # | Fault | How it surfaces |
|---|---|---|
| 1 | Unreachable device | C9300-X-Leaf-1 absent from telemetry / offline in Cloud Control inventory since the maintenance window |
| 2 | Port not forwarding — access policy | Access port alert events post-upgrade; ports in policy-blocked or err-disabled state preventing user traffic |
| 3 | Misconfigured DNS | ThousandEyes DNS test: internal hostnames fail, public DNS resolves — DHCP scope points to wrong resolver |

---

**RCA Summary — Key Points**

- **The partial connectivity pattern is the key:** public internet works, internal resources do not. This pattern has exactly one explanation — DNS. The DHCP scope is pointing clients at a resolver that cannot answer internal queries.
- **The unreachable device:** The C9300-X-Leaf-1 went silent post-upgrade. The investigation should determine whether the device lost its management configuration (likely) versus a hardware failure (less likely given the timing). The distinction drives the remediation path.
- **The access policy fault:** A policy applied during or after the upgrade caused access ports to stop forwarding frames for affected users, compounding the outage beyond what DNS alone would explain.
- **Connecting thread:** All three faults share one contributing factor — the maintenance window closed without any post-upgrade verification. A verification checklist would have caught all three before business hours.

---

*Return to the challenge: [Appendix C — Scenario 2: Mexico City](../appendix-c-scenarios/)*
