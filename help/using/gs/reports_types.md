---
description: When customizing reports, the broad flexibility might create some questions as to the type of report that is best suited to get the data that you need.
keywords: mobile
seo-description: When customizing reports, the broad flexibility might create some questions as to the type of report that is best suited to get the data that you need.
seo-title: Report Types
solution: Marketing Cloud,Analytics
title: Report Types
topic: Reports,Metrics
uuid: 356c6910-1a6e-4f13-b4fb-bfcc529be6d4
index: y
internal: n
snippet: y
translate: y
---

# Report Types

Before customizing reports, you must understand the difference between a metric and a dimension. 

<table id="table_548AFD96D5724DAD9AD36B7F5317E33E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Item </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Metric </p> </td> 
   <td colname="col2"> <p>A metric is used to measure your data. </p> <p>Metrics are values that can be counted and added and are used to see how often specific actions occur in your app. Common metrics include installs, launches, revenue, lifetime value, and logins. For example, each time your app is launched, the <span class="term"> launches</span> value is increased by one. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dimension </p> </td> 
   <td colname="col2"> <p>A dimension is used to describe your data. </p> <p>Dimensions are represented by using a string, or a number that acts like a string (such as a postal code), and is used to organize and segment your data. Examples of common dimensions include OS version, campaign name, product name, and mobile carrier. Each dimension has a number of specific values that are associated with that dimension. For example, the OS version dimension has values such as "iOS 7" and "Android 4.1.2". </p> </td> 
  </tr> 
 </tbody> 
</table>

Here are the types of reports that you can generate in the Mobile UI: 

* [ Over-Time Report](../gs/reports_types.md#section_2741DA54C90C49AFB17C7B9BC7AD627D)
* [ Trended Report](../gs/reports_types.md#section_C9BE9A2EDBFF4D938B9AF14C8AA67883)
* [ Filtered Over-Time Reports](../gs/reports_types.md#section_F8FAF2A4496F449CA99EF1E052C71A2D)
* [ Ranked Reports](../gs/reports_types.md#section_C073D744A95843AF99EE74FB5B013735)
* [ Sunburst Report](../gs/reports_types.md#section_17A9842039174DE094A6B1E9837E35BB)
* [ Pathing Report](../gs/reports_types.md#section_AD400106BC684B50B27CCCD3F4497114)
* [ Funnel Report](../gs/reports_types.md#section_AF3B0C899D844FC3AD1F91A2C452C92F)

## Over-Time Report {#section_2741DA54C90C49AFB17C7B9BC7AD627D}

Over-time reports show how metrics are performing over a time range so you can quickly identify spikes and trends. Analysis often starts in an over-time report and moves into trended and ranked reports as you drill down to investigate the factors that might be contributing to a metric spike or trend. 

For example, if you see a spike in launches, you might run a trended report that shows launches for the top 5 operating systems to see which operating systems are contributing most to the spike in launches: 

<a id="fig_9CA190689C6141B080A8DF98C4CEBC6B"></a> ![](assets/overtime.png) 

To view dimension values with other metrics on an over-time report, you can use the instances metric and define a dimension filter. 

## Trended Report {#section_C9BE9A2EDBFF4D938B9AF14C8AA67883}

Trended reports help you see how your most popular dimensions are performing against a metric. You can use this report to determine which values are contributing most to a change in a metric. 

<a id="fig_89A9AFED46FC4CC58D9E63AFDE1F9E1A"></a> ![](assets/trended.png) 

To view a trended report for a dimension, add a sticky filter (for example, Operating System = iOS 6.0.1) to an over-time report to view the same data. As a bonus, you can add five additional metrics to the filtered over-time report. 

## Filtered Over-Time Reports {#section_F8FAF2A4496F449CA99EF1E052C71A2D}

If you have a specific dimension value that you want to view, you can add a sticky filter to an over-time report. The following report shows 30 days' worth of launches, upgrades, and crashes for a specific operating system version. 

<a id="fig_9522D1EA179843CFAA7658586F53D366"></a> ![](assets/overtime-filter.png) 

## Ranked Reports {#section_C073D744A95843AF99EE74FB5B013735}

Ranked reports show you how often the top 50 dimension contribute to a metric. This report is useful to view total contribution for a date range across a large number of values. 

<a id="fig_47EB8377C4854E7F85C6758B34BD6F41"></a> ![](assets/ranked.png) 

## Sunburst Report {#section_17A9842039174DE094A6B1E9837E35BB}

Sunburst reports provide, for example, the base report along with breakdowns. The visualization uses height to show the metric and the performance differences between the metrics. Each concentric circle represents an audience segment in the category for that circle. You can take actions on an audience, such as applying a Sticky Filter, hiding a metric, and viewing metrics. 

You can view the report an in-product tutorial that describes how to interact with a sunburst chart. 

To start the tutorial: 
1. in [!UICONTROL  Manage App Settings], click **[!UICONTROL  Usage]**.
1. Click **[!UICONTROL  Technology]** > **[!UICONTROL  Technology Breakdown]**.
1. In the title bar of the report, click **[!UICONTROL  Customize]**, and click the information icon  ![](assets/icon_information.png).


<a id="fig_A9C373DC024A46AE9C49795A6AD8431E"></a> ![](assets/report_technology.png) 

## Pathing Report {#section_AD400106BC684B50B27CCCD3F4497114}

A Pathing report is based on path analysis and displays a pathing chart that represents paths that are taken from one state in the app to another state. 

<a id="fig_A505D37AD0284196A807A34664B3C620"></a> ![](assets/action_paths.png) 

Each node is shaped like a box and represents a state in the users' paths though an app. For example, in the illustration above, the top node represents the number of users that launched the app and selected a photo from the gallery. 

## Funnel Report {#section_AF3B0C899D844FC3AD1F91A2C452C92F}

Funnel reports allow you to identify where customers abandon a marketing campaign or divert from a defined conversion path while interacting with your mobile app. You can also use the Funnel report to compare the actions of different segments. 

The funnel visualization lets you see where customers fall out of the process. Gaining visibility into customer decisions at each step helps you understand where customers are being deterred, what path they tend to follow, and when they leave your app. 

<a id="fig_2659F3DAB1FF40ED8F6346A71A4D0515"></a> ![](assets/funnel.png) 
