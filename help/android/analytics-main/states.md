---
description: States are the different screens or views in your application.
seo-description: States are the different screens or views in your application.
seo-title: Track App States
solution: Marketing Cloud,Analytics
title: Track App States
topic: Developer and implementation
uuid: 69c99d05-5816-4c86-97c5-d218dc26c129
index: y
internal: n
snippet: y
---

# Track App States {#track-app-states}

States are the different screens or views in your application.

<a id="section_845C9DB2F9C34428BB679C9BB612855A"></a>

Each time a new state is displayed in your application, for example, when a user navigates from the home page to the news feed, a `trackState` call is sent. In Android, `trackState` is typically called each time a new activity is loaded.

## Tracking States {#section_380DF56C4EE4432A823940E4AE4C9E91}

1. Add the [library to your project and implement lifecycle](../getting-started/dev-qs.md#concept_13176B6E37F547D6935E37125F457972). 
1. Import the library: 

   ```java
   import com.adobe.mobile.*;
   ```

1. In the `onCreate` function, call `trackState` to send a hit for this state view: 

   ```java
   @Override 
   public void onCreate(Bundle savedInstanceState) { 
       super.onCreate(savedInstanceState); 
       setContentView(R.layout.main); 
     
       // Adobe - track when this state loads 
       Analytics.trackState("State Name", null); 
   }
   ```

The `"State Name"` is reported in the `View State` variable in Adobe Mobile services, and a view is recorded for each `trackState` call. In other Analytics interfaces, `View State` is reported as `Page Name`, and `state views` is reported as `page views`.

## Send Additional Data {#section_CFDB4F944496401786A145C209AB387C}

In addition to the `"State Name"`, you can send additional context data with each track action call:

```java
@Override 
public void onCreate(Bundle savedInstanceState) { 
    super.onCreate(savedInstanceState); 
    setContentView(R.layout.main); 
  
    // Adobe - track when this state loads 
    HashMap<String, Object> exampleContextData = new HashMap<String, Object>(); 
    exampleContextData.put("myapp.login.LoginStatus", "logged in"); 
    Analytics.trackState("Home Screen", exampleContextData); 
}
```

Context data values must be mapped to custom variables in [Adobe Mobile services](https://mobilemarketing.adobe.com): 

![](assets/map-variable-context-state.png)

## App State Reporting {#section_0F6A54AB7A3F42C9BB042D86A0FC4630}

States are typically viewed by using a pathing report, which allows you to see how users navigate your app and which states are most frequently viewed.

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
   <td colname="col2"> <p>The <b>View States</b> report. </p> <p>This report is based on the paths that the users took through your application. A sample path is <span class="ignoretag"> <span class="uicontrol"> Home </span>  &gt; <span class="uicontrol"> Settings </span>  &gt; <span class="uicontrol"> Feed </span> </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Adobe Analytics </td> 
   <td colname="col2"> States can be viewed anywhere that <b>Pages</b> can be viewed, such as the <b>Pages</b> report, the <b>Page Views</b> report, and the <b>Path</b> report. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ad hoc analytics </td> 
   <td colname="col2"> States can be viewed anywhere <b>Pages</b> can be viewed by using the <b>Page</b> dimension, <b>Page Views</b> metric, <b>Path</b> reports. </td> 
  </tr> 
 </tbody> 
</table>

