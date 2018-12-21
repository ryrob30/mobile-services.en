---
description: Here is the list of methods that are provided by the Android library.
keywords: android;library;mobile;sdk
seo-description: Here is the list of methods that are provided by the Android library.
seo-title: Configuration Methods
solution: Marketing Cloud,Analytics
title: Configuration Methods
topic: Developer and implementation
uuid: 663aeb6c-1b97-4a3a-8c0e-dd4c2ec28c01
---

# Configuration Methods{#configuration-methods}

Here is the list of methods that are provided by the Android library.

This section contains the following information:

* [Initial Configuration](../configuration/methods.md#section_9169243ECC4744A899A8271F92090ECD) 
* [SDK Settings (Config Class)](../configuration/methods.md#section_C1EB977043C04D2B93E5A63DB72828B6)

## Initial Configuration {#section_9169243ECC4744A899A8271F92090ECD}

The following method must be called once in the `onCreate` method of your main activity: 

<table id="table_4A7CC636112C4D158955D71DC7E0CFCA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Method </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> setContext </td> 
   <td colname="col2"> <p> For example: </p> 
    <codeblock class="syntax java">
      @Overridepublic&nbsp;void&nbsp;onCreate(Bundle&nbsp;savedInstanceState)&nbsp;{&nbsp;&nbsp;super.onCreate(savedInstanceState);&nbsp;&nbsp;setContentView(R.layout.main);&nbsp;&nbsp;Config.setContext(this.getApplicationContext());} 
    </codeblock> </td> 
  </tr> 
 </tbody> 
</table>

## SDK Settings (Config Class) {#section_C1EB977043C04D2B93E5A63DB72828B6}

<table id="table_74D286D1763D4C9F996C2E95A1FEFB39" class="codescroll"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Method </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> registerAdobeDataCallback </td> 
   <td colname="col2"> <p> Registers an object that implements the <span class="codeph"> AdobeDataCallback </span> interface. The overwritten "call" method will be invoked with a <span class="codeph"> Config.MobileDataEvent </span> value and the associated data in a <span class="codeph"> Map&lt;String, Object&gt; </span> for the triggering event. For more details about which events will trigger this callback, see <a href="../configuration/methods.md#section_92732814141646E294782BC9020367EB" format="dita" scope="local"> MobileDataEvent Enum </a>. </p> <p> <p>Tip:  This method requires version 4.9.0 or later. </p> </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax java">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;registerAdobeDataCallback(final&amp;nbsp;AdobeDataCallback&amp;nbsp;callback); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax java">
      Config.registerAdobeDataCallback(new&nbsp;Config.AdobeDataCallback()&nbsp;{&nbsp;&nbsp;&nbsp;&nbsp;@Override&nbsp;&nbsp;&nbsp;&nbsp;public&nbsp;void&nbsp;call(Config.MobileDataEvent&nbsp;event,&nbsp;Map&lt;String,&nbsp;Object&gt;&nbsp;contextData)&nbsp;{&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;//&nbsp;handle&nbsp;each&nbsp;event&nbsp;type&nbsp;accordingly&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;if&nbsp;(event&nbsp;==&nbsp;Config.MobileDataEvent.MOBILE_EVENT_ACQUISITION_INSTALL)&nbsp;{&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;//&nbsp;do&nbsp;something&nbsp;with&nbsp;acquisition&nbsp;data&nbsp;found&nbsp;in&nbsp;contextData&nbsp;parameter&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;HashMap&lt;String,&nbsp;Object&gt;&nbsp;acquisitionData&nbsp;=&nbsp;new&nbsp;HashMap&lt;String,&nbsp;Object&gt;(contextData);&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;...&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}&nbsp;&nbsp;&nbsp;&nbsp;}}); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> getVersion </td> 
   <td colname="col2"> <p> Returns the current version of the Adobe Mobile library. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax java">
      public&amp;nbsp;static&amp;nbsp;String&amp;nbsp;getVersion(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax java">
      String&amp;nbsp;libraryVersion&amp;nbsp;=&amp;nbsp;Config.getVersion(); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> getPrivacyStatus </td> 
   <td colname="col2"> <p>Returns the enum representation of the privacy status for current user. </p> <p>Here are the privacy status values: </p> 
    <ul id="ul_9B1847F75F49466796B5929C485DA9DD"> 
     <li id="li_738965BC048044B5A6ACCE02FC84E74E"> <span class="codeph"> MOBILE_PRIVACY_STATUS_OPT_IN </span>, where the hits are sent immediately. </li> 
     <li id="li_9BB3A31DC62B4EE6AEC364145463E09B"> <span class="codeph"> MOBILE_PRIVACY_STATUS_OPT_OUT </span>, where the its are discarded. </li> 
     <li id="li_AF7571F4B2614B8EAAC43F17216626CF"> <span class="codeph"> MOBILE_PRIVACY_STATUS_UNKNOWN </span>, where if your report suite is timestamp enabled, hits are saved until the privacy status changes to opt-in (hits are sent) or opt-out (hits are discarded). <p>If your report suite is not timestamp enabled, hits are discarded until the privacy status changes to opt in. </p> </li> 
    </ul> <p>The default value is set in the <span class="codeph"> ADBMobileConfig.json </span> file. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax java">
      public&amp;nbsp;static&amp;nbsp;MobilePrivacyStatus&amp;nbsp;getPrivacyStatus(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax java">
      MobilePrivacyStatus&amp;nbsp;privacyStatus&amp;nbsp;=&amp;nbsp;Config.getPrivacyStatus(); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> setPrivacyStatus </td> 
   <td colname="col2"> <p>Sets the privacy status for the current user to <span class="codeph"> status </span>. </p> <p>You can set the privacy status to one of the following values: </p> 
    <ul id="ul_55894773EF51490AB162F0227AE9EEDD"> 
     <li id="li_257F818CBB144C34843840E3FED3B881"> <span class="codeph"> MOBILE_PRIVACY_STATUS_OPT_IN </span>, where the hits are sent immediately. <p>These hits are sent immediately. </p> </li> 
     <li id="li_199FDE7713A84A0FA810D5130F8002B8"> <span class="codeph"> MOBILE_PRIVACY_STATUS_OPT_OUT </span>, where the its are discarded. <p>These hits are discarded. </p> </li> 
     <li id="li_DA25DEED309040D39A8D6E9A6D6BCDAC"> <span class="codeph"> MOBILE_PRIVACY_STATUS_UNKNOWN </span>, where if your report suite is timestamp enabled, hits are saved until the privacy status changes to opt-in (hits are sent) or opt-out (hits are discarded). <p>If your report suite is not timestamp enabled, hits are discarded until the privacy status changes to opt in. </p> </li> 
    </ul> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax java">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;setPrivacyStatus(MobilePrivacyStatus&amp;nbsp;status); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax java">
      Config.setPrivacyStatus(MobilePrivacyStatus.MOBILE_PRIVACY_STATUS_OPT_IN); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> getLifetimeValue </td> 
   <td colname="col2"> <p>Returns the lifetime value of the current user. </p> <p>The default value is <span class="codeph"> 0 </span>. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax java">
      public&amp;nbsp;static&amp;nbsp;BigDecimal&amp;nbsp;getLifetimeValue(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax java">
      BigDecimal&amp;nbsp;currentLifetimeValue&amp;nbsp;=&amp;nbsp;Config.getLifetimeValue(); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> getUserIdentifier </td> 
   <td colname="col2"> <p>If a custom identifier has been set, the custom user identifier is returned. If a custom identifier has not been set, it returns <span class="codeph"> null </span>. </p> <p>The default value is <span class="codeph"> null </span>. </p> <p>Tip:  If your app upgrades from the Experience Cloud 3.x to the 4.x SDK, the previous custom or automatically generated visitor ID is retrieved and stored as the custom user identifier. This preserves visitor data between SDK upgrades. For new installations on the 4.x SDK, until it is set, the user identifier is <span class="codeph"> null </span>. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax java">
      public&amp;nbsp;static&amp;nbsp;String&amp;nbsp;getUserIdentifier(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax java">
      String&amp;nbsp;userId&amp;nbsp;=&amp;nbsp;Config.getUserIdentifier(); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> setUserIdentifier </td> 
   <td colname="col2"> <p>Sets the user identifier to <span class="codeph"> identifier </span>. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax java">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;setUserIdentifer(String&amp;nbsp;identifier); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax java">
      Config.setUserIdentifier("billybob"); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> getDebugLogging </td> 
   <td colname="col2"> <p>Returns the current debug logging preference. </p> <p>The default value is <span class="codeph"> false </span>. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax java">
      public&amp;nbsp;static&amp;nbsp;Boolean&amp;nbsp;getDebugLogging(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax java">
      Boolean&amp;nbsp;debugging&amp;nbsp;=&amp;nbsp;Config.getDebugLogging(); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> setDebugLogging </td> 
   <td colname="col2"> <p>Sets the debug logging preference to <span class="codeph"> debugLogging </span>. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax java">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;setDebugLogging(Boolean&amp;nbsp;debugLogging); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax java">
      Config.setDebugLogging(true); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> collectLifecycleData </td> 
   <td colname="col2"> <p>Indicates to the SDK that lifecycle data should be collected for use across all solutions in the SDK. For more information, see <a href="../metrics.md#concept_77CA5CEB51D1418FB98EC7C044682A05" format="dita" scope="local"> Lifecycle Metrics </a>. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax java">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;collectLifecycleData(final&amp;nbsp;Activity&amp;nbsp;activity,&amp;nbsp;final&amp;nbsp;Map&lt;String,&amp;nbsp;Object&gt;&amp;nbsp;contextData); 
    </codeblock> <p> <b>Example:</b> </p> <p>Without extra context data: </p> 
    <codeblock class="syntax java">
      @Overrideprotected&nbsp;void&nbsp;onResume()&nbsp;{&nbsp;&nbsp;&nbsp;super.onResume();&nbsp;&nbsp;&nbsp;Config.collectLifecycleData(this);} 
    </codeblock> <p>With extra context data: </p> 
    <codeblock class="syntax java">
      @Overridepublic&nbsp;void&nbsp;onResume()&nbsp;{&nbsp;&nbsp;&nbsp;&nbsp;HashMap&lt;String,&nbsp;Object&gt;&nbsp;contextData&nbsp;=&nbsp;new&nbsp;HashMap&lt;String,&nbsp;Object&gt;();&nbsp;&nbsp;&nbsp;&nbsp;contextData.put("myapp.category",&nbsp;"Game");&nbsp;&nbsp;&nbsp;&nbsp;Config.collectLifecycleData(this,&nbsp;contextData);} 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> collectLifecycleData (Activity activity) </td> 
   <td colname="col2"> <p>(<b>Version 4.2 or later</b>) Indicates to the SDK that lifecycle data should be collected for use across all solutions in the SDK. For more information, see <a href="../metrics.md#concept_77CA5CEB51D1418FB98EC7C044682A05" format="dita" scope="local"> Lifecycle Metrics </a>. </p> 
    <!--does this method make is so you don't have to set context anymore?--> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax java">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;collectLifecycleData(final&amp;nbsp;Activity&amp;nbsp;activity); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax java">
      @Overrideprotected&nbsp;void&nbsp;onResume()&nbsp;{&nbsp;super.onResume();&nbsp;//&nbsp;assumes&nbsp;being&nbsp;called&nbsp;in&nbsp;an&nbsp;Activity&nbsp;class&nbsp;Config.collectLifecycleData(this);} 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> pauseCollecting​LifecycleData </td> 
   <td colname="col2"> <p>Indicates to the SDK that your app is paused, so that lifecycle metrics are calculated correctly. For example, <span class="codeph"> onPause </span> collects a timestamp to determine the previous session length. This also sets a flag so that lifecycle knows that the app did not crash. For more information, see <a href="../metrics.md#concept_77CA5CEB51D1418FB98EC7C044682A05" format="dita" scope="local"> Lifecycle Metrics </a>. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax java">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;pauseCollectingLifecycleData(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax java">
      @Overrideprotected&nbsp;void&nbsp;onPause()&nbsp;{&nbsp;&nbsp;&nbsp;super.onPause();&nbsp;&nbsp;&nbsp;Config.pauseCollectingLifecycleData();} 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> setSmallIconResourceId(int resourceId) </td> 
   <td colname="col2"> <p>(<b>Version 4.2 or later</b>) Sets the small icon that will be used for notifications that were created by the SDK. This icon will appear in the status bar and will be the secondary image that is displayed when the user sees the complete notification in the notification center. </p> <p><b>Syntax:</b> </p> 
    <codeblock class="syntax java">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;setSmallIconResourceId(final&amp;nbsp;int&amp;nbsp;resourceId); 
    </codeblock> <p><b>Example:</b> </p> 
    <codeblock class="syntax java">
      Config.setSmallIconResourceId(R.drawable.appIcon); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> setLargeIconResourceId(int resourceId) </td> 
   <td colname="col2"> <p>(<b>Version 4.2 or later</b>) Sets the large icon that will be used for notifications that were created by the SDK. This icon will be the primary image that is displayed when the user sees the complete notification in the notification center. </p> <p><b>Syntax:</b> </p> 
    <codeblock class="syntax java">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;setLargeIconResourceId(final&amp;nbsp;int&amp;nbsp;resourceId); 
    </codeblock> <p><b>Example:</b> </p> 
    <codeblock class="syntax java">
      Config.setLargeIconResourceId(R.drawable.appIcon); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> overrideConfigStream(InputStream configInput) </td> 
   <td colname="col2"> <p>(<b>Version 4.2 or later</b>) Allows you to load a different ADBMobile JSON config file when the application starts. The different configuration is used until the application is closed. </p> <p><b>Syntax:</b> </p> 
    <codeblock class="syntax java">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;overrideConfigStream(final&amp;nbsp;InputStream&amp;nbsp;configInput); 
    </codeblock> <p><b>Example:</b> </p> 
    <codeblock class="syntax java">
      &nbsp;try&nbsp;{&nbsp;InputStream&nbsp;configInput&nbsp;=&nbsp;getAssets().open("ExampleJSONFile.json");&nbsp;Config.overrideConfigStream(configInput);&nbsp;}&nbsp;catch&nbsp;(IOException&nbsp;ex)&nbsp;{&nbsp;//&nbsp;do&nbsp;something&nbsp;with&nbsp;the&nbsp;exception&nbsp;if&nbsp;needed} 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> setPushIdentifier </td> 
   <td colname="col2"> <p>Sets the device token for push notifications. </p> <p><b>Syntax:</b> </p> 
    <codeblock class="syntax java">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;setPushIdentifier(final&amp;nbsp;String&amp;nbsp;registrationId); 
    </codeblock> <p><b>Example:</b> </p> 
    <codeblock class="syntax java">
      ...//&nbsp;note:&nbsp;the&nbsp;code&nbsp;to&nbsp;retreive&nbsp;the&nbsp;push&nbsp;token&nbsp;must&nbsp;run&nbsp;in&nbsp;the&nbsp;backgroundInstanceID&nbsp;instanceID&nbsp;=&nbsp;InstanceID.getInstance(getApplicationContext());String&nbsp;token&nbsp;=&nbsp;instanceID.getToken("835015092242",&nbsp;GoogleCloudMessaging.INSTANCE_ID_SCOPE,&nbsp;null);Config.setPushIdentifier(token);... 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> submitAdvertisingIdentifierTask </td> 
   <td colname="col2"> <p>Provides a Callable to the SDK that returns the string of the Advertising Identifier that is returned from Google Play Services. </p> <p>The SDK runs this task on a background thread and sets an internal variable for the Advertising Identifier that is based on the value returned from the Callable. </p> <p> <p>Important:  If you want to use the Advertising Identifier in Acquisition or Lifecycle, call it before calling <span class="filepath"> Config.collectLifecycleData </span>. </p> </p> <p><b>Syntax:</b> </p> 
    <codeblock class="syntax java">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;submitAdvertisingIdentifierTask(final&amp;nbsp;Callable&lt;String&gt;&amp;nbsp;task); 
    </codeblock> <p><b>Example:</b> </p> 
    <codeblock class="syntax java">
      @Overridepublic&nbsp;void&nbsp;onResume()&nbsp;{&nbsp;&nbsp;&nbsp;&nbsp;super.onResume();&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;final&nbsp;Callable&lt;String&gt;&nbsp;task&nbsp;=&nbsp;new&nbsp;Callable&lt;String&gt;()&nbsp;{&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;@Override&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;public&nbsp;String&nbsp;call()&nbsp;throws&nbsp;Exception&nbsp;{&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;AdvertisingIdClient.Info&nbsp;idInfo;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;String&nbsp;adid&nbsp;=&nbsp;null;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Context&nbsp;appContext&nbsp;=&nbsp;CLASSNAME.this.getApplicationContext();&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;try&nbsp;{&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;idInfo&nbsp;=&nbsp;AdvertisingIdClient.getAdvertisingIdInfo(appContext);&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;if&nbsp;(idInfo&nbsp;!=&nbsp;null)&nbsp;{&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;adid&nbsp;=&nbsp;idInfo.getId();&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}&nbsp;catch&nbsp;(Exception&nbsp;ex)&nbsp;{&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Log.e("Error",&nbsp;ex.getLocalizedMessage());&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;return&nbsp;adid;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}&nbsp;&nbsp;&nbsp;&nbsp;};&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Config.submitAdvertisingIdentifierTask(task);&nbsp;&nbsp;&nbsp;&nbsp;Config.collectLifecycleData(this);} 
    </codeblock> </td> 
  </tr> 
 </tbody> 
</table>

## AdobeDataCallback Interface {#section_600A63B3136F47DCB928071485C5117C}

```java
public interface AdobeDataCallback {  
    void call(MobileDataEvent event, Map<String, Object> contextData);  
} 
```

## MobileDataEvent Enum {#section_92732814141646E294782BC9020367EB}

```java
public enum MobileDataEvent {  
    MobileDataEvent.MOBILE_EVENT_LIFECYCLE, // triggers on a lifecycle hit  
    MobileDataEvent.MOBILE_EVENT_ACQUISITION_INSTALL, // triggers on a app install that has acquisition data  
    MobileDataEvent.MOBILE_EVENT_ACQUISITION_LAUNCH // triggers on launch when the device previously installed via acquisition  
}
```

