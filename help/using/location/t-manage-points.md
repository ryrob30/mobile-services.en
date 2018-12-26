---
description: You can create and manage points of interest, which allow you to define geographical locations that you can use for correlation purposes, target with in-app messages, and so on. When a hit is sent in a point of interest, the point of interest is attached to the hit.
keywords: mobile
seo-description: You can create and manage points of interest, which allow you to define geographical locations that you can use for correlation purposes, target with in-app messages, and so on. When a hit is sent in a point of interest, the point of interest is attached to the hit.
seo-title: Manage Points of Interest
solution: Marketing Cloud,Analytics
title: Manage Points of Interest
topic: Metrics
uuid: 7b362534-54fb-43a3-b6b2-dfc8f45ff7c6
---

# Manage Points of Interest{#manage-points-of-interest}

You can create and manage POIs, which allow you to define geographical locations that you can use for correlation purposes, target with in-app messages, and so on. When a hit is sent in a POI, the POI is attached to the hit.

To use [!DNL Location] features, complete the following tasks:

* You must have [!DNL Analytics—Mobile Apps] or [!DNL Analytics Premium]. 
* You must enable **[!UICONTROL Location Reports]** for the app. 
* If you are using a version of the iOS SDK or Android SDK older than version 4.2, after adding new **[!UICONTROL Points of Interest]**, you must download a new configuration file and give it to your app developers.

  If you are using the iOS SDK or Android SDK version 4.2 or later,you do not need to submit an app update to the store to update your **[!UICONTROL Points of Interest]**. On the [!DNL Manage Points of Interest] page, clicking **[!UICONTROL Save]** packages changes to the **[!UICONTROL Points of Interest]** list and updates the configuration file for the live app. Saving also updates the list of points in your app on the user devices, as long as the app uses the updated SDK and configuration with a remote POI URL.

On the user's device, for a hit to be assigned to a **[!UICONTROL Points of Interest]**, location must be enabled for the app. 

1. Click the name of the app to go to its [!DNL Manage App Settings] **[!UICONTROL]** page.
1. Click **[!UICONTROL Location]** > **[!UICONTROL Manage Points of Interest]**.

   ![Step Result](assets/poi.png)

1. Type information in each of the following fields:

    <table id="table_5BFF39183C0F44FE9478F1E6173B4888"> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> Option </th> 
      <th colname="col2" class="entry"> Description </th> 
      </tr>
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p><span class="uicontrol"> Point Name</span> </p> </td> 
      <td colname="col2"> <p>Type the <span class="uicontrol"> Point of Location</span> name. This could be the name of a city, county, or region. You can also create a <span class="uicontrol"> Point of Location</span> around specific locations, such as sports stadiums or businesses. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p><span class="uicontrol"> Latitude </span> </p> </td> 
      <td colname="col2"> <p>Type the latitude of the <span class="uicontrol"> Point of Location</span>. You can find this information from other sources, including the Internet. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p><span class="uicontrol"> Longitude </span> </p> </td> 
      <td colname="col2"> <p>Type the longitude of the <span class="uicontrol"> Point of Location</span>. You can find this information from other sources, including the Internet. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p><span class="uicontrol"> Radius (Meters)</span> </p> </td> 
      <td colname="col2"> <p>Type the radius (in meters) around the <span class="uicontrol"> Point of Location</span> that you want to include. </p> <p>For example, if you create a POI, for Denver, Colorado, you could specify a radius large enough to include the city of Denver and the surrounding areas but exclude Colorado Springs. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p><span class="uicontrol"> Map Icon </span> </p> </td> 
      <td colname="col2"> <p>Select an icon that will display on the <a href="../location/c-location-overview.md#concept_D5FA9592A77D46898A7E6DAAC78E1712" format="dita" scope="local"> Overview</a> and <a href="../location/c-map-points.md#concept_E51E9A97ED4D4729ADC40492DA32FC2B" format="dita" scope="local"> Map</a> reports. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Add additional points of interest, as needed.

   We recommend that you add no more than 5,000 points of interest. If you add more than 5,000, you can save the points, but you will receive a warning message informing you that best practices dictate having fewer than 5,000 points. 
1. Click **[!UICONTROL Save]**.

To delete one or more POIs, select the applicable check boxes, and click **[!UICONTROL Remove Selected]**.

Click **[!UICONTROL Import]** or **[!UICONTROL Export]** to work with the data by using a [!DNL .csv] file instead of using the [!DNL Adobe Mobile] user interface. 
