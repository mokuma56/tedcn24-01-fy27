# Section 1: Explore the LAB and Cloud Control Capabilities

In this section, you will discover how Cloud Control streamlines the management of your cloud infrastructure through a centralized interface. You'll gain hands-on experience with its core monitoring, automation, and governance features to understand how they work together to simplify operations at scale.

## Step 1: Lab and Topoloy  Overview

<p>Review the assigned lab POD and network topology diagram provided in your lab guide. Note your POD number, device hostnames, IP addressing scheme, and the interconnections between devices, as these will be referenced throughout this lab.</p>

![](../screenshots/capture-65158d7c.png)

## Step 2: Logging into your assinged Cloud Control Tenant and exploring the Home Screen

<p>Open a web browser and navigate to <a href="https://cloud.cisco.com" rel="noopener noreferrer" target="_blank"><strong>https://cloud.cisco.com</strong></a>. Enter your provided credentials (username and password) and click <strong>Sign In</strong> to authenticate. Accept any authentication pop-ups.</p><p><strong>NOTE:</strong> If you are unable to locate your POD login credentials, please contact a proctor.</p>

![](../screenshots/capture-f706efe4.png)

Once you are logged in successfully explore the (3) sections listed below on the home screen:

1. The selected Organization — if you have access to more than one organization, you can easily switch between them.
2. The AI Assistant, which serves as your natural language interface to the platform. Feel free to explore the pre-built prompts and run some queries.
NOTE: This is a lab environment, so data is limited and you may not see real-world results.

3.The Actions section, which highlights any actions required in your environment. Take note of any actions that are displayed. You can engage with these actions agentically, which will be covered in detail later.

![](../screenshots/capture-91b7aa81.png)

## Step 3: Explore 9-Dot Menu

<p>Click the <strong>9-dot menu</strong> (grid icon) located in the top navigation bar of Cloud Control to explore the available options and applications.</p>

![](../screenshots/capture-6f4e152f.png)

<p>Explore&nbsp;the&nbsp;(3)&nbsp;Main&nbsp;sections&nbsp;available:&nbsp;</p><p>1.&nbsp;Platform&nbsp;Services:&nbsp;These&nbsp;are&nbsp;the&nbsp;services&nbsp;which&nbsp;sit&nbsp;across&nbsp;the&nbsp;entire&nbsp;infrastructure.&nbsp;We&nbsp;will&nbsp;be&nbsp;exploring&nbsp;each&nbsp;of&nbsp;these&nbsp;in&nbsp;more&nbsp;detail.&nbsp;These&nbsp;services&nbsp;will&nbsp;continue&nbsp;to&nbsp;expand,&nbsp;with&nbsp;things&nbsp;like&nbsp;Fabric&nbsp;etc..&nbsp;</p><p>2.&nbsp;Products:&nbsp;These&nbsp;are&nbsp;the&nbsp;Products&nbsp;that&nbsp;are&nbsp;currently&nbsp;integrated&nbsp;with&nbsp;our&nbsp;Tenant.&nbsp;In&nbsp;our&nbsp;case&nbsp;of&nbsp;the&nbsp;lab,&nbsp;we&nbsp;only&nbsp;have&nbsp;Meraki&nbsp;integrated.&nbsp;Normally&nbsp;you&nbsp;would&nbsp;have&nbsp;multiple&nbsp;products&nbsp;integrated.&nbsp;For&nbsp;a&nbsp;full&nbsp;list&nbsp;of&nbsp;supported&nbsp;products&nbsp;and&nbsp;on-boarding&nbsp;requirements&nbsp;please&nbsp;visit&nbsp;the&nbsp;Cloud&nbsp;Control&nbsp;On-Boarding&nbsp;Sharepoint&nbsp;site&nbsp;<a href="https://cisco.sharepoint.com/sites/CiscoCloudControl-ControlledAvailability/SitePages/Home.aspx" rel="noopener noreferrer" target="_blank">Here</a>&nbsp;</p><p>3.&nbsp;The&nbsp;Favorites&nbsp;Section:&nbsp;In&nbsp;this&nbsp;section&nbsp;you&nbsp;can&nbsp;save&nbsp;pages&nbsp;in&nbsp;your&nbsp;products&nbsp;that&nbsp;you&nbsp;frequently&nbsp;visit,&nbsp;so&nbsp;you&nbsp;can&nbsp;quickly&nbsp;navigate&nbsp;to&nbsp;them.&nbsp;</p>

!!! note ""
    Practice clicking a Platform Service or Product. You will see it Pinned to the navigation bar. This navigation bar will stay consitent no matter where you navigate within Cloud Control making for quick and easy navigation.

![](../screenshots/capture-eb82ce39.png)

## Step 4: Explore Inventory Capabilities

<p>First,&nbsp;navigate&nbsp;to&nbsp;the&nbsp;Inventory&nbsp;section&nbsp;of&nbsp;Cisco&nbsp;Cloud&nbsp;Control.</p>

![](../screenshots/capture-a4548035.png)

<p>⠿Next,&nbsp;Explore&nbsp;the&nbsp;available&nbsp;capabilities.&nbsp;Review&nbsp;the&nbsp;Inventory&nbsp;Insights&nbsp;dashboard&nbsp;to&nbsp;examine&nbsp;detected&nbsp;issues,&nbsp;recommendations,&nbsp;and&nbsp;asset&nbsp;visibility&nbsp;across&nbsp;your&nbsp;managed&nbsp;devices.&nbsp;</p>

![](../screenshots/capture-8620480a.png)

<p>Click&nbsp;on&nbsp;show&nbsp;device&nbsp;inventory&nbsp;or&nbsp;change&nbsp;the&nbsp;view&nbsp;.&nbsp;</p>

![](../screenshots/capture-112100bd.png)

<p>Begin&nbsp;by&nbsp;practicing&nbsp;the&nbsp;use&nbsp;of&nbsp;the&nbsp;AI-assisted&nbsp;search&nbsp;functionality&nbsp;within&nbsp;the&nbsp;Inventory&nbsp;section.&nbsp;Work&nbsp;collaboratively&nbsp;with&nbsp;your&nbsp;team&nbsp;to&nbsp;explore&nbsp;and&nbsp;discuss&nbsp;the&nbsp;available&nbsp;Inventory&nbsp;capabilities,&nbsp;including&nbsp;filtering,&nbsp;sorting,&nbsp;and&nbsp;device&nbsp;categorization&nbsp;options.</p><p></p><p>Next,&nbsp;locate&nbsp;your&nbsp;two&nbsp;(2)&nbsp;dedicated&nbsp;switches&nbsp;within&nbsp;the&nbsp;Inventory&nbsp;list&nbsp;and&nbsp;click&nbsp;on&nbsp;one&nbsp;to&nbsp;select&nbsp;it.</p><p></p><p>Observe&nbsp;the&nbsp;device&nbsp;details&nbsp;panel&nbsp;that&nbsp;opens&nbsp;along&nbsp;the&nbsp;right&nbsp;side&nbsp;of&nbsp;the&nbsp;screen.&nbsp;This&nbsp;panel&nbsp;displays&nbsp;comprehensive&nbsp;information&nbsp;for&nbsp;your&nbsp;<strong>C9300-X-X</strong>,&nbsp;your&nbsp;Cisco&nbsp;Catalyst&nbsp;C9300&nbsp;switch.&nbsp;</p><p></p><p>Review&nbsp;the&nbsp;<strong>General</strong>&nbsp;tab,&nbsp;which&nbsp;presents&nbsp;a&nbsp;high-level&nbsp;device&nbsp;Overview&nbsp;including&nbsp;key&nbsp;operational&nbsp;indicators&nbsp;such&nbsp;as&nbsp;a&nbsp;Reachability&nbsp;status&nbsp;of&nbsp;<em>Reachable</em>&nbsp;—&nbsp;confirming&nbsp;the&nbsp;device&nbsp;is&nbsp;actively&nbsp;communicating&nbsp;with&nbsp;the&nbsp;management&nbsp;platform&nbsp;—&nbsp;and&nbsp;a&nbsp;Compliance&nbsp;status&nbsp;of&nbsp;<em>Compliant</em>,&nbsp;indicating&nbsp;that&nbsp;the&nbsp;device&nbsp;configuration&nbsp;meets&nbsp;the&nbsp;defined&nbsp;policy&nbsp;standards&nbsp;for&nbsp;your&nbsp;organization.</p><p></p><p>Once&nbsp;you&nbsp;have&nbsp;reviewed&nbsp;the&nbsp;device&nbsp;details,&nbsp;click&nbsp;the&nbsp;<strong>View&nbsp;in&nbsp;Meraki</strong>&nbsp;button&nbsp;located&nbsp;in&nbsp;the&nbsp;bottom-right&nbsp;corner&nbsp;of&nbsp;the&nbsp;details&nbsp;panel.&nbsp;</p>

![](../screenshots/capture-1ead1250.png)

<p>This&nbsp;action&nbsp;launches&nbsp;the&nbsp;Meraki&nbsp;Dashboard&nbsp;directly&nbsp;in&nbsp;context&nbsp;for&nbsp;the&nbsp;selected&nbsp;device,&nbsp;illustrating&nbsp;the&nbsp;seamless&nbsp;cross-platform&nbsp;navigation&nbsp;capability&nbsp;within&nbsp;Cisco&nbsp;Cloud&nbsp;Control.&nbsp;</p><p></p><p>This&nbsp;integration&nbsp;allows&nbsp;network&nbsp;administrators&nbsp;to&nbsp;move&nbsp;fluidly&nbsp;between&nbsp;unified&nbsp;inventory&nbsp;management&nbsp;and&nbsp;platform-specific&nbsp;dashboards&nbsp;without&nbsp;the&nbsp;need&nbsp;to&nbsp;separately&nbsp;log&nbsp;in&nbsp;or&nbsp;search&nbsp;for&nbsp;the&nbsp;device&nbsp;within&nbsp;Meraki.</p><p></p><p>Notice&nbsp;the&nbsp;top&nbsp;navigation&nbsp;bar&nbsp;highlights&nbsp;the&nbsp;unified&nbsp;Cloud&nbsp;Control&nbsp;interface,&nbsp;click&nbsp;Home&nbsp;to&nbsp;quickly&nbsp;return&nbsp;to&nbsp;the&nbsp;Cloud&nbsp;Control&nbsp;home&nbsp;screen.&nbsp;You&nbsp;can&nbsp;actually&nbsp;click&nbsp;any&nbsp;element&nbsp;on&nbsp;the&nbsp;banner&nbsp;and&nbsp;quickly&nbsp;navigate&nbsp;to&nbsp;it.&nbsp;These&nbsp;tabs&nbsp;allow&nbsp;you&nbsp;to&nbsp;seamlessly&nbsp;navigate&nbsp;between&nbsp;management&nbsp;planes&nbsp;within&nbsp;a&nbsp;single&nbsp;dashboard.</p><p></p>

![](../screenshots/capture-2c0815ed.png)

<p>Next&nbsp;from&nbsp;top&nbsp;navigation&nbsp;banner&nbsp;click&nbsp;topology.</p>

![](../screenshots/capture-eefe5d44.png)

<p>Topology&nbsp;shows&nbsp;you&nbsp;your&nbsp;Global&nbsp;topology&nbsp;by&nbsp;site</p>

![](../screenshots/capture-d940b575.png)

!!! note ""
    <p>Congratulations&nbsp;on&nbsp;completing&nbsp;this&nbsp;section!&nbsp;You&nbsp;have&nbsp;successfully&nbsp;learned&nbsp;how&nbsp;to&nbsp;navigate&nbsp;the&nbsp;Cisco&nbsp;Cloud&nbsp;Control&nbsp;Platform&nbsp;and&nbsp;have&nbsp;gained&nbsp;hands-on&nbsp;experience&nbsp;with&nbsp;several&nbsp;of&nbsp;its&nbsp;core&nbsp;platform&nbsp;services.&nbsp;Specifically,&nbsp;you&nbsp;explored&nbsp;how&nbsp;to&nbsp;leverage&nbsp;the&nbsp;AI&nbsp;Assistant&nbsp;to&nbsp;streamline&nbsp;troubleshooting&nbsp;and&nbsp;accelerate&nbsp;decision-making,&nbsp;how&nbsp;to&nbsp;use&nbsp;the&nbsp;Inventory&nbsp;service&nbsp;to&nbsp;discover,&nbsp;organize,&nbsp;and&nbsp;manage&nbsp;network&nbsp;assets&nbsp;across&nbsp;your&nbsp;environment,&nbsp;and&nbsp;how&nbsp;to&nbsp;utilize&nbsp;the&nbsp;Topology&nbsp;service&nbsp;to&nbsp;visualize&nbsp;network&nbsp;relationships&nbsp;and&nbsp;understand&nbsp;the&nbsp;interconnections&nbsp;between&nbsp;devices&nbsp;and&nbsp;services.&nbsp;These&nbsp;foundational&nbsp;skills&nbsp;will&nbsp;serve&nbsp;as&nbsp;building&nbsp;blocks&nbsp;as&nbsp;you&nbsp;progress&nbsp;through&nbsp;the&nbsp;remaining&nbsp;sections&nbsp;of&nbsp;this&nbsp;lab.</p>
