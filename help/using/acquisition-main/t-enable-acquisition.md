---
description: Acquisition tracking must be enabled in the SDK configuration before you can track and report on marketing links.
keywords: mobile
seo-description: Acquisition tracking must be enabled in the SDK configuration before you can track and report on marketing links.
seo-title: Configure Acquisition
solution: Marketing Cloud,Analytics
title: Configure Acquisition
topic: Metrics
uuid: e996e43e-8a77-47a3-a6fb-53f676f92bef
---

# Configure Acquisition {#configure-acquisition}

Acquisition tracking must be enabled in the SDK configuration before you can track and report on marketing links.

1. On the [!DNL Manage App Settings] page for the app, scroll to the **[!UICONTROL SDK Acquisition Options]** section.
1. Complete the following tasks:

   * Enable the check box
    To enable acquisition, select the check box. When you select this check box, the **[!UICONTROL Referrer Timeout]** field becomes active, and the value changes from 0 to 5.

   * Enter a value in the **[!UICONTROL Referrer Timeout (seconds)]** field
     (Optional) This field is optional if you have already enabled the **[!UICONTROL Enable]** check box. You can change the timeout value, which is specified in seconds. This setting specifies the time to wait for acquisition information before sending the First Launch hit. We recommend that you use the 5-second default value.

    >[!IMPORTANT]
    >You must enter a non-zero value. If you enable acquisition but leave the value as zero, acquisition links will not function.

1. Download and use the new SDK configuration file in your app.

   You have successfully configured Acquisition on **iOS**.
   To enable Acquisition on **Android**, complete the steps in [Tracking Mobile Acquisition](/help/android/acquisition-main/acquisition.md).
