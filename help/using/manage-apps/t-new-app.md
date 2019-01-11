---
description: You can use this information to create a new app and configure its key metrics;configure the SDK options for Adobe Analytics and Adobe Audience Manager;configure acquisition and ID service options;and download the configuration file, SDKs, and developer and tester tools.
keywords: mobile
seo-description: You can use this information to create a new app and configure its key metrics;configure the SDK options for Adobe Analytics and Adobe Audience Manager;configure acquisition and ID service options;and download the configuration file, SDKs, and developer and tester tools.
seo-title: Add a New App
solution: Marketing Cloud,Analytics
title: Add a New App
topic: Metrics
uuid: 706b5e4d-1318-4a9e-8c69-ffabf51fa02c
---

# Add a New App{#add-a-new-app}

You can use this information to create a new app and configure its key metrics;configure the SDK options for [!DNL Adobe Analytics] and [!DNL Adobe Audience Manager]; configure acquisition and ID service options; and download the configuration file, SDKs, and developer and tester tools.

 These instructions will help you add a new app and configure [!DNL Adobe Analytics] and [!DNL Adobe Audience Manager] integrations.

Before you can configure your app, you must add it in the [!DNL Adobe Mobile Services] user interface. After you create the app, the correct configuration is generated, and you can provide this configuration to the developers who are implementing the Mobile SDK for the app. 

1. [Sign in](../gs/gs-signin.md#concept_7C5CF11607B4441EBE22982E955D1D5E) to [!DNL Adobe Mobile Services] and complete one of the following tasks:

    * Click **[!UICONTROL Create New]** to create an app. 
    * To add additional apps, click [!DNL Manage Apps] in the left navigation menu, then click **[!UICONTROL Add]**.

       >[!TIP]
       >
       >To manage existing apps, click [!DNL Manage Apps] in the left navigation menu and click the app that you want to modify. You can make changes on the [!DNL App Information] page.

1. Type information in the following fields:

   **[!UICONTROL Report Suite]** 

     Specify the report suite in which reporting data will be collected and stored in <span class="keyword"> Adobe Analytics </span>. </p> <p> Each app is connected to one <span class="keyword"> Analytics </span> report suite. If you are sending app data to multiple reports suites, add a new app for each report suite. Each app is connected to one <span class="keyword"> Analytics </span> report suite. If you are sending app data to multiple reports suites, add a new app for each report suite. 

     If you have been given <span class="keyword"> Analytics </span> administrator privileges in <span class="keyword"> Adobe Mobile </span>, you can create a new report suite in <span class="keyword"> Adobe Mobile </span>. </p> <p>To create a new report suite, select the <span class="uicontrol"> New Report Suite </span> and type information into the following fields: 

      * **[!UICONTROL Report Suite ID]**: This ID is used to uniquely identify the report suite in [!DNL Adobe Analytics]. Your company prefix is automatically added to the beginning of the ID.  
      * **[!UICONTROL Copy Settings From]**: The variables, events, processing rules, and other settings are set up in the new report suite exactly like they are in this report suite. A report suite created in [!DNL Mobile Services ] is offline-enabled (or time stamped) only if the **[!UICONTROL Copy Settings From]** report suite used was the Mobile App Template, or if you create a report suite that is offline enabled. </p> </li> 
          <li id="li_DF70F8872FBA4A8F80F5D8B2EB3E835C"> <p> <span class="uicontrol"> Timezone: </span> All reporting dates are in this time zone. This setting attempts to use a time zone close to what your browser uses. </p> </li> 
          <li id="li_C3EA81F601874156A4C669F2E3E66082"> <p> <span class="uicontrol"> Currency: </span> Revenue is both tracked and reported as this type of currency. </p> </li> 
        </ul> </p> <p> <p>Tip:  To use a virtual reporting suite (VRS), see <a href="../manage-apps/c-mob-vrs.md#concept_0C6EDD6139AC4B08A2316CFCE77CC717" format="dita" scope="local"> Virtual Report Suites 

    <table id="table_A9356F6A5D1F4441AE4E594C1E4F5FE6"> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> Setting </th> 
      <th colname="col2" class="entry"> Description </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1" morerows="1"> <p> <span class="uicontrol"> Report Suite </span> </p> </td> 
      <td colname="col2"> <p>Specify the report suite in which reporting data will be collected and stored in <span class="keyword"> Adobe Analytics </span>. </p> <p> Each app is connected to one <span class="keyword"> Analytics </span> report suite. If you are sending app data to multiple reports suites, add a new app for each report suite. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col2"> <p>If you have been given <span class="keyword"> Analytics </span> administrator privileges in <span class="keyword"> Adobe Mobile </span>, you can create a new report suite in <span class="keyword"> Adobe Mobile </span>. </p> <p>To create a new report suite, select the <span class="uicontrol"> New Report Suite </span> and type information into the following fields: </p> <p> 
        <ul id="ul_771732DB4445424F8E71838845A1E131"> 
          <li id="li_14BBFA72D01C41029737950095C63C1A"> <p> <span class="uicontrol"> Report Suite ID: </span> This ID is used to uniquely identify the report suite in <span class="keyword"> Adobe Analytics </span>. Your company prefix is automatically added to the beginning of the ID. </p> </li> 
          <li id="li_747FF935822B45C4A168EF1B6A2783D6"> <p> <span class="uicontrol"> Copy Settings From: </span> The variables, events, processing rules, and other settings are set up in the new report suite exactly like they are in this report suite. A report suite created in <span class="keyword"> Mobile Services </span> is offline-enabled (or time stamped) only if the <span class="wintitle"> Copy Settings From </span> report suite used was the Mobile App Template, or if you create a report suite that is offline enabled. </p> </li> 
          <li id="li_DF70F8872FBA4A8F80F5D8B2EB3E835C"> <p> <span class="uicontrol"> Timezone: </span> All reporting dates are in this time zone. This setting attempts to use a time zone close to what your browser uses. </p> </li> 
          <li id="li_C3EA81F601874156A4C669F2E3E66082"> <p> <span class="uicontrol"> Currency: </span> Revenue is both tracked and reported as this type of currency. </p> </li> 
        </ul> </p> <p> <p>Tip:  To use a virtual reporting suite (VRS), see <a href="../manage-apps/c-mob-vrs.md#concept_0C6EDD6139AC4B08A2316CFCE77CC717" format="dita" scope="local"> Virtual Report Suites </a>. </p> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <span class="uicontrol"> Icon </span> </p> </td> 
      <td colname="col2"> <p>(Optional) To browse to and select an icon for your app, click the <span class="uicontrol"> A </span> icon. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <span class="uicontrol"> Name </span> </p> </td> 
      <td colname="col2"> <p>(Optional) Type a descriptive name for the app. </p> <p>A descriptive name helps you quickly locate an app. A meaningful name can help you quickly understand the app's purpose and settings. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <span class="uicontrol"> Type </span> </p> </td> 
      <td colname="col2"> <p>Select a type from the drop-down list. The available reports that display in the left navigation menu vary depending on the type of app you select. </p> <p>Here are the available types: </p> 
        <ul id="ul_CDB18D35AF404821821CE3CEC243ADB9"> 
        <li id="li_0C66033E68E74920AF8D192067A96B77"> <span class="uicontrol"> Standard </span> <p>You can leave the <span class="uicontrol"> Standard </span> option selected for most apps. </p> </li> 
        <li id="li_E83F5FB9A4C8402DA35DEB2BE3C79700"> <span class="uicontrol"> Publication: </span> <p>You can select this option if your app was built using Adobe Digital Publishing Suite. </p> </li> 
        <li id="li_1C5038FB6F85462B87E2834C88AE1FFA"> <span class="uicontrol"> Game </span> <p>This option is similar to the <span class="uicontrol"> Standard </span> option, except that <span class="uicontrol"> Game </span> updates the terminology used in the reports to terms for games. For example, <span class="term"> users </span> is changed to <span class="term"> players </span>. Game-specific reports are automatically shown for game apps. </p> </li> 
        </ul> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <span class="uicontrol"> Description </span> </p> </td> 
      <td colname="col2"> <p>(Optional) Type a description for the app. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Click **[!UICONTROL Save]** to add the new app.

   After the app has been added, you can check the [!DNL App Information] page about configuring additional options. For more information, see [Manage App Settings](../c-manage-app-settings/c-manage-app-settings.md#concept_3A1E216CB91D43C5BE343CF2D9398D27).
