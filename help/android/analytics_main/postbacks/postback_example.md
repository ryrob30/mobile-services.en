---
description: You can use this information to help you understand postbacks are and how they work.
keywords: android;library;mobile;sdk
seo-description: You can use this information to help you understand postbacks are and how they work.
seo-title: Postbacks Example
solution: Marketing Cloud,Analytics
title: Postbacks Example
topic: Developer and implementation
uuid: 04975750-5781-45d8-b60f-92df45f1e19a
index: y
internal: n
snippet: y
translate: y
---

# Postbacks Example


>[!CAUTION]
>
>This example is provided for informational purposes only. The [!DNL  ADBMobileConfig.json] file should be configured in the Adobe Mobile UI and should not be manually modified. A manually edited configuration file can be dangerous when you have remote messages configuration enabled. 



This topic contains the following information: 


* [ ADBMobileConfig.json Definition ](../../analytics_main/postbacks/postback_example.md#section_8751E8176F3546C09420341A39758AFF)
* [ Source Code ](../../analytics_main/postbacks/postback_example.md#section_D063DE82976D4EDEA97E804BD1C4718F)


## ADBMobileConfig.json Definition {#section_8751E8176F3546C09420341A39758AFF}


```
"messages": [ 
    { 
        "messageId": "79ae37c9-89b9-465e-af7f-d3351771f1dc", 
        "template": "callback", 
        "payload": {  
            "templateurl": "http://my.server.com/?user={user.name}&zip={user.zip}&c16={%sdkver%}&c27=cln,{a.PrevSessionLength}", 
            "templatebody": "c2RrdmVyPXslc2RrdmVyJX0mY2I9eyVjYWNoZWJ1c3QlfSZjbGllbnRJZD17bi5jbGllbnQuaWR9JnRzPXsldGltZXN0YW1wVSV9JnRzej17JXRpbWVzdGFtcFolfQ==", 
            "contenttype": "application/x-www-form-urlencoded",  
            "timeout": 4 
        }, 
        "showOffline": true, 
        "showRule": "always", 
        "endDate": 2524730400, 
        "startDate": 0, 
        "audiences": [], 
        "triggers": [ 
            { 
                "key": "pageName", 
                "matches": "eq", 
                "values": [ 
                    "MainMenu" 
                ] 
            } 
        ] 
    } 
] 

```

## Code Sample {#section_D063DE82976D4EDEA97E804BD1C4718F}


```
HashMap<String, Object> contextData = new HashMap<String, Object>(); 
contextData.put("user.name", "bob"); 
contextData.put("user.zip", "90210"); 
Analytics.trackState("MainMenu", contextData);
```
Because its state is ` “MainMenu”`, this tracking call triggers the above postback message. The URL will replace all template variables with values from the hit. Assuming that the user’s previous session was 132 seconds long, and that user is on Android SDK version 4.6.0, the resulting URL would look like this: 

` http://my.server.com/?user=bob&amp;zip=90210&amp;c16=4.6.0-AN&amp;c27=cln,132` 
