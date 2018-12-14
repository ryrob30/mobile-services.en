---
description: You can configure audience options for in-app messages, including view, trigger, and trait options.
keywords: mobile
seo-description: You can configure audience options for in-app messages, including view, trigger, and trait options.
seo-title: Audience  In-App Message
solution: Marketing Cloud,Analytics
title: Audience  In-App Message
topic: Metrics
uuid: 6c815d4c-7626-4cf4-9158-3f059c79317a
index: y
internal: n
snippet: y
---

# Audience: In-App Message{#audience-in-app-message}

You can configure audience options for in-app messages, including view, trigger, and trait options.

1. In your app, click **[!UICONTROL Messaging]** > **[!UICONTROL Manage Messages]** > **[!UICONTROL Create Message]** > **[!UICONTROL Create In-App]**. 
1. On the [!DNL Audience] page, type information in the following fields:

<table id="table_57E4D9BE2D6B473899F30F5B512E4F94"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Field </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="uicontrol"> View </span> </p> </td> 
   <td colname="col2"> <p>Select the option that triggers a message to display: </p> <p> 
     <ul id="ul_C0EC9D84402F415FA92432C068E7D0AE"> 
      <li id="li_8763B65E5BFC45A28DEE138CE03CE44B"> <p><b>Always</b> </p> <p>This option means that the message is displayed each time the trigger occurs. </p> </li> 
      <li id="li_D66F86838138481FA818F6B51DE67898"> <p> <b>Once</b> </p> <p>This option means that the message is displayed only the first time the trigger occurs. </p> </li> 
      <li id="li_D2C2C59C4C934FD5BAA161128DB997B4"> <p><b>Until Click-Through</b> </p> <p>This option means that means that the message is displayed each time the trigger occurs until the user clicks through. This trigger applies only to full screen and alert messages. </p> </li> 
     </ul> </p> <p>Most messages need to redirect or use a resource from the internet and will not display if offline. To always show the message regardless of network connectivity, select the <span class="uicontrol"> Show Offline</span> check box. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="uicontrol"> Trigger </span> </p> </td> 
   <td colname="col2"> <p>Select an option from the drop-down list and select a condition. </p> <p>For example, you could select <span class="uicontrol"> Launched</span> from the first drop-down list and <span class="uicontrol"> Exists</span> from the second drop-down list. </p> <p>You can also specify custom context data that needs to be in the triggering hit to display the message. </p> <p> <p>Important:  If you select multiple triggers, for the message to display, all triggers must occur on the same hit. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="uicontrol"> Traits </span> </p> </td> 
   <td colname="col2"> <p>You can determine who should see the in-app message when it is triggered and filter (segment) the audience to hits that have specified data. </p> <p>For example, you can define a rule in which Points of Interest contain Denver. This filter allows you to show the message to customers that are in one of your points of interest with Denver in the name, at the trigger time. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Additional Information about Traits and Triggers {#section_48C39EFB8CAA4F62B994FCC91DF588E6}

>[!IMPORTANT]
>
>Triggers and traits use data that is passed to Analytics from your app. These values are passed as context data, mapped variables, and metrics. A variable is a text-based value, and a metric is a numerical value.

To see the mapping of these key value pairs in the Mobile Services UI and validate the value for your trigger, click **[!UICONTROL Manage App Settings]** > **[!UICONTROL Manage Variables & Metrics]** , which displays the following tabs:

* **[!UICONTROL Standard Variables & Metrics]** 
* **[!UICONTROL Custom Variables]** 
* **[!UICONTROL Custom Metrics]**

After you validate the mapping, select the appropriate matcher or logical operator to configure your audience for the message.

### Selecting Metrics and Variables {#example_AB126F03BD1C4094B791E230B3DB1189}

![](assets/custom_trigger_matcher_options.png)

The following scenarios help you determine whether you should select a metric or a variable as your trigger:

**Metrics**

A metric is a number, and an example is the number of purchases.

1. Click **[!UICONTROL Manage Messages]** > **[!UICONTROL Create Message]**. 
1. Complete the following steps in the **[!UICONTROL Trigger]** section on the **[!UICONTROL Audience]** tab:

    1. Select a standard event such as **[!UICONTROL Launched]** and select **[!UICONTROL exists]**. 
    
    1. Select a second trigger that is a custom data point and that is mapped to a metric. 
    1. Under **[!UICONTROL Number]**, select a matcher option.

**Variables**

A variable is a text string that is a unique identifier, and examples include country, airport, and so on.

1. Click **[!UICONTROL Manage Messages]** > **[!UICONTROL Create Message]**. 
1. Complete the following steps in the **[!UICONTROL Trigger]** section on the **[!UICONTROL Audience]** tab:

    1. Select a standard event such as **[!UICONTROL Launched]** and select **[!UICONTROL exists]**. 
    
    1. Select a second trigger that is a custom data point and that is mapped to a variable. 
    1. Under **[!UICONTROL Text]**, select a matcher option.

For more information about context data, variables, and metrics, see [Managing your App](https://marketing.adobe.com/resources/help/en_US/mobile/c_mob_manage-app.html). 
