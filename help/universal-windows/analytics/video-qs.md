---
description: Information to help you with Video Analytics.
seo-description: Information to help you with Video Analytics.
seo-title: Video Analytics
solution: Marketing Cloud,Analytics
title: Video Analytics
topic: Developer and implementation
uuid: f45dac3b-cd2e-4fba-a3b2-c243640ecfa4
index: y
internal: n
snippet: y
---

# Video Analytics{#video-analytics}

Information to help you with Video Analytics.

Video measurement is described in detail in the [Measuring Video in Analytics](https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/video/) guide. The general process to measure video is very similar across all AppMeasurement platforms. This quick start section provides a basic overview of the developer tasks along with code samples. 
The following table lists the media data that is sent to Analytics. Use processing rules to map the context data in the Context Data Variable column to an Analytics variable as described in the Variable Type column. 

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
   <td colname="col2"> <p>eVar </p> <p>Default expiration: Visit </p> <p>Custom Insight (s.prop, used for video pathing) </p> </td> 
   <td colname="col3"> <p>(Required) Collects the name of the video, as specified in the implementation, when a visitor views the video in some way.You can add classifications for this variable. </p> <p>(Optional) The Custom Insight variable provides video pathing information. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> a.media.name </p> </td> 
   <td colname="col2"> <p>Custom Insight (s.prop) </p> </td> 
   <td colname="col3"> <p>(Optional) Provides video pathing information. Pathing must be enabled for this variable by ClientCare. </p> <p>Event type: Custom Insight (s.prop) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> a.media.segment </p> </td> 
   <td colname="col2"> <p>eVar </p> <p>Default expiration: Page view </p> </td> 
   <td colname="col3"> <p>(Required) Collects video segment data, including the segment name and the order in which the segment occurs in the video. </p> <p>This variable is populated by enabling the <span class="codeph"> segmentByMilestones </span> variable when tracking player events automatically, or by setting a custom segment name when tracking player events manually. </p> <p>For example, when a visitor views the first segment in a video, SiteCatalyst might collect the following in the Segments eVar: </p> <p> <pre>1:M:0-25</pre> </p> <p>The default video data collection method collects data at the following points: video start (play), segment begin, and video end (stop). Analytics counts the first segment view at the start of the segment, when the visitor starts watching. Subsequent segment views as the segment begins. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> a.contentType </p> </td> 
   <td colname="col2"> <p>eVar </p> <p>Default expiration: Page view </p> </td> 
   <td colname="col3"> <p>Collects data about the type of content viewed by a visitor. Hits sent by video measurement are assigned a content type of "video". </p> <p>This variable does not need to be reserved exclusively for video tracking. Having other content report content type using this same variable lets you analyze the distribution of visitors across the different types of content. For example, you could tag other content types using values such as “article" or “product page" using this variable. </p> <p>From a video measurement perspective, Content Type lets you identify video visitors and thereby calculate video conversion rates. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> a.media.timePlayed </p> </td> 
   <td colname="col2"> <p>Event </p> <p>Type: Counter </p> </td> 
   <td colname="col3"> <p>Counts the time, in seconds, spent watching a video since the last data collection process (image request). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> a.media.view </p> </td> 
   <td colname="col2"> <p>Event </p> <p>Type: Counter </p> </td> 
   <td colname="col3"> <p>Indicates that a visitor has viewed some portion of a video. However, it does not provide any information about how much, or what part, of a video the visitor viewed. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>a.media.segmentView </p> </td> 
   <td colname="col2"> <p>Event </p> <p>Type: Counter </p> </td> 
   <td colname="col3"> <p>Indicates that a visitor has viewed some portion of a video segment. However, it does not provide any information about how much, or what part, of a video the visitor viewed. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>a .media.complete </p> </td> 
   <td colname="col2"> <p>Event </p> <p>Type: Counter </p> </td> 
   <td colname="col3"> <p>Indicates that a user has viewed a complete video. By default, the complete event is measured 1 second before the end of the video. </p> <p>During implementation, you can specify how many seconds from the end of the video you would like to consider a view complete. For live video and other streams that don't have a defined end, you can specify a custom point to measure completes. For example, after a specific time viewed. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Configure Media Settings {#section_929945D4183C428AAF3B983EFD3E2500}

Configure a `MediaSettings` object with the settings you want to use to track video:

```js
var mySettings = ADB.Media.settingsWith("name", 10, "playerName", "playerId");
```

## Track Player Events {#section_C7F43AECBC0D425390F7FCDF3035B65D}

To measure video playback, The `Play`, `Stop`, and `Close` methods need to be called at the appropriate times. For example, when the player is paused, `Stop`. `Play` is called when playback starts or is resumed.

## Classes {#section_16838332727348F990305C0C6B0D795C}

**Class: MediaSettings**

```
property Platform::String ^name; 
property Platform::String ^playerName; 
property Platform::String ^playerID; 
property double length; 
property Platform::String ^channel; 
property Platform::String ^milestones; 
property Platform::String ^offsetMilestones; 
property bool segmentByMilestones; 
property bool segmentByOffsetMilestones; 
property int trackSeconds; 
property int completeCloseOffsetThreshold; 
 
// MediaAnalytics Ad settings 
property Platform::String ^parentName; 
property Platform::String ^parentPod; 
property Platform::String ^CPM; 
property double parentPodPosition; 
property bool isMediaAd;
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
   <td colname="col1"> SettingsWith <p>winJS: settingsWith </p> </td> 
   <td colname="col2"> <p> Returns a <span class="codeph"> MediaSettings </span> object with specified parameters. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax csharp">
      static&amp;nbsp;MediaSettings&amp;nbsp;^SettingsWith(Platform::String&amp;nbsp;^name,&amp;nbsp;double&amp;nbsp;length,&amp;nbsp;Platform::String&amp;nbsp;^playerName,&amp;nbsp;Platform::String&amp;nbsp;^playerID); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax javascript">
      var&amp;nbsp;mySettings&amp;nbsp;=&amp;nbsp;ADB.Media.settingsWith("name",&amp;nbsp;10,&amp;nbsp;"playerName",&amp;nbsp;"playerId"); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> AdSettingsWith <p>winJS: adSettingsWith </p> </td> 
   <td colname="col2"> <p> Returns a <span class="codeph"> MediaSettings </span> object for use with tracking an ad video. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax csharp">
      static&amp;nbsp;MediaSettings&amp;nbsp;^AdSettingsWith(Platform::String&amp;nbsp;^name,&amp;nbsp;double&amp;nbsp;length,&amp;nbsp;Platform::String&amp;nbsp;^playerName,&amp;nbsp;Platform::String&amp;nbsp;^parentName,&amp;nbsp;Platform::String&amp;nbsp;^parentPod,&amp;nbsp;double&amp;nbsp;parentPosition,&amp;nbsp;Platform::String&amp;nbsp;^CPM); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax javascript">
      var&amp;nbsp;myAdSettings&amp;nbsp;=&amp;nbsp;ADB.Media.adSettingsWith("name",&amp;nbsp;10,&amp;nbsp;"playerName",&amp;nbsp;"parentName",&amp;nbsp;"parentPod",&amp;nbsp;5,&amp;nbsp;"myCPM"); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Open <p>winJS: open </p> </td> 
   <td colname="col2"> <p>Tracks a media open using the settings defined in <span class="codeph"> settings </span> </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax csharp">
      static&amp;nbsp;void&amp;nbsp;Open(MediaSettings&amp;nbsp;^settings); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax javascript">
      ADB.Media.open(mySettings); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Close <p>winJS: close </p> </td> 
   <td colname="col2"> <p> Tracks a media close for the media item named <i>name</i>. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax csharp">
      static&amp;nbsp;void&amp;nbsp;Close(Platform::String&amp;nbsp;^name); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax javascript">
      ADB.Media.close("mediaName"); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Play <p>winJS: play </p> </td> 
   <td colname="col2"> <p>Tracks a media play for the media item named <i>name</i> at the given <i>offset</i> (in seconds). </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax csharp">
      static&amp;nbsp;void&amp;nbsp;Play(Platform::String&amp;nbsp;^name,&amp;nbsp;double&amp;nbsp;offset); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax javascript">
      ADB.Media.play("mediaName",&amp;nbsp;0); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Complete <p>winJS: complete </p> </td> 
   <td colname="col2"> <p> Manually mark the media item as complete at the <i>offset</i> provided (in seconds). </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax csharp">
      static&amp;nbsp;void&amp;nbsp;Complete(Platform::String&amp;nbsp;^name,&amp;nbsp;double&amp;nbsp;offset); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax javascript">
      ADB.Media.complete("mediaName",&amp;nbsp;8); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Stop <p>winJS: stop </p> </td> 
   <td colname="col2"> <p> Notifies the media module that the video has been stopped or paused at the given <i>offset</i>. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax csharp">
      static&amp;nbsp;void&amp;nbsp;Stop(Platform::String&amp;nbsp;^name,&amp;nbsp;double&amp;nbsp;offset); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax javascript">
      ADB.Media.stop("mediaName",&amp;nbsp;4); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Click <p>winJS: click </p> </td> 
   <td colname="col2"> <p> Notifies the media module that the media item has been clicked. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax csharp">
      static&amp;nbsp;void&amp;nbsp;Click(Platform::String&amp;nbsp;^name,&amp;nbsp;double&amp;nbsp;offset); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax javascript">
      ADB.Media.click("mediaName",&amp;nbsp;3); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Track <p>winJS: track </p> </td> 
   <td colname="col2"> <p>Sends a track action call (no page view) for the current media state. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax csharp">
      static&amp;nbsp;void&amp;nbsp;Track(Platform::String&amp;nbsp;^name,&amp;nbsp;Windows::Foundation::Collections::IMap&lt;Platform::String^,&amp;nbsp;Platform::Object^&gt;&amp;nbsp;^contextData); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax javascript">
      ADB.Media.track("mediaName",&amp;nbsp;null); 
    </codeblock> </td> 
  </tr> 
 </tbody> 
</table>

