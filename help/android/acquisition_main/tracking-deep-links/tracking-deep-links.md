---
description: You can use this information to track deep and deferred deep links in your mobile apps by using the Adobe Mobile Android SDK.
keywords: android;library;mobile;sdk
seo-description: You can use this information to track deep and deferred deep links in your mobile apps by using the Adobe Mobile Android SDK.
seo-title: Tracking Deep Links
solution: Marketing Cloud,Analytics
title: Tracking Deep Links
topic: Developer and implementation
uuid: 4af0e267-694a-42f4-b137-33a181a70e5b
index: y
internal: n
snippet: y
translate: y
---

# Tracking Deep Links

This topic contains the following information: 

* [ Getting Started ](../../acquisition_main/tracking-deep-links/tracking-deep-links.md#section_3DC3E891AC7840DAA723F83427CB77F2)
* [ Deep Link Public Info ](../../acquisition_main/tracking-deep-links/tracking-deep-links.md#section_1815396353614DA8A63D8D92112217E7)

## Getting Started {#section_3DC3E891AC7840DAA723F83427CB77F2}

**Tracking Deep Links** 

1. Add the SDK to your project and implement Lifecycle metrics. For more information, see [ Core Implementation and Lifecycle ](../../getting_started/dev_qs.md#concept_13176B6E37F547D6935E37125F457972). 

1. Register the application to handle [ URLs ](http://developer.android.com/training/basics/intents/filters.html). 

1. Pass Activity with deep link intent to Adobe SDK by using ` collectLifecycleData`. 

   Here is a sample track deep link: 

   ```
   java   public class ParseDeepLinkActivity extends Activity { 
       @Override 
       protected void onCreate(Bundle savedInstanceState) { 
           super.onCreate(savedInstanceState); 
     
           Config.collectLifecycleData(this); 
           ... 
       } 
   }
   ```

The [!DNL  Adobe Mobile] SDK can parse key and value pairs of data that is appended to any deep or universal link as long as the link contains a key with the ` a.deeplink.id` label and a corresponding non-null and user-generated value. All key and value pairs of data that are appended to the link will be parsed, attached to a lifecycle hit, and sent to [!DNL  Adobe Analytics] as long as the link contains the ` a.deeplink.id` key and value. 

Additionally, you might append one or more of the following reserved keys (with user-generated values) to the deep or universal link: 


* ` a.launch.campaign.trackingcode`
* ` a.launch.campaign.source`
* ` a.launch.campaign.medium`
* ` a.launch.campaign.term`
* ` a.launch.campaign.content`


These keys are pre-mapped variables for reporting in [!DNL  Adobe Analytics]. For more information on mapping and processing rules, see [ Processing Rules and Context Data ](../../getting_started/proc_rules.md#concept_4DAF0756D0DB43BD8C0627E023665FA5). 

**Tracking Deferred Deep Links (for use with Marketing Links)** 

With a deferred deep link, the Adobe SDK will open a new Intent with the deep link as the intent data. This process is handled as an external deep link using the code above. 

## Deep Link Public Information {#section_1815396353614DA8A63D8D92112217E7}

**Constants** 

```
java/* 
 * Used for message deep link tracking 
 * Key for deep link URL. 
 */ 
public static final String ADB_MESSAGE_DEEPLINK_KEY = "adb_deeplink";
```
