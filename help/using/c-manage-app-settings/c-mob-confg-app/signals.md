---
description: Postbacks let you send data collected by Adobe Mobile to a separate third-party server. By leveraging the same triggers and traits that you use to display an in-app message, you can configure Mobile Services to send customized data to a third-party destination.
seo-description: Postbacks let you send data collected by Adobe Mobile to a separate third-party server. By leveraging the same triggers and traits that you use to display an in-app message, you can configure Mobile Services to send customized data to a third-party destination.
seo-title: Configure Postbacks
title: Configure Postbacks
uuid: a026575c-057b-4868-b6c8-9514cbc32b4d
---

# Configure Postbacks{#configure-postbacks}

Postbacks let you send data collected by Adobe Mobile to a separate third-party server. By leveraging the same triggers and traits that you use to display an in-app message, you can configure Mobile Services to send customized data to a third-party destination.

>[!NOTE]
>
>To use postbacks, you must install the 4.6 SDK or later. For more information, see [Android - Postbacks](/help/android/analytics-main/postbacks/postbacks.md) or [iOS - Postbacks](/help/ios/analytics-main/postback/postback.md).

1. Click the name of the desired app to go to its [!DNL Manage App Settings] page and click the **[!UICONTROL Manage Postbacks]** link at the top right side. 
1. Click **[!UICONTROL Create Postback]**. 
1. Type the following information in the fields:

    <table id="table_62E6928094C84476AB259A02E08816F2"> 
    <thead> 
    <tr> 
    <th colname="col1" class="entry"> Option </th> 
    <th colname="col2" class="entry"> Description </th> 
    </tr>
    </thead>
    <tbody> 
    <tr> 
    <td colname="col1"> <p><span class="uicontrol"> Postback Type</span> </p> </td> 
    <td colname="col2"> <p>Choose <span class="uicontrol"> Custom</span>. </p> <p>Templates will be available in the future. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p><span class="uicontrol"> Name </span> </p> </td> 
    <td colname="col2"> <p>Specify a descriptive name for the postback. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p><span class="uicontrol"> URL </span> </p> </td> 
    <td colname="col2"> <p>Specify a valid endpoint URL (along with appropriate query parameters as needed for GET requests). </p> <p>You obtain this URL from the party you are sending the data to (ad server or your own endpoint). </p> <p>For example: </p> <p><span class="filepath"> https://my.server.com/?user=bob&amp;zip=90210&amp;c16=4.6.0-iOS&amp;c27=cln,132</span> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p><span class="uicontrol"> Context Variable </span> </p> </td> 
    <td colname="col2"> <p>Highlight portions of the URL and select the desired context variable from the drop-down list. </p> <p>You can also simply insert context variables into the URL. </p> <p>The URL will replace all template variables with values from the hit. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1" morerows="1"> <p><span class="uicontrol"> Add Post Body</span> </p> </td> 
    <td colname="col2"> <p>Specify any additional post body content, for example on a post request. </p> <p><b>Content Type:</b> If you specify post body text, specify the <span class="wintitle"> content type</span> for the post body. </p> <p>For example, <span class="codeph"> application/json</span>.</p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p><span class="uicontrol"> Timeout (in seconds)</span> </p> </td> 
    <td colname="col2"> <p>Specify the time (in seconds) to wait for the postback. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p><span class="uicontrol"> Trigger(s) </span> </p> </td> 
    <td colname="col2"> <p>Specify one or more data tags and conditions that trigger the postback. For example, you could choose <span class="uicontrol"> Crashed</span> as the trigger and <span class="uicontrol"> Exists</span> as the condition to trigger the postback when the app crashes. </p> <p>You can also specify which metrics activate the postback. For example, you can select <span class="uicontrol"> Device Name</span> as the trigger, <span class="uicontrol"> Equals</span>, and <span class="uicontrol"> iPhone 6 Plus</span> as conditions to activate the postback when the app crashes on iPhone 6 Plus devices. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p><span class="uicontrol"> Trait(s)</span> </p> </td> 
    <td colname="col2"> <p>Specify who can see the message when it is triggered. Options include <span class="uicontrol"> Session Length</span>, <span class="uicontrol"> First Launch Date</span>, and <span class="uicontrol"> App ID</span>. </p> </td> 
    </tr> 
    </tbody> 
    </table>

1. Click **[!UICONTROL Save]** to create the postback and add it to the **[!UICONTROL Manage Postbacks]** list.

   To activate the postback in the future, do one of the following:

    * Select the checkbox next to the postback in the **[!UICONTROL Manage Postbacks]** list and click **[!UICONTROL Activate Selected]**. 
    
    * Click **[!UICONTROL Save & Activate]** to save your changes and immediately activate the postback.

