#  (TEDC24) Unlock the Potential of Cisco’s Agentic Ops Framework

**Version:** 1.0 Draft  |  **Author:** Matt Okuma   |  **Date:** 2026-07-18  |  **Difficulty:** Intermediate  |  **Duration:** 60 min

**Tags:** agent-builder, cisco, ai-canvas, mcp, integrations, automation, cloud-control, studio

## Prerequisites

- Cisco SSO credentials and access to your Cloud Control tenant
- Admin Console access within your tenant
- API credentials for the third-party tools you want to connect (see Appendix A)

## Introduction

## The Vision: Cisco Cloud Control

Enterprise IT runs on specialized products, each built to solve a different operational challenge. Cisco has spent decades building deep capabilities across networking, security, compute, observability, and collaboration. That depth matters — but the hardest operational problems rarely stay within one product or IT domain. Issues spill across boundaries, context gets lost, and teams spend more time coordinating than resolving.

Cisco Cloud Control was built to change that. It connects the full Cisco estate and third-party systems into one unified operational environment, giving teams a single place to manage infrastructure, carry context across products, and move from issue to resolution — without giving up the specialized tools they already rely on.

As AI agents become a practical part of IT operations, teams will increasingly work alongside agents that investigate issues, recommend changes, and take action. This new operating model is **AgenticOps**. Cisco Cloud Control is the platform that makes it practical — providing the trusted access, live operational context, authorized tools, and safeguards that agents need to act with confidence.

Built on this foundation, **AI Canvas** brings operators and AI agents together to investigate and resolve cross-domain issues in real time. **Agent Builder** lets organizations build their own custom agents, encode their expertise, and connect the tools they already use — such as ServiceNow, Meraki, and more.

Cisco Cloud Control delivers three foundational capabilities:

- **Manage** — One control plane to manage the Cisco estate and connected third-party systems.
- **Resolve** — Find and fix issues across products and IT domains with shared operational context.
- **Extend** — Build custom apps and agents, connect existing tools, and add Cisco and ecosystem capabilities.

---

## What You Will Do in This Lab

In this hands-on lab you will experience Cisco Cloud Control end-to-end across its key platform areas:

1. **Explore the Platform** — Navigate Cisco Cloud Control and understand its capabilities across Platform Services, getting familiar with the unified operational environment.

2. **Discover Your Meraki Organization** — Connect to your Meraki org and explore the network infrastructure available in your POD, seeing how Cisco Cloud Control surfaces real device and topology context.

3. **Experience the Agentic AI Canvas** — Work with the AI Canvas to see how operators and AI agents collaborate to investigate and resolve cross-domain issues across your infrastructure.

4. **Build an Agent with Agent Builder** — Leverage a ServiceNow integration to construct a working AI agent from scratch, defining its tools, context, and behavior.

5. **Troubleshoot a Network Issue** — Diagnose and resolve a connectivity problem between the two switches in your POD, using the platform's operational context to identify root cause and take action.

## Learning Objectives

- Navigate to Agent Builder via the Cloud Control Studio interface
- Configure third-party integrations (ServiceNow, Atlassian, Infoblox, BlueCat) in Admin Console
- Verify integration connections and use them in AI Canvas with natural language queries
- Create an autonomous agent with a profile, trigger, and cadence
- Test an agent using the Test tab before promoting to production
- Promote, monitor, and manage agent versions in production

## Section 1: Explore the LAB and Cloud Control Capabilities

In this section, you will discover how Cloud Control streamlines the management of your cloud infrastructure through a centralized interface. You'll gain hands-on experience with its core monitoring, automation, and governance features to understand how they work together to simplify operations at scale.

### Step 1: Lab and Topoloy  Overview

<p>Review the assigned lab POD and network topology diagram provided in your lab guide. Note your POD number, device hostnames, IP addressing scheme, and the interconnections between devices, as these will be referenced throughout this lab.</p>

> **Expected Result:** <p>Your POD's network topology is understood. Each POD has two (2) dedicated 9300 Cloud Managed switches and multiple attached clients, providing a small but real-world branch site to work with.</p>

### Step 2: Logging into your assinged Cloud Control Tenant and exploring the Home Screen

<p>Open a web browser and navigate to <a href="https://cloud.cisco.com" rel="noopener noreferrer" target="_blank"><strong>https://cloud.cisco.com</strong></a>. Enter your provided credentials (username and password) and click <strong>Sign In</strong> to authenticate. Accept any authentication pop-ups.</p><p><strong>NOTE:</strong> If you are unable to locate your POD login credentials, please contact a proctor.</p>

> **Expected Result:** <p>You are successfully logged in to the Cloud Control tenant dashboard and have explored the home screen.</p>

### Step 3: Explore 9-Dot Menu

<p>Click the <strong>9-dot menu</strong> (grid icon) located in the top navigation bar of Cloud Control to explore the available options and applications.</p>

> **Expected Result:** <p>The 9-dot menu expands to display all available applications and navigation options within Cloud Control. You have explored the applications, products, and the option to pin items to the navigation banner.</p>

## Conclusion

You have now set up integrations, created and tested an agent, and promoted it to production. Use the Observability tab and Notifications pane to monitor ongoing agent runs. Refer to Appendix A for vendor-specific credential setup and Appendix B for the full list of available tools per integration. For issues not covered in the Troubleshooting section, contact your Cisco representative.
