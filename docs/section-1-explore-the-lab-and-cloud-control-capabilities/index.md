# Section 1: Explore the LAB and Cloud Control Capabilities

In this section, you will discover how Cloud Control streamlines the management of your cloud infrastructure through a centralized interface. You'll gain hands-on experience with its core monitoring, automation, and governance features to understand how they work together to simplify operations at scale.

## Step 1: Lab and Topoloy  Overview

Review the assigned lab POD and network topology diagram provided in your lab guide. Note your POD number, device hostnames, IP addressing scheme, and the interconnections between devices, as these will be referenced throughout this lab.

![](../screenshots/capture-65158d7c.png)

## Step 2: Logging into your assinged Cloud Control Tenant and exploring the Home Screen

Open a web browser and navigate to [**https://cloud.cisco.com**](https://cloud.cisco.com). Enter your provided credentials (username and password) and click **Sign In** to authenticate. Accept any authentication pop-ups.

**NOTE:** If you are unable to locate your POD login credentials, please contact a proctor.

![](../screenshots/capture-f706efe4.png)

Once you are logged in successfully explore the (3) sections listed below on the home screen:

1. The selected Organization — if you have access to more than one organization, you can easily switch between them.
2. The AI Assistant, which serves as your natural language interface to the platform. Feel free to explore the pre-built prompts and run some queries.
NOTE: This is a lab environment, so data is limited and you may not see real-world results.

3.The Actions section, which highlights any actions required in your environment. Take note of any actions that are displayed. You can engage with these actions agentically, which will be covered in detail later.

![](../screenshots/capture-91b7aa81.png)

## Step 3: Explore 9-Dot Menu

Click the **9-dot menu** (grid icon) located in the top navigation bar of Cloud Control to explore the available options and applications.

![](../screenshots/capture-6f4e152f.png)

Explore the (3) Main sections available: 

1. Platform Services: These are the services which sit across the entire infrastructure. We will be exploring each of these in more detail. These services will continue to expand, with things like Fabric etc.. 

2. Products: These are the Products that are currently integrated with our Tenant. In our case of the lab, we only have Meraki integrated. Normally you would have multiple products integrated. For a full list of supported products and on-boarding requirements please visit the Cloud Control On-Boarding Sharepoint site [Here](https://cisco.sharepoint.com/sites/CiscoCloudControl-ControlledAvailability/SitePages/Home.aspx) 

3. The Favorites Section: In this section you can save pages in your products that you frequently visit, so you can quickly navigate to them.

!!! note ""
    Practice clicking a Platform Service or Product. You will see it Pinned to the navigation bar. This navigation bar will stay consitent no matter where you navigate within Cloud Control making for quick and easy navigation.

![](../screenshots/capture-eb82ce39.png)

## Step 4: Explore Inventory Capabilities

First, navigate to the Inventory section of Cisco Cloud Control.

![](../screenshots/capture-a4548035.png)

Next, Explore the available capabilities. Review the Inventory Insights dashboard to examine detected issues, recommendations, and asset visibility across your managed devices.

![](../screenshots/capture-8620480a.png)

Click on show device inventory or change the view .

![](../screenshots/capture-112100bd.png)

Begin by practicing the use of the AI-assisted search functionality within the Inventory section. Work collaboratively with your team to explore and discuss the available Inventory capabilities, including filtering, sorting, and device categorization options.

Next, locate your two (2) dedicated switches within the Inventory list and click on one to select it.

Observe the device details panel that opens along the right side of the screen. This panel displays comprehensive information for your **C9300-X-X**, your Cisco Catalyst C9300 switch. 

Review the **General** tab, which presents a high-level device Overview including key operational indicators such as a Reachability status of *Reachable* — confirming the device is actively communicating with the management platform — and a Compliance status of *Compliant*, indicating that the device configuration meets the defined policy standards for your organization.

Once you have reviewed the device details, click the **View in Meraki** button located in the bottom-right corner of the details panel.

![](../screenshots/capture-1ead1250.png)

This action launches the Meraki Dashboard directly in context for the selected device, illustrating the seamless cross-platform navigation capability within Cisco Cloud Control. 

This integration allows network administrators to move fluidly between unified inventory management and platform-specific dashboards without the need to separately log in or search for the device within Meraki.

Notice the top navigation bar highlights the unified Cloud Control interface, click Home to quickly return to the Cloud Control home screen. You can actually click any element on the banner and quickly navigate to it. These tabs allow you to seamlessly navigate between management planes within a single dashboard.

![](../screenshots/capture-2c0815ed.png)

Next from top navigation banner click topology.

![](../screenshots/capture-eefe5d44.png)

Topology shows you your Global topology by site

![](../screenshots/capture-d940b575.png)

!!! note ""
    Congratulations on completing this section! You have successfully learned how to navigate the Cisco Cloud Control Platform and have gained hands-on experience with several of its core platform services. Specifically, you explored how to leverage the AI Assistant to streamline troubleshooting and accelerate decision-making, how to use the Inventory service to discover, organize, and manage network assets across your environment, and how to utilize the Topology service to visualize network relationships and understand the interconnections between devices and services. These foundational skills will serve as building blocks as you progress through the remaining sections of this lab.
