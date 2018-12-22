---
description: You can create or edit marketing links to provide deep linking into your mobile app or your website.
keywords: mobile
seo-description: You can create or edit marketing links to provide deep linking into your mobile app or your website.
seo-title: Create or Edit Marketing Links
solution: Marketing Cloud,Analytics
title: Create or Edit Marketing Links
topic: Metrics
uuid: 305a8265-38de-4d19-8c79-b3912f5aae7c
---

# Create or Edit Marketing Links{#create-or-edit-marketing-links}

You can create or edit marketing links to provide deep linking to your mobile app or your website.

For more information about universal links and app links, see [Universal Links and App Links](../../../c-manage-app-settings/c-mob-confg-app/c-universal-app-links.md#concept_95121E3CF0904C2CA9606EC67C9EAA81). 

1. In your app, in the left navigation pane, expand **[!UICONTROL Acquisition]** and click **[!UICONTROL Marketing Link Builder]**.
1. Complete one of the following tasks:

    * To create a marketing link, click **[!UICONTROL Create New]**. 
    * To edit a link, click the link's name in the **[!UICONTROL Title]** column.

1. Type information in the following fields:

    * **Marketing Link Name:**

      (Required) Specify a descriptive name for your marketing link. The name displays only on the [!DNL Marketing Links] page in the [!DNL Adobe Mobile Services] UI. A descriptive name helps you or others in your organization quickly find a specific link and can provide insight into its purpose. 

    * **Unique Tracking Code:**

      (Required) Specify the desired tracking code or click ![](assets/icon_generate.png) to create a new tracking code. You can view reports that detail use of the tracking code.
    
    * **Add Tracking Context Data:**

      (Optional) Click the **[!UICONTROL +]** icon and type the relevant information to track your campaign using context data. In the **[!UICONTROL Custom Context Data]** drop-down list, select a preset tag or one of your own tags. Context data is used for reporting when the marketing link is deployed.

      The following preset tags are available:

      <table id="table_CFCEED0575D94FD4A1433B870FA8FDB7"> 
      <thead> 
        <tr> 
        <th colname="col1" class="entry"> Tag Option </th> 
        <th colname="col2" class="entry"> Description </th> 
        </tr>
      </thead>
       <tbody> 
        <tr> 
        <td colname="col1"> <p><span class="uicontrol"> Custom Context Data </span> </p> </td> 
        <td colname="col2"> <p>Specify the key and value. </p> <p>If you add custom context data, you must create a processing rule. For more information, see <!--REKHA--<a href="https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/processing-rules/processing-rules.html" format="dita" scope="external"> Processing Rules</a>. </p>--> </td> 
        </tr> 
        <tr> 
        <td colname="col1"> <p><span class="uicontrol"> Source </span> </p> </td> 
        <td colname="col2"> <p>Specify the original referrer, such as "newsletter" or "homepage." </p> </td> 
        </tr> 
        <tr> 
        <td colname="col1"> <p><span class="uicontrol"> Medium </span> </p> </td> 
        <td colname="col2"> <p>Specify the marketing medium, such as "banner" or "email." </p> </td> 
        </tr> 
        <tr> 
        <td colname="col1"> <p><span class="uicontrol"> Content </span> </p> </td> 
        <td colname="col2"> <p>Specify the name or ID of the ad with the link. </p> </td> 
        </tr> 
        <tr> 
        <td colname="col1"> <p><span class="uicontrol"> Term </span> </p> </td> 
        <td colname="col2"> <p>Specify paid terms or other search terms for the ad. </p> </td> 
        </tr> 
      </tbody> 
    </table>

1. Click **[!UICONTROL Save]**.
1. Type information in the following fields:

    * (Required) In **[!UICONTROL Fallback URL]**, Specify the URL that users are directed to when a destination cannot be matched (for example, if the user is on a desktop or another platform that does not match a destination rule). 
    * In **[!UICONTROL Marketing Link Options]**, select **[!UICONTROL Interstitials]** or **[!UICONTROL Universal and App Links]**.

      For more information, see [Interstitials](../../../acquisition-main/c-marketing-links-builder/t-create-edit-adobe-links/t-interstitials.md#task_1A4A822E89CB46E2A8943EEE384EBD23) or [Universal Links and App Links](../../../c-manage-app-settings/c-mob-confg-app/c-universal-app-links.md#concept_95121E3CF0904C2CA9606EC67C9EAA81). 
    
    * (Conditional) If **[!UICONTROL Universal or App Links]** is selected, in **[!UICONTROL Custom Path]**, users can define the URL path after the domain with any query parameter. For more information, see [Universal Links and App Links](../../../c-manage-app-settings/c-mob-confg-app/c-universal-app-links.md#concept_95121E3CF0904C2CA9606EC67C9EAA81).

1. Click **[!UICONTROL Edit Deep Link Interstitial]** and configure the link.

   (Optional) When there are multiple destinations, users can be routed depending on whether they have a mobile app installed. If the app is installed, an interstitial landing page is displayed.

   For more information, see [Interstitials](../../../acquisition-main/c-marketing-links-builder/t-create-edit-adobe-links/t-interstitials.md#task_1A4A822E89CB46E2A8943EEE384EBD23). 

1. Click **[!UICONTROL Save]** and click **[!UICONTROL Next]**.
1. In the [!DNL Destination] page, configure the link.

   1. Click the **[!UICONTROL Decision]** icon (  ![](assets/icon_decision.png) ) and select one of the following decision locations:

       * **[!UICONTROL Add Decision]** 
       * **[!UICONTROL Add Path]**

   1. If you selected **[!UICONTROL Add Decision]**, select one of the following decision types:

       * **[!UICONTROL Operating Decision]**

         Supported operating systems include iOS, Android, AMX, and so on. 
       
       * **[!UICONTROL Device Type]**

         Device types include devices such as desktops, eReaders, game consoles, mobile phones, set top boxes, and so on.

   1. Click the **[!UICONTROL Destination]** icon ( ![](assets/icon_square.png) ) and select one of the following destination types:

       * **[!UICONTROL App Store]** 
       * **[!UICONTROL Web Link]** 
       * **[!UICONTROL App Deep Link]** 
       * **[!UICONTROL Hybrid Link]**

       >[!TIP]
       >
       >When you use the **[!UICONTROL Web Link]** destination type with a link to the app store, acquisition is not tracked. To track acquisitions, use the **[!UICONTROL App Store]** destination type.

       For more information, see [Create New Link Destination](../../../acquisition-main/c-manage-link-destinations/t-create-new-app-deep-link-destination.md#). 
       
1. To save the marketing link, click ![](assets/icon_elipses.png) and then **[!UICONTROL Save]**.
