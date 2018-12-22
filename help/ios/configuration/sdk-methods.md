---
description: Here is a list of methods that are provided by the iOS library.
seo-description: Here is a list of methods that are provided by the iOS library.
seo-title: Configuration Methods
solution: Marketing Cloud,Analytics
title: Configuration Methods
topic: Developer and implementation
uuid: 623c7b07-fbb3-4d39-a5c4-e64faec4ca29
---

# Configuration Methods{#configuration-methods}

Here is a list of methods that are provided by the iOS library.

 The SDK currently has support for multiple [!DNL Adobe Experience Cloud Solutions], including [!DNL Analytics], [!DNL Target], [!DNL Audience Manager], and the [!DNL Experience Cloud ID service]. 

<table id="table_74D286D1763D4C9F996C2E95A1FEFB39"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Method </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> setAppExtensionType </p> </td> 
   <td colname="col2"> <p>Configures the Adobe Mobile SDK setting to determine what kind of extension is currently being executed. </p> <p>Set to one of the following values: 
     <ul id="ul_CBE2250BD1B541F18C699F322A00FA23"> 
      <li id="li_8B6252CB2F384876B82A69E71521BB7E"> <span class="codeph"> ADBMobileAppExtensionTypeRegular </span> - extension is bundled with a containing app </li> 
      <li id="li_5804CD63AA824C9EB8D75E511F656C0D"> <span class="codeph"> ADBMobileAppExtensionTypeStandAlone </span> - extension is not bundled with a containing app </li> 
     </ul> </p> <p> <p>Tip:  This method should <b>only</b> be used if your app has an extension or is a stand-alone extension. For more information, see <a href="../configuration/sdk-methods.md#section_18DB491D0ABC4765BB5A467D8FEF4F1B" format="dita" scope="local"> ADBMobileAppExtensionType </a>. </p> </p> <p><b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      +&amp;nbsp;(void)&amp;nbsp;setAppExtensionType:(ADBMobileAppExtensionType)type; 
    </codeblock> <p><b>Example:</b> </p> 
    <codeblock class="syntax c">
      [ADBMobile&amp;nbsp;setAppExtensionType:ADBMobileAppExtensionTypeStandAlone]; 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>version </p> </td> 
   <td colname="col2"> <p> Returns the current version of the Adobe Mobile library. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      +&amp;nbsp;(NSString&amp;nbsp;*)&amp;nbsp;version; 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      NSString&amp;nbsp;*libraryVersion&amp;nbsp;=&amp;nbsp;[ADBMobile&amp;nbsp;version]; 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>privacyStatus </p> </td> 
   <td colname="col2"> <p>Returns the enum representation of the privacy status for current user: 
     <ul id="ul_9B1847F75F49466796B5929C485DA9DD"> 
      <li id="li_738965BC048044B5A6ACCE02FC84E74E"> <span class="codeph"> ADBMobilePrivacyStatusOptIn </span> - hits are sent immediately. </li> 
      <li id="li_9BB3A31DC62B4EE6AEC364145463E09B"> <span class="codeph"> ADBMobilePrivacyStatusOptOut </span> - hits are discarded. </li> 
      <li id="li_AF7571F4B2614B8EAAC43F17216626CF"> <span class="codeph"> ADBMobilePrivacyStatusUnknown </span> - If offline tracking is enabled, hits are saved until the privacy status changes to opt-in (then hits are sent) or opt-out (then hits are discarded). If offline tracking is not enabled, hits are discarded until the privacy status changes to opt in. </li> 
     </ul> </p> <p>The default value is set in <span class="codeph"> ADBMobileConfig.json </span>. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      +&amp;nbsp;(ADBMobilePrivacyStatus)&amp;nbsp;privacyStatus; 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMobilePrivacyStatus&amp;nbsp;privacyStatus&amp;nbsp;=&amp;nbsp;[ADBMobile&amp;nbsp;privacyStatus]; 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>setPrivacyStatus: </p> </td> 
   <td colname="col2"> <p>Sets the privacy status for the current user to <span class="codeph"> status </span>. </p> <p>Set to one of the following values: 
     <ul id="ul_B1C6CBA807B34428819A26A641598B16"> 
      <li id="li_BD3F6C675464458CA6D8F319E927D54B"> <span class="codeph"> ADBMobilePrivacyStatusOptIn </span> - hits are sent immediately. </li> 
      <li id="li_EF64829B421043A394D2F178B36D5CC9"> <span class="codeph"> ADBMobilePrivacyStatusOptOut </span> - hits are discarded. </li> 
      <li id="li_EF6FFB5A735D4725A75FEC5D49094A69"> <span class="codeph"> ADBMobilePrivacyStatusUnknown </span> - If offline tracking is enabled, hits are saved until the privacy status changes to opt-in (then hits are sent) or opt-out (then hits are discarded). If offline tracking is not enabled, hits are discarded until the privacy status changes to opt in. </li> 
     </ul> </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      +&amp;nbsp;(void)&amp;nbsp;setPrivacyStatus:(ADBMobilePrivacyStatus)status; 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      [ADBMobile&amp;nbsp;setPrivacyStatus:ADBMobilePrivacyStatusOptIn]; 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>lifetimeValue </p> </td> 
   <td colname="col2"> <p>Returns the lifetime value of the current user. </p> <p>Default: 0 </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      +&amp;nbsp;(NSDecimalNumber&amp;nbsp;*)&amp;nbsp;lifetimeValue; 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      NSDecimalNumber&amp;nbsp;*lifeValue&amp;nbsp;=&amp;nbsp;[ADBMobile&amp;nbsp;lifetimeValue]; 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>trackingIdentifier </p> </td> 
   <td colname="col2"> <p>Returns the automatically generated visitor identifier. This is an app-specific unique visitor ID that is generated by Adobe’s servers. If Adobe's servers cannot be reached at the time of generation, then the ID is generated using Apple's CFUUID. The value is generated at the initial launch and is stored and used from that point forward. This ID is preserved between app upgrades, is saved and restored during the standard application backup process, and is removed at uninstall. </p> <p> <p>Tip:  If your app upgrades from the Experience Cloud 3.x to the 4.x SDK, the previous custom or automatically generated visitor ID is retrieved and stored as the custom user identifier. For more information, see the <span class="codeph"> userIdentifier </span> row below. </p> </p> <p>This preserves visitor data between SDK upgrades. For new installations on the 4.x SDK, the user identifier is <span class="codeph"> nil </span> and tracking identifier is used. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      +&amp;nbsp;(NSString&amp;nbsp;*)&amp;nbsp;trackingIdentifier; 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      NSString&amp;nbsp;*tid&amp;nbsp;=&amp;nbsp;[ADBMobile&amp;nbsp;trackingIdentifier]; 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> userIdentifier </p> </td> 
   <td colname="col2"> <p>If a custom identifier has been set, the user identifier is returned. If a custom identifier is not set, <span class="codeph"> nil </span> is returned. </p> <p>Default: <span class="codeph"> nil </span> </p> <p> <p>Tip:  If your app upgrades from the Experience Cloud 3.x to 4.x SDK, the previous custom or automatically generated visitor ID is retrieved and stored as the custom user identifier. This preserves visitor data between upgrades of the SDK. </p> </p> <p>For new installations on the 4.x SDK, the user identifier is <span class="codeph"> nil </span> until set. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      +&amp;nbsp;(NSString&amp;nbsp;*)&amp;nbsp;userIdentifier; 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      NSString&amp;nbsp;*uid&amp;nbsp;=&amp;nbsp;[ADBMobile&amp;nbsp;userIdentifier]; 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> setUserIdentifier: </p> </td> 
   <td colname="col2"> <p>Sets the user identifier to <span class="codeph"> identifier </span>. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      +&amp;nbsp;(void)&amp;nbsp;setUserIdentifier:(NSString&amp;nbsp;*)identifier; 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      [ADBMobile&amp;nbsp;setUserIdentifier:@"billybob"]; 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> debugLogging </p> </td> 
   <td colname="col2"> <p>Returns the current debug logging preference. </p> <p>Default: NO </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      +&amp;nbsp;(BOOL)&amp;nbsp;debugLogging; 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      BOOL&amp;nbsp;debugging&amp;nbsp;=&amp;nbsp;[ADBMobile&amp;nbsp;debugLogging]; 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> setDebugLogging: </p> </td> 
   <td colname="col2"> <p>Sets the debug logging preference to <span class="codeph"> debug </span>. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      +&amp;nbsp;(void)&amp;nbsp;setDebugLogging:(BOOL)debug; 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      [ADBMobile&amp;nbsp;setDebugLogging:YES]; 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> keepLifecycleSessionAlive </p> </td> 
   <td colname="col2"> <p>Indicates to the SDK that your next resume from background should not start a new session, regardless of the value of lifecycle session timeout in your config file. </p> <p> <p>Tip:  This method is intended to be used for apps that register for notifications while in background and should only be called from the code that runs while your app is in the background. </p> </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      +&amp;nbsp;(void)&amp;nbsp;keepLifecycleSessionAlive; 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      [ADBMobile&amp;nbsp;keepLifecycleSessionAlive]; 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> collectLifecycleData </p> </td> 
   <td colname="col2"> <p>Indicates to the SDK that lifecycle data should be collected for use across all solutions in the SDK. See <a href="../metrics.md#concept_77CA5CEB51D1418FB98EC7C044682A05" format="dita" scope="local"> Lifecycle Metrics </a>. </p> <p> <p>Tip:  The preferred location to invoke this method is in <span class="codeph"> application:didFinishLaunchingWithOptions: </span> </p> </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      +&amp;nbsp;(void)&amp;nbsp;collectLifecycleData; 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      [ADBMobile&amp;nbsp;collectLifecycleData]; 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>collectLifecycleDataWithAdditionalData: </p> </td> 
   <td colname="col2"> <p> <p>Important:  To use <span class="codeph"> collectLifecycleDataWithAdditionalData: </span>, you must have SDK version 4.4 or later. </p> </p> <p>Allows you to pass in additional data when collecting lifecycle metrics. </p> <p> <p>Tip:  This method must be called from the entry point of your app. Where applicable, this may include one or both of the methods <span class="codeph"> application:didFinishLaunchingWithOptions: </span> and/or <span class="codeph"> applicationWillEnterForeground: </span> in your AppDelegate class. </p> </p> <p> <p>Important:  Data that is passed to the SDK via <span class="codeph"> collectLifecycleDataWithAdditionalData: </span> will be persisted by the SDK in <span class="codeph"> NSUserDefaults </span>. The SDK will strip values in the <span class="codeph"> NSDictionary </span> parameter that are not of type <span class="codeph"> NSString </span> or <span class="codeph"> NSNumber </span>. </p> </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      +&amp;nbsp;(void)&amp;nbsp;collectLifecycleDataWithAdditionalData:(nullable&amp;nbsp;NSDictionary&amp;nbsp;*)data; 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      [ADBMobile&amp;nbsp;collectLifecycleDataWithAdditionalData:@{@"entryType":@"appShortcutIcon"}]; 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>overrideConfigPath </p> </td> 
   <td colname="col2"> <p> <p>Important:  To use <span class="codeph"> overrideConfigPath </span>, you must have SDK version 4.2 or later. </p> </p> <p>Lets you load a different ADBMobile JSON config file when the application starts. The different configuration is used until the application is closed. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      +&amp;nbsp;(void)&amp;nbsp;overrideConfigPath:&amp;nbsp;(nullable&amp;nbsp;NSString&amp;nbsp;*)&amp;nbsp;path; 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      NSString&nbsp;*filePath&nbsp;=&nbsp;[[NSBundle&nbsp;mainBundle]&nbsp;pathForResource:@"ExampleJSONFile"&nbsp;ofType:@"json"]; 
     
[ADBMobile&nbsp;overrideConfigPath:filePath]; 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>setPushIdentifier </p> </td> 
   <td colname="col2"> <p>Sets the device token for push notifications. </p> <p> <p>Important:  This method should only be used in the <span class="codeph"> application:didRegisterForRemoteNotificationsWithDeviceToken: </span> method. </p> </p> <p><b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      +&amp;nbsp;(void)&amp;nbsp;setPushIdentifier:(NSData&amp;nbsp;*)deviceToken; 
    </codeblock> <p><b>Example:</b> </p> 
    <codeblock class="syntax c">
      -&nbsp;(void)&nbsp;application:(UIApplication&nbsp;*)application&nbsp;didRegisterForRemoteNotificationsWithDeviceToken:(NSData&nbsp;*)deviceToken&nbsp;{ 
     
&nbsp;&nbsp;&nbsp;&nbsp;[ADBMobile&nbsp;setPushIdentifier:deviceToken];&nbsp; 
     
} 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>setAdvertisingIdentifier </p> </td> 
   <td colname="col2"> <p>Sets the IDFA in the SDK. If the IDFA has been set in the SDK, the IDFA will be sent in lifecycle. It can also be accessed in Signals (Postbacks). </p> <p> <p>Tip:  Retrieve the IDFA from Apple APIs <b>only</b> if you are using an ad service. If you retrieve IDFA, and are not using it properly, your app might be rejected. </p> </p> <p><b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      +&amp;nbsp;(void)&amp;nbsp;setAdvertisingIdentifier:(NSString&amp;nbsp;*)identifier; 
    </codeblock> <p><b>Example:</b> </p> 
    <codeblock class="syntax c">
      NSString&nbsp;*idfa&nbsp;=&nbsp;[[[ASIdentifierManager&nbsp;sharedManager]&nbsp;advertisingIdentifier]&nbsp;UUIDString]; 
     
[ADBMobile&nbsp;setAdvertisingIdentifier:idfa]; 
    </codeblock> </td> 
  </tr> 
 </tbody> 
</table>

## ADBMobileAppExtensionType enum {#section_18DB491D0ABC4765BB5A467D8FEF4F1B}

```
/** 
 * @brief An enum type. 
 * The possible types of app extension you might use 
 * @see setAppExtensionType 
 */ 
typedef NS_ENUM(NSUInteger, ADBMobileAppExtensionType) { 
 ADBMobileAppExtensionTypeRegular = 0, /*!< Enum value ADBMobileAppExtensionTypeRegular. */ 
 ADBMobileAppExtensionTypeStandAlone = 1 /*!< Enum value ADBMobileAppExtensionTypeStandAlone. */ 
};
```

