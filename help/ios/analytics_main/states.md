---
description: States are the different screens or views in your application. Each time a new state is displayed in your application, for example, when a user navigates from the home page to the news feed, a track state call should be sent. In iOS, a state is typically tracked in the viewDidLoad method of each view.
seo-description: States are the different screens or views in your application. Each time a new state is displayed in your application, for example, when a user navigates from the home page to the news feed, a track state call should be sent. In iOS, a state is typically tracked in the viewDidLoad method of each view.
seo-title: Track App States
solution: Marketing Cloud,Analytics
title: Track App States
topic: Developer and implementation
uuid: 0e5d0dcc-c013-4e4a-abd8-ce0c114a672a
index: y
internal: n
snippet: y
translate: y
---

# Track App States


<a id="section_845C9DB2F9C34428BB679C9BB612855A"></a>


>[!TIP]
>
>To track states, make a call to ` trackState`. States are not automatically tracked. 



## Tracking States {#section_380DF56C4EE4432A823940E4AE4C9E91}


1. Add the [ library to your project and implement lifecycle ](../getting_started/dev_qs.md#concept_13176B6E37F547D6935E37125F457972).
1. Import the library. 
   ```
   #import "ADBMobile.h"
   ```


1. Call ` trackState` to send a hit for this state view. 
   ```
   [ADBMobile trackState:@"Login Screen"  
                    data:nil];
   ```




In Adobe Mobile services, the **[!UICONTROL  State Name]** is reported in the *` View State`* variable, and a view is recorded for each ` trackState` call. In other Analytics interfaces, **[!UICONTROL  View State]** is reported as **[!UICONTROL  Page Name]**, and state views is reported as page views. 

## Sending Additional Data {#section_CFDB4F944496401786A145C209AB387C}

In addition to the **[!UICONTROL  State Name]**, you can send additional context data with each track action call: 

```
NSMutableDictionary *contextData = [NSMutableDictionary dictionary]; 
[contextData setObject:@"logged in" forKey:@"myapp.login.LoginStatus"]; 
[ADBMobile trackState:@"Home Screen" data:contextData];
```
Context data values must be mapped to custom variables in [ Adobe Mobile services ](https://mobilemarketing.adobe.com): 
![](assets/map-variable-context-state.png) 
## App State Reporting {#section_0F6A54AB7A3F42C9BB042D86A0FC4630}

States are typically viewed by using a pathing report so you can see how users navigate your app and which states are viewed most. 



<table id="table_1715AF0A897C40A39604500C6ABFBFE6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry"> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Adobe Mobile Services </td> 
   <td colname="col2"> <p>The <b>View States</b> report. </p> <p>This report is based on the paths that the users took through your application. For example, after you log in, click 
     <ignoretag> 
      <span class="uicontrol"> Home </span>  &gt; 
      <span class="uicontrol"> Settings </span>  &gt; 
      <span class="uicontrol"> Feed </span> 
     </ignoretag>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Adobe Analytics </td> 
   <td colname="col2"> States can be viewed anywhere that <span class="uicontrol"> Pages </span> can be viewed, such as the <span class="uicontrol"> Pages </span> report, the <span class="uicontrol"> Page Views </span> report, and the <span class="uicontrol"> Path </span> report. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ad hoc analytics </td> 
   <td colname="col2"> States can be viewed anywhere <span class="uicontrol"> Pages </span> can be viewed using the <b></b> <span class="uicontrol"> Page </span>dimension, <span class="uicontrol"> Page Views </span> <b></b> metric, and <span class="uicontrol"> Path </span> reports. </td> 
  </tr> 
 </tbody> 
</table>

