---
description: The following table describes the different app identifiers that are used by the Android SDK and Adobe Mobile services.
seo-description: The following table describes the different app identifiers that are used by the Android SDK and Adobe Mobile services.
seo-title: App IDs
solution: Marketing Cloud,Analytics
title: App IDs
topic: Developer and implementation
uuid: 0380000a-edfc-4718-8074-ca2e6d2b7c9f
index: y
internal: n
snippet: y
translate: y
---

# App IDs



<table id="table_6411AFB4F30544B58AA29A4C589F0AC8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ID </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> ID sent with lifecycle metrics </td> 
   <td colname="col2"> <p>This is a combination of the app name and the bundle version that is submitted to the app store. </p> <p> This value is used for the <span class="uicontrol"> Versions</span> report in Adobe Mobile services, and you can filter using this value to segment by a specific release version of your app. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> App Store ID </td> 
   <td colname="col2"> <p>This ID is assigned to your app by the app store, and is provided in Adobe Mobile services when you create acquisition links. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> AppID in ADBMobile JSON Config </td> 
   <td colname="col2"> <p>This is a unique ID that is assigned to the app instance by Adobe Mobile services for all the associated metadata in the system. </p> <p>This ID is used to create the unique URLs for acquisition tracking or tracking link. This ID is automatically added to the ADBMobile JSON config file when this file is downloaded from the UI and can be found on <span class="wintitle"> Manage App Settings</span> under the <span class="uicontrol"> Acquisition</span> settings for your app. </p> </td> 
  </tr> 
 </tbody> 
</table>

