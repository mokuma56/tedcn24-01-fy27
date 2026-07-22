# Appendix A: Validated AI Prompts

## Step 1: Known-Good Prompts for AI Assistant and Agentic Canvas



This appendix contains a curated collection of **known-good prompts** that have been tested and validated within this lab environment. These prompts are designed to be used directly with the **AI Assistant** or the **AI Agentic Canvas** inside Cisco Cloud Control to produce high-quality, actionable results.

Throughout the lab, you will find references back to this appendix for relevant prompts at each stage. You are encouraged to use these prompts as a starting point — experiment with variations, combine them, or use them as inspiration for building your own agentic workflows. The more you interact with the AI interfaces using well-formed prompts, the richer the outputs you will receive.

Prompts are organized by product integration so you can quickly locate the right prompt for the context you are working in.

### Meraki Dashboard

```
How is my organization doing?
```

```
Are there any critical alerts?
```

```
Show my WAN port utilization.
```

```
Show my WAN port status.
```

```
SD-WAN uplink/WAN port status across your fabric
```

```
Meraki appliance uplink status for the Mexico City network
```

```
yes please pull real-time client usage data directly from Meraki for that network
```

### ThousandEyes

```
Are there any outages affecting my monitored services right now?
```

```
What are the current latency and packet loss metrics for my critical tests?
```

```
Are there any anomalies in my ThousandEyes tests?
```

### Nexus Dashboard

```
Is my data center fabric healthy right now?
```

```
Give me an overall health summary of my data center fabrics.
```

```
Are there any critical issues across my data center fabrics?
```

```
Which fabric components need attention today?
```

```
Show me a health overview of all fabrics managed by Nexus Dashboard.
```

### Hyperfabric

```
Show me all devices discovered in my Nexus Hyperfabric organization.
```

```
Are any devices in my fabric unable to communicate?
```

```
Are there any reachability issues between endpoints in my fabric?
```

```
Show me all endpoints currently connected to my fabric and their locations.
```

```
Show me the topology of my Nexus Hyperfabric deployment.
```

```
Can I add any connections to my fabrics?
```

### Intersight

```
Which servers are running the oldest firmware version?
```

```
Are there any storage drives in a degraded or failed state?
```

```
List all servers with inactive or disconnected network adapters.
```

```
Who made changes to my server profiles in the last 24 hours?
```

```
Give me an overall health summary of my compute infrastructure.
```

### Secure Access

```
why can lee chang not access jira via ZTA in secure access?
```

### Secure Firewall

```
What is the current status of all my site-to-site VPN tunnels?
```

```
Are there any IKE negotiation failures on my VPN tunnels?
```

```
Which tunnels have had the most disruptions this month?
```

```
What are the best practices for site-to-site VPN configuration?
```

### Catalyst SD-WAN

```
Give me a summary of my network and application health.
```

```
Give me a summary of my SD-WAN network and application health.
```

```
Can you show the Rx/Tx bandwidth rates, utilization, and peak usage for all my WAN links?
```

```
How are my applications performing, and are there any SLA violations in my SD-WAN network?
```

```
What is the usage of applications in my SD-WAN network?
```

```
Give me an overall health summary of my Catalyst SD-WAN deployment.
```

### Cisco Collaboration Hub

```
Show me poor quality meetings for Dace Waters
```

```
can you diagnose why the device called Jane Rodriquez DM had issues in its last meeting. Conference ID 721823729975301029. Please provide the ThousandEyes network path as well.
```

```
Show me calls with poor quality for Victoria Price
```

```
Analyze calls in the last 7 days for device Michael Chang 9871
```

```
Tell me about the last meeting in the SJC Conf Room
```

### Splunk Cloud

```
How is the health of my Splunk deployment?
```

```
What is the p95 latency per Splunk service for the last 24 hours?
```

```
Summarize any alerts from our Splunk system
```

```
Show any failed Splunk login attempts in the last 24 hours grouped by user
```
