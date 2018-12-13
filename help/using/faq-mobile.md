---
description: Frequently asked questions and answers for Adobe Mobile Services and a general description of features.
keywords: mobile
seo-description: Frequently asked questions and answers for Adobe Mobile Services and a general description of features.
seo-title: Frequently Asked Questions
solution: Marketing Cloud,Analytics
title: Frequently Asked Questions
topic: Metrics
uuid: 62a9241c-2ada-483a-a594-b023916cb0b6
index: y
internal: n
snippet: y
---

# Frequently Asked Questions{#frequently-asked-questions}

Frequently asked questions and answers for Adobe Mobile Services and a general description of features.

* [Adobe Mobile SDK](faq-mobile.md#section_9C2181F7B39A4BEB8EE6BCEFCF14C72F) 
* [Adobe Analytics](faq-mobile.md#section_78EC9D83791F477AAED678720CEBA9F6) 
* [Messaging](faq-mobile.md#section_5EFDD2B2EBA543C09902FF979C89F2EC) 
* [Location](faq-mobile.md#section_01208FE3B7764E0DADDCB9AD9E1FCD87) 
* [Acquisition](faq-mobile.md#section_B37F1129CD5843E890D0E54179455357)

## Adobe Mobile SDK {#section_9C2181F7B39A4BEB8EE6BCEFCF14C72F}

<table id="table_CC3D15C375E247A784EB58BD1599138A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Question </th> 
   <th colname="col2" class="entry"> Answer </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Do you make frequent updates with the SDK? </td> 
   <td colname="col2"> <p>Yes, we are constantly making updates in effort to get you the most feature rich, standard-compliant, and secure SDKs. We typically release a new version every month. These SDK updates are drop-in replacements (for version 4x) to aid in ease of implementation. For more information on our updates, see our <a href="https://marketing.adobe.com/resources/help/en_US/whatsnew/" format="https" scope="external"> Release Notes</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> What SDK version should I be on? </td> 
   <td colname="col2"> <p>Our current SDKs are on version 4.11. For more information, see our <a href="https://marketing.adobe.com/resources/help/en_US/whatsnew/" format="https" scope="external"> Release Notes</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Where can I download the SDKs? </td> 
   <td colname="col2"> <p>SDKs for individual mobile platforms may be downloaded by visiting the <a href="c-manage-app-settings/c-manage-app-settings.md#concept_3A1E216CB91D43C5BE343CF2D9398D27" format="dita" scope="local"> Manage App Settings</a> section. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> How do I configure the SDKs? </td> 
   <td colname="col2"> <p>After you have <a href="manage-apps/t-new-app.md#task_DB20EA0C8DF54C62B46858A77C53221F" format="dita" scope="local"> created a new app report suite</a>, navigate to Manage App Settings and configure all of the required options on the app information page. After you save your configuration, download the required SDKs from the bottom of the Manage App Settings page. The SDK will come pre-configured with the options you have saved and can be found in the ADBMobileConfig.json file within the SDK package. If you change any SDK settings on the Manage App Settings page, make sure you re-download the SDK files or update your ADBMobileConfig.json file with the necessary changes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Do the Adobe Mobile SDKs support IPv6 for iOS? </td> 
   <td colname="col2"> <p>The Adobe Mobile SDKs use the standard iOS and Android network stacks. For iOS, the SDK uses NSURLSession (iOS versions 7+) and NSURLConnection (iOS versions &lt;7) which are fully compliant with IPv6. Developers who have built or use their own networking stack may want to review if there are other mitigating considerations. </p> <p>Further information from <a href="https://developer.apple.com/library/content/documentation/NetworkingInternetWeb/Conceptual/NetworkingOverview/UnderstandingandPreparingfortheIPv6Transition/UnderstandingandPreparingfortheIPv6Transition.html#__/apple_ref/doc/uid/TP40010220-CH213-SW1" format="https" scope="external"> Apple</a>: <i>If you're writing a client-side app using high-level networking APIs such as NSURLSession and the CFNetwork frameworks and you connect by name, you should not need to change anything for your app to work with IPv6 addresses.</i> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Adobe Analytics {#section_78EC9D83791F477AAED678720CEBA9F6}

<table id="table_A0EE706BA75B4ADC98CF6CE60778A58F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Question </th> 
   <th colname="col2" class="entry"> Answer </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> What are Lifecycle Metrics? </td> 
   <td colname="col2"> <p>Lifecycle Metrics are "out-of-the-box" metrics that are automatically collected when the SDK is first implemented in your app. For more information, see <a href="https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/android/metrics.html#concept_E1B46EBFAF0147BDB408F47453757167" format="https" scope="external"> Lifecycle Metrics</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> How can I troubleshoot processing rules? </td> 
   <td colname="col2"> <p>For more information, see <a href="https://marketing.adobe.com/resources/help/en_US/reference/processing_rules_tips.html" format="https" scope="external"> Processing Rules Tips and Tricks</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Can I send my analytics data to multiple report suites? </td> 
   <td colname="col2"> <p>Yes. The SDKs provide the ability to send data to multiple Adobe Analytics report suites. To capture data in multiple report suites by using an image request, set the multiple report suite IDs in the <span class="uicontrol"> rsids</span> field under <span class="uicontrol"> analytics</span> section in the ADBMobileConfig.json file, delimited by commas and no spaces. For more information, see <a href="https://marketing.adobe.com/resources/help/en_US/mobile/ios/json_config.html" format="https" scope="external"> ADBMobile JSON Config</a> (see rsids variable). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> How are Mobile visits different from launches? </td> 
   <td colname="col2"> <p>A launch is measured by the SDK when a user opens the app for the first time or returns to the app after having been out of the app for longer than the specified timeout value. The typical timeout is 5 minutes (300 seconds) in lifecycleTimeout field, which is located in the ADBMobileConfig.json file. </p> <p>A visit is a server-side calculation by Adobe Analytics and is based on the first and last data hits that are sent by the SDK without exceeding a visit timeout. Typically, session timeouts are set at 30 minutes for a report suite. Although visits come from traditional web analytics, these hits still provide valuable insights into how users enter and exit from your app. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Messaging {#section_5EFDD2B2EBA543C09902FF979C89F2EC}

<table id="table_95B7704F36314032AEF744D2D2FE7EED"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Question </th> 
   <th colname="col2" class="entry"> Answer </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Are there size or other limitations on push notifications? </td> 
   <td colname="col2"> <p>Push notification messages have a 140 character limit. There are no limits on how many notifications might be sent or scheduled or how often notifications are sent. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Do you support custom payloads for push notifications? </td> 
   <td colname="col2"> <p>Yes, we provide for a custom push payload that may coded in JSON. Android and iOS payloads are restricted to 4KB and 2KB respectively. These payloads are sent to the app via a push or a local notification. For more information, see <a href="in-app-messaging/t-create-push-message/c-experience--push-message.md#concept_FFB89CED02B14436A2F922962FFFC040" format="dita" scope="local"> Experience: Push Message</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Are there size limitations on in-app messages? </td> 
   <td colname="col2"> <p>Published and active in-app messages created in Adobe Mobile Services are hosted on a server with a 15MB size restriction per app report suite. While this restriction applies to message content and resources hosted with Adobe, there are no restrictions on what resources the in-app message may refer to on other hosts or those within the app. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Can I use my own HTML for in-app messages? </td> 
   <td colname="col2"> <p>Yes, we support custom HTML for your in-app messages. For more information, see <a href="in-app-messaging/t-in-app-message/c-experience-in-app-message.md#concept_5BF20C67C4D4425C8A41CE17AB162DE4" format="dita" scope="local"> Experience: In-App Message</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> What triggers can I use to send push notifications or in-app messages? </td> 
   <td colname="col2"> <p>Marketers may choose any Analytics data or event that is being sent as a trigger to display in-app messages. In-app messages use triggers that happen locally on the device. If multiple triggers are chosen, all triggers must occur in the same hit for the message to display. For more information, see <a href="in-app-messaging/t-in-app-message/c-experience-in-app-message.md#concept_5BF20C67C4D4425C8A41CE17AB162DE4" format="dita" scope="local"> Experience: In-App Message</a>. </p> <p>Push messages are sent using pre-existing Adobe Analytics segments or custom segments that may be created on historic Analytics data already collected. For more information, see <a href="in-app-messaging/t-create-push-message/c-experience--push-message.md#concept_FFB89CED02B14436A2F922962FFFC040" format="dita" scope="local"> Experience: Push Message</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Why am I getting an error with the in-app, push, or marketing link name that I typed? </p> </td> 
   <td colname="col2"> <p>You cannot use the same in-app message, push message, or marking link name in multiple apps that use the same parent report suite or VRS. To resolve this issue, enter another name for your in-app message, push message, or marketing link. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Location {#section_01208FE3B7764E0DADDCB9AD9E1FCD87}

<table id="table_13E9CD4924804971A65C091C23A55B10"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Question </th> 
   <th colname="col2" class="entry"> Answer </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Is there a limit on how many Points of Interest (POIs) I can have? </td> 
   <td colname="col2"> <p>There no specific restriction, but for ideal performance and due to memory restrictions on the user's device, we recommend that you create or upload a maximum of 5000 POIs. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Acquisition {#section_B37F1129CD5843E890D0E54179455357}

<table id="table_EF10A129108D4BC0B9EB9ED1A3C1721B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Question </th> 
   <th colname="col2" class="entry"> Answer </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Can I attribute campaigns to in-app activities? </td> 
   <td colname="col2"> <p>Yes. Adobe Mobile Services can help you build marketing tricks that help promote and drive traffic to your apps and tie acquisition campaigns to in-app analytics and conversions. For more information, see <a href="acquisition-main/acquisition-main.md#concept_542D3F9599614CB89ACF558683E9D34B" format="dita" scope="local"> Acquisition </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> How can I set up links to acquire and track new app users? </td> 
   <td colname="col2"> <p>You can create marketing links that route users to download applications from the Apple App Store and Google Play. These links allow you to attribute your success events to the downloads. For more information, see <a href="acquisition-main/c-marketing-links-builder/c-marketing-links-builder.md#concept_6EC4426B1AEE42EAAB06887B58C604B6" format="dita" scope="local"> Marketing Links Builder</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

