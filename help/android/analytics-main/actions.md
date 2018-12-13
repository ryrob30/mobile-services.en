---
description: Actions are the events that occur in your Android app that you want to measure.
seo-description: Actions are the events that occur in your Android app that you want to measure.
seo-title: Track App Actions
solution: Marketing Cloud,Analytics
title: Track App Actions
topic: Developer and implementation
uuid: fe01c1df-f6bb-4b32-b3ef-959d2c724af6
index: y
internal: n
snippet: y
---

# Track App Actions {#track-app-actions}

Actions are the events that occur in your Android app that you want to measure.

<a id="section_6DCAFC20F3444CFF9848C1D66E73BD5C"></a>

Each action has one or more corresponding metrics that are incremented each time the event occurs. For example, you might send a `trackAction` call for each new subscription, each time an article is viewed, or each time a level is completed. Actions are not tracked automatically, so you must call `trackAction` when an event that you want to track occurs, and map the action to a custom event.

## Tracking Actions {#section_380DF56C4EE4432A823940E4AE4C9E91}

1. Add the [library to your project and implement lifecycle](../getting-started/dev-qs.md#concept_13176B6E37F547D6935E37125F457972). 
1. Import the library: 

   ```java
   import com.adobe.mobile.*;
   ```

1. When the action that you want to track occurs in your app, call `trackAction` to send a hit for this action: 

   ```java
   Analytics.trackAction("myapp.ActionName", null);
   ```

1. In the Adobe Mobile Services UI, select your app and click **[!UICONTROL Manage App Settings]**. 
1. Click **[!UICONTROL Manage Variables and Metrics]** and click the **[!UICONTROL Custom Metrics]** tab. 

1. Map the context data name that is defined in your code, for example, `myapp.ActionName`, to a custom event.

   <a id="fig_8129BD79A67F4E18A32DD5DE89F73AFA"></a>

   ![](assets/map-event-context-data.png)

You can also set a prop to hold all action values by mapping a custom prop with a name like **[!UICONTROL Custom Actions]** and setting the value to `a.action`.

![](assets/map-custom-prop.png)

## Sending Additional Data {#section_3EBE813E54A24F6FB669B2478B5661F9}

In addition to the action name, you can send additional context data with each track action call:

```java
HashMap<String, Object> exampleContextData = new HashMap<String, Object>(); 
exampleContextData.put("myapp.social.SocialSource", "Twitter"); 
Analytics.trackAction("myapp.SocialShare", exampleContextData);
```

Context data values must be mapped to custom variables in [Adobe Mobile services](https://mobilemarketing.adobe.com):

<a id="fig_1E995262EA99453EB03E76B4DAD83CA2"></a>

![](assets/map-variable-context-action.png)

## Action Reporting {#section_0F6A54AB7A3F42C9BB042D86A0FC4630}

<table id="table_1715AF0A897C40A39604500C6ABFBFE6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Interface </th> 
   <th colname="col2" class="entry"> Report </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Adobe Mobile Services </td> 
   <td colname="col2"> <p> <span class="uicontrol"> Action Paths </span> report. </p> <p>View the order in which actions occur in your app. You can also click <span class="uicontrol"> Customize </span> on any report to view actions ranked, trended, or in a breakdown report or apply a filter to view actions for a specific segment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Marketing reports &amp; analytics </td> 
   <td colname="col2"> <p> <span class="uicontrol"> Custom Event </span> report. </p> <p>After an action is mapped to a custom event, you can view mobile events similar to all other Analytics events. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ad hoc analytics </td> 
   <td colname="col2"> <p> <span class="uicontrol"> Custom Event </span> report. </p> <p>After an action is mapped to a custom event, you can view mobile events similar to all other Analytics events. </p> </td> 
  </tr> 
 </tbody> 
</table>

