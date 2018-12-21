---
description: Definition and source code examples for the Postbacks feature.
seo-description: Definition and source code examples for the Postbacks feature.
seo-title: Postback Example
solution: Marketing Cloud,Analytics
title: Postback Example
topic: Developer and implementation
uuid: 809c5646-7a80-40df-984b-0af89d854259
---

# Postback Example{#postback-example}

Definition and source code examples for the Postbacks feature.

>[!CAUTION]
>
>This example is provided for informational purposes only. The [!DNL ADBMobileConfig.json] file should be configured in the Adobe Mobile UI and should not be manually modified. A manually edited configuration file can be dangerous when you have remote messages configuration enabled.

This topic contains the following information:

* [ADBMobileConfig.json Definition](../../analytics-main/postback/postback-example.md#section_0F6EC001AB6D488E815F50C7F5DA022E) 
* [Source Code](../../analytics-main/postback/postback-example.md#section_8169B88A2C634CB788DA574EE8C4B1DC)

## ADBMobileConfig.json Definition {#section_0F6EC001AB6D488E815F50C7F5DA022E}

```
"messages": [ 
    { 
        "messageId": "79ae37c9-89b9-465e-af7f-d3351771f1dc", 
        "template": "callback", 
        "payload": {  
            "templateurl": "https://my.server.com/?user={user.name}&zip={user.zip}&c16={%sdkver%}&c27=cln,{a.PrevSessionLength}", 
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

## Code Sample {#section_8169B88A2C634CB788DA574EE8C4B1DC}

```
NSDictionary *contextData = @{@"user.name":@"bob", @"user.zip":@"90210"}; 
[ADBMobile trackState:@"MainMenu" data:contextData];
```

Because its state is `“MainMenu”`, this tracking call triggers the above postback message. The URL will replace all template variables with values from the hit. Assuming that the user’s previous session was 132 seconds long, and that user is on iOS SDK version 4.6.0, the resulting URL would look like this:

`https://my.server.com/?user=bob&zip=90210&c16=4.6.0-iOS&c27=cln,132` 
