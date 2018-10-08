---
description: You can set the in-app message trigger to be the push message ID that is sent when a user opens the app from the push message.
seo-description: You can set the in-app message trigger to be the push message ID that is sent when a user opens the app from the push message.
seo-title: Trigger an In-App Message when the App is Opened from a Push Message
title: Trigger an In-App Message when the App is Opened from a Push Message
uuid: 9cda3040-53f2-4d1f-907e-1da19a579e86
index: y
internal: n
snippet: y
translate: y
---

# Trigger an In-App Message when the App is Opened from a Push Message

You can set the in-app message trigger to be the push message ID that is sent when a user opens the app from the push message.

1. Get the push message ID for the push message that will be sent to the user.

   You can find the push message ID in the URL during the message creation workflow.

   Here is an example:

   <a id="fig_9FFB80B416644145BAC0D6C7A3FF1E81"></a>

   ![](assets/brandon_task1.png) 

1. Save and activate the in-app message with the following trigger:

   `“a.push.payloadID” =`

   >[!TIP]
   >
   >The push message ID is the ID that you located in step 1.

   This trigger must be manually added because it is not available in the **[!UICONTROL Trigger]** drop-down list.

   <a id="fig_527C9CBFA7CA44C396F52F814DCD6340"></a>

   ![](assets/brandon_task2.png) 

1. Save and send the push message that has the push ID that you located in step 1.
1. Click through the push message to open the app and verify that the in-app message displays when the app opens.

   While you are testing, remember the following information:

* After you save the in-app message, it takes about 45 seconds for the hosted config file to update with the new message. 
* The app looks for config file updates (the new in-app message) when there is a **new** launch, so you must ensure that the app is firing a new launch when the push message is clicked.

  This usually means that you need to ensure that the session timeout has occurred. The default timeout is 5 minutes.

