---
description: The Action Paths report is based on path analysis and displays a pathing chart that represents the paths that are taken from one state to another state in the app.
keywords: mobile
seo-description: The Action Paths report is based on path analysis and displays a pathing chart that represents the paths that are taken from one state to another state in the app.
seo-title: Action Paths
solution: Marketing Cloud,Analytics
title: Action Paths
topic: Reports,Metrics
uuid: a21e5d9e-fd57-4178-9d64-87181b7f988b
---

# Action Paths{#action-paths}

The Action Paths report is based on path analysis and displays a pathing chart that represents the paths that are taken from one state to another state in the app.

 Both the **[!UICONTROL View Paths]** and **[!UICONTROL Action Paths]** reports are pathing reports. The **[!UICONTROL View Paths]** report shows you how users navigate in your app from one screen to the next. The **[!UICONTROL View Actions]** report shows you the sequence of actions and events, such as clicks, selections, resizing, and so on, that users perform in your app.

>[!TIP]
>
>You can use a [funnel report](../usage/reports-funnel.md#concept_7FA67283442D428FA444B0706083F67E) to combine navigation and actions in one report.

![](assets/action_paths.png)

Each node, shaped like a box, represents a state in the users' paths though an app. For example, in the graphic above, the top node represents the number of users who launched the app and then picked a photo from the gallery.

To display the options to modify the chart, click a node and click **[!UICONTROL Focus]** or **[!UICONTROL Expand]**. For example, if you click the **[!UICONTROL PhotoPicked]** state in the top node, the **[!UICONTROL Focus]** and **[!UICONTROL Expand]** icons display.

![](assets/action_paths_icons.png)

To expand, click the **[!UICONTROL +]** icon. This option displays the additional paths that come into, or go out of, the node. In the graphic below, state 1 is launching the app, state 2 is picking a photo (the item you previously expanded), and state 3 includes the different paths users took:

* Selecting an item 
* Adding an item 
* Dragging an item 
* Scaling an item

Expanding a state is similar to a funnel.

![](assets/action_paths_expand.png)

To isolate the node and show paths that come into, and go out of the selected node, click the  ![](assets/icon_focus.png) icon. In the graphic below, the following paths were completed **before** users selected a photo:

* Rotating an item 
* Scaling an item 
* Dragging an item 
* Removing an item

Of the users who selected a photo, the following paths were completed **after** the photo was selected:

* Selecting an item 
* Adding an item 
* Dragging an item 
* Scaling an item

![](assets/action_paths_focus.png)

You can focus or expand multiple nodes to get a detailed view of paths users take in your app. For example:

![](assets/action_paths_mult.png)

You can configure the following options for this report:

<table id="table_1F79804A6A0240A98CB73A6EBE7F1068"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Option </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="uicontrol"> Time Period</span> </p> </td> 
   <td colname="col2"> <p>Click the <span class="uicontrol"> Calendar</span> icon to select a custom period or to select a preset time period from the drop-down list. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="uicontrol"> Customize</span> </p> </td> 
   <td colname="col2"> <p>Customize your reports by changing the <span class="uicontrol"> Show By</span> options, adding metrics and filters, and adding additional series (metrics), and more </p> <p>For more information, see <a href="../usage/reports-customize/reports-customize.md#concept_ED099E16594044E69FFD91829F436907" format="dita" scope="local"> Customize Reports</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="uicontrol"> Filter</span> </p> </td> 
   <td colname="col2"> <p>Click <span class="uicontrol"> Filter</span> to create a filter that spans different reports to see how a segment is performing across all mobile reports. A sticky filter allows you to define a filter that is applied to all non-pathing reports. </p> <p>For more information, see <a href="../usage/reports-customize/t-sticky-filter.md#task_75B0AD4D58014BB0A5A09FE1B074ECE1" format="dita" scope="local"> Add Sticky Filter</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="uicontrol"> Download</span> </p> </td> 
   <td colname="col2"> <p>Click <span class="uicontrol"> PDF</span> or <span class="uicontrol"> CSV</span> to download or open documents and share with users who do not have access to Mobile Services or to use it in presentations. </p> </td> 
  </tr> 
 </tbody> 
</table>

