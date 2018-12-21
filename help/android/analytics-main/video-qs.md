---
description: Here is some information about measuring video on Android by the video measurement solution.
keywords: android;library;mobile;sdk
seo-description: Here is some information about measuring video on Android by the video measurement solution.
seo-title: Video Analytics
solution: Marketing Cloud,Analytics
title: Video Analytics
topic: Developer and implementation
uuid: a137cc27-dc28-48c0-b08e-2ca17d2c7e1d
---

# Video Analytics{#video-analytics}

Here is some information about measuring video on Android by the video measurement solution.

>[!TIP]
>
>During video playback, frequent "heartbeat" calls are sent to this service to measure time played. These heartbeat calls are sent every 10 seconds, which results in granular video engagement metrics and more accurate video fallout reports. For more information about Adobe's video measurement solution, see [Measuring Video in Adobe Analytics using Video Heartbeat](https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/hbvideo/).

The general process to measure video is similar across all platforms. This content provides an overview of the developer tasks with code samples.

This topic contains the following information:

* [Map Player Events to Analytics Variables](../analytics-main/video-qs.md#section_E84987F878AB4A3A83AE700FEC4C9D4D) 
* [Configure Media Settings](../analytics-main/video-qs.md#section_929945D4183C428AAF3B983EFD3E2500) 
* [Track Player Events](../analytics-main/video-qs.md#section_C7F43AECBC0D425390F7FCDF3035B65D) 
* [Classes](../analytics-main/video-qs.md#section_16838332727348F990305C0C6B0D795C) 
* [Media Measurement Class and Method Reference](../analytics-main/video-qs.md#section_50DF9359A7B14DF092634C8E913C77FE)

## Map Player Events to Analytics Variables {#section_E84987F878AB4A3A83AE700FEC4C9D4D}

The following table lists the media data that is sent to Analytics. Processing rules are used to map the context data in the **Context Data Variable** column to an Analytics variable in the **Variable Type** column. 

<table id="table_BB4B4141447545A7B8FC05AC3AA10DD3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Context Data Variable </p> </th> 
   <th colname="col2" class="entry"> <p>Variable Type </p> </th> 
   <th colname="col3" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> a.media.name </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_76D7B66ED81F44C19162FAF191EB05FD"> 
      <li id="li_00D84D3A724A4A62A873914578B1170F"> <p>eVar </p> </li> 
      <li id="li_5031B8E8AA9A400D83BFAF3C44596B45"> <p>Default expiration: Visit </p> </li> 
      <li id="li_A13A88CE7952433BAB35380B7C799417"> <p>Custom Insight (s.prop, used for video pathing) </p> </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p>(<b>Required</b>) When a visitor views the video in some way, this context data variable collects the name of the video, as specified in the implementation. You can add classifications for this variable. </p> <p>(<b>Optional</b>) The Custom Insight variable provides video pathing information. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> a.media.name </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_3F75EF93E4174BCF96BC00C3457B58C0"> 
      <li id="li_CE658F4E1503418989E4D17F8608F0D8"> <p>Custom Insight (s.prop) </p> </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p>(<b>Optional</b>) Provides video pathing information. </p> <p> <p>Important:  Pathing must be enabled for this variable by ExpCare. </p> </p> <p>Event type: Custom Insight (s.prop) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> a.media.segment </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_1733BF26839142CF85F026A5A40EBF36"> 
      <li id="li_B2B3B050682844C38E4CF38534C923B3"> <p>eVar </p> </li> 
      <li id="li_7070651BEBCC4031A0F95BBF5BA87E95"> <p>Default expiration: Page view </p> </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p>(<b>Required</b>) Collects video segment data, including the segment name and the order in which the segment occurs in the video. </p> <p>This variable is populated by enabling the <span class="codeph"> segmentByMilestones </span> variable when automatically tracking player events or by setting a custom segment name when manually tracking player events. </p> <p>For example, when a visitor views the first segment in a video, SiteCatalyst might collect the following in the Segments eVar: </p> <p> <pre>1:M:0-25</pre> </p> <p>The default video data collection method collects data at the following points: </p> <p> 
     <ul id="ul_7C3E780CE23F4308B53C53F49FD76667"> 
      <li id="li_1105B416152342418FEF65B2505641CD">video start (play) </li> 
      <li id="li_DD1B4593611F40C482476AF394B28F96">segment begin </li> 
      <li id="li_7A59263DD551489AA24182EF4D50C131">video end (stop) </li> 
     </ul> </p> <p>Analytics counts the first segment view at the start of the segment, when the visitor starts watching. Subsequent segment views as the segment begins. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> a.contentType </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_C356710043304C87B3A3FE2D25E6A2BA"> 
      <li id="li_121ECFC00B7E4A76A9E313E012C8592B"> <p>eVar </p> </li> 
      <li id="li_0ED6A20842B748BEAF1FFBCEE7980729"> <p>Default expiration: Page view </p> </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p>Collects data about the type of content that is viewed by a visitor. Hits sent by video measurement are assigned a content type of <span class="codeph"> video </span>. </p> <p>From a video measurement perspective, <b>Content Type</b> allows you identify video visitors and calculate video conversion rates. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> a.media.timePlayed </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_9D323694F3504F72B593F4101BF8B469"> 
      <li id="li_F4B5EA07FDD04D06B3F77BC864D5D3A1"> <p>Event </p> </li> 
      <li id="li_02125BF04EB849A49E19EB13D8DC1D2D"> <p>Type: Counter </p> </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p>Counts the time, in seconds, that is spent watching a video since the last data collection process (image request). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> a.media.view </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_644EE8B78987465C8E056A71436BAAF0"> 
      <li id="li_5BF4538E9C244C94A18BE4B6B34C48B2"> <p>Event </p> </li> 
      <li id="li_A1BE06D79A564607BE2BAA95BF3A44F3"> <p>Type: Counter </p> </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p>Indicates that a visitor has viewed some portion of a video. However, it does not provide any information about how much, or which part, of a video that the visitor viewed. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>a.media.segmentView </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_9DBA1D26971A4590B3E4271A9BBD26A6"> 
      <li id="li_9B2E85AB3FAD4A479311A7B246D0E9CC"> <p>Event </p> </li> 
      <li id="li_DFFF04840743444A8342782C720EEAFC"> <p>Type: Counter </p> </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p>Indicates that a visitor has viewed some portion of a video segment. However, it does not provide any information about how much, or which part, of a video that the visitor viewed. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>a .media.complete </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_C3F877322AE640D983AEAB8095787DEF"> 
      <li id="li_E623122CC7DA4C53A7C5C9F24B962FC7"> <p>Event </p> </li> 
      <li id="li_74F9DF23FD6E43BAB9216A35DB5815DE"> <p>Type: Counter </p> </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p>Indicates that a user has viewed a complete video. By default, the complete event is measured 1 second before the end of the video. </p> <p>During implementation, you can specify how many seconds from the end of the video you would like to consider a view as being complete. For live video and other streams that do not have a defined end, you can specify a custom point to measure completes (for example, after a specific time viewed). </p> </td> 
  </tr> 
 </tbody> 
</table>

## Configure Media Settings {#section_929945D4183C428AAF3B983EFD3E2500}

Configure a `MediaSettings` object with the settings you want to use to track video:

```java
MediaSettings mySettings = Media.settingsWith("name", 10, "playerName", "playerId");
```

## Track Player Events {#section_C7F43AECBC0D425390F7FCDF3035B65D}

To measure video playback, the `mediaPlay`, `mediaStop`, and `mediaClose` methods need to be called at the appropriate times. For example, when the player is paused, call `mediaStop`. `mediaPlay` is called when playback starts or is resumed.

## Classes {#section_16838332727348F990305C0C6B0D795C}

**Class: MediaSettings**

```java
public String name; 
public String playerName; 
public String playerID; 
public double length; 
public String channel; 
public String milestones; 
public String offsetMilestones; 
public boolean segmentByMilestones; 
public boolean segmentByOffsetMilestones; 
public int trackSeconds = 0; 
public int completeCloseOffsetThreshold = 1; 
 
// MediaAnalytics Ad settings 
public String parentName; 
public String parentPod; 
public String CPM; 
public double parentPodPosition; 
public boolean isMediaAd;
```

** Class: MediaState**

```java
public Date openTime = new Date(); 
public String name; 
public String segment; 
public String playerName; 
public String mediaEvent; 
public int offsetMilestone; 
public int segmentNum; 
public int milestone; 
public double length; 
public double offset; 
public double percent; 
public double timePlayed; 
public double segmentLength; 
public boolean complete = false; 
public boolean clicked = false; 
public boolean ad; 
public boolean eventFirstTime;
```

## Media Measurement Class and Method Reference {#section_50DF9359A7B14DF092634C8E913C77FE}

<table id="table_09C45190983F41B4A5790B756ADACE51"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Method </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> settingsWith </td> 
   <td colname="col2"> <p> Returns a <span class="codeph"> MediaSettings </span> object with specified parameters. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax java">
      public&amp;nbsp;static&amp;nbsp;MediaSettings&amp;nbsp;adSettingsWith(String&amp;nbsp;name,&amp;nbsp;double&amp;nbsp;length,&amp;nbsp;String&amp;nbsp;playerName,&amp;nbsp;String&amp;nbsp;parentName,&amp;nbsp;String&amp;nbsp;parentPod,&amp;nbsp;double&amp;nbsp;parentPodPosition,&amp;nbsp;String&amp;nbsp;CPM); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax java">
      MediaSettings&amp;nbsp;mySettings&amp;nbsp;=&amp;nbsp;Media.settingsWith("name",&amp;nbsp;10,&amp;nbsp;"playerName",&amp;nbsp;"playerId"); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> adSettingsWith </td> 
   <td colname="col2"> <p> Returns a <span class="codeph"> MediaSettings </span> object for use with tracking an ad video. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax java">
      public&amp;nbsp;static&amp;nbsp;MediaSettings&amp;nbsp;adSettingsWith(String&amp;nbsp;name,&amp;nbsp;double&amp;nbsp;length,&amp;nbsp;String&amp;nbsp;playerName,&amp;nbsp;String&amp;nbsp;parentName,&amp;nbsp;String&amp;nbsp;parentPod,&amp;nbsp;double&amp;nbsp;parentPodPosition,&amp;nbsp;String&amp;nbsp;CPM); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax java"></codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> open </td> 
   <td colname="col2"> <p> Opens a <span class="codeph"> MediaSettings </span> object for tracking. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax java">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;open(MediaSettings&amp;nbsp;settings,&amp;nbsp;MediaCallback&amp;nbsp;callback); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax java">
      Media.open(mySettings,&nbsp;new&nbsp;Media.MediaCallback()&nbsp;{&nbsp;@Override&nbsp;public&nbsp;void&nbsp;call(Object&nbsp;item)&nbsp;{&nbsp;&nbsp;//&nbsp;monitor&nbsp;callback&nbsp;if&nbsp;you&nbsp;want&nbsp;to&nbsp;be&nbsp;notified&nbsp;every&nbsp;second&nbsp;the&nbsp;media&nbsp;is&nbsp;playing&nbsp;}});
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> close </td> 
   <td colname="col2"> <p> Closes the media item named <i>name</i>. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax java">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;close(String&amp;nbsp;name); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax java">
      Media.close("name"); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> play </td> 
   <td colname="col2"> <p> Plays the media item named <i>name</i> at the given <i>offset</i> in seconds. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax java">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;play(String&amp;nbsp;name,&amp;nbsp;double&amp;nbsp;offset); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax java"></codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> complete </td> 
   <td colname="col2"> <p> Manually mark the media item as complete at the <i>offset</i> provided in seconds. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax java">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;complete(String&amp;nbsp;name,&amp;nbsp;double&amp;nbsp;offset); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax java">
      Media.complete("name",&amp;nbsp;0); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> stop </td> 
   <td colname="col2"> <p> Notifies the media module that the video has been stopped or paused at the given <i>offset</i>. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax java">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;stop(String&amp;nbsp;name,&amp;nbsp;double&amp;nbsp;offset); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax java">
      Media.stop("name",&amp;nbsp;0); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> click </td> 
   <td colname="col2"> <p> Notifies the media module that the media item has been clicked. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax java">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;click(String&amp;nbsp;name,&amp;nbsp;double&amp;nbsp;offset); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax java">
      Media.click("name",&amp;nbsp;0); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> track </td> 
   <td colname="col2"> <p>Sends a track action call (no page view) for the current media state. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax java">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;track(String&amp;nbsp;name,&amp;nbsp;Map&lt;String,&amp;nbsp;Object&gt;&amp;nbsp;data); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax java">
      Media.track("name",&amp;nbsp;null); 
    </codeblock> </td> 
  </tr> 
 </tbody> 
</table>
