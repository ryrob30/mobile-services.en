---
description: The general process to measure video is very similar across all AppMeasurement platforms. This section provides a basic overview of the developer tasks along with code samples.
seo-description: The general process to measure video is very similar across all AppMeasurement platforms. This section provides a basic overview of the developer tasks along with code samples.
seo-title: Video Analytics
title: Video Analytics
uuid: 0d2731f3-77a9-4db1-9a8c-1e56c212ecb4
index: y
internal: n
snippet: y
---

# Video Analytics{#video-analytics}

The general process to measure video is very similar across all AppMeasurement platforms. This section provides a basic overview of the developer tasks along with code samples.

<a id="section_E84987F878AB4A3A83AE700FEC4C9D4D"></a>

For more information about Video measurement is described in detail in the [Measuring Video in Analytics](https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/video/) guide.  The following table lists the media data that is sent to Analytics. Use processing rules to map the context data in the Context Data Variable column to an Analytics variable as described in the Variable Type column. 

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

## Track Player Events {#section_C7F43AECBC0D425390F7FCDF3035B65D}

To measure video playback, The `mediaPlay`, `mediaStop`, and `mediaClose` methods need to be called at the appropriate times. For example, when the player is paused, `mediaStop`. `mediaPlay` is called when playback starts or is resumed.

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
   <td colname="col1"> open </td> 
   <td colname="col2"> <p> Opens a video for tracking. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax cpp">
      void&amp;nbsp;open(QString&amp;nbsp;name,&amp;nbsp;double&amp;nbsp;length,&amp;nbsp;QString&amp;nbsp;playerName,&amp;nbsp;QString&amp;nbsp;playerID&amp;nbsp;=&amp;nbsp;QString()); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax cpp">
      ADBMediaAnalytics::sharedInstance()-&gt;open("name",&amp;nbsp;10.0,&amp;nbsp;"playerName",&amp;nbsp;"playerID"); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> openAd </td> 
   <td colname="col2"> <p> Opens a <span class="codeph"> MediaSettings </span> object for tracking. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax cpp">
      void&amp;nbsp;openAd(QString&amp;nbsp;name,&amp;nbsp;double&amp;nbsp;length,&amp;nbsp;QString&amp;nbsp;playerName,&amp;nbsp;QString&amp;nbsp;parentName,&amp;nbsp;QString&amp;nbsp;parentPod,&amp;nbsp;double&amp;nbsp;parentPodPosition,&amp;nbsp;QString&amp;nbsp;CPM); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax cpp">
      ADBMediaAnalytics::sharedInstance()-&gt;openAd("name",&amp;nbsp;10,&amp;nbsp;"playerName",&amp;nbsp;"parentName",&amp;nbsp;"podName",&amp;nbsp;0,&amp;nbsp;"CPM"); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> close </td> 
   <td colname="col2"> <p> Closes the media item named <i>name</i>. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax cpp">
      void&amp;nbsp;close(QString&amp;nbsp;name); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax cpp">
      ADBMediaAnalytics::sharedInstance()-&gt;close("name"); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> play </td> 
   <td colname="col2"> <p> Plays the media item named <i>name</i> at the given <i>offset</i> (in seconds). </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax cpp">
      void&amp;nbsp;play(QString&amp;nbsp;name,&amp;nbsp;double&amp;nbsp;offset); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax cpp">
      ADBMediaAnalytics::sharedInstance()-&gt;play("name",&amp;nbsp;0); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> complete </td> 
   <td colname="col2"> <p> Manually mark the media item as complete at the <i>offset</i> provided (in seconds). </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax cpp">
      void&amp;nbsp;complete(QString&amp;nbsp;name,&amp;nbsp;double&amp;nbsp;offset); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax cpp">
      ADBMediaAnalytics::sharedInstance()-&gt;complete("name",&amp;nbsp;0); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> stop </td> 
   <td colname="col2"> <p> Notifies the media module that the video has been stopped or paused at the given <i>offset</i>. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax cpp">
      stop(QString&amp;nbsp;name,&amp;nbsp;double&amp;nbsp;offset); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax cpp">
      ADBMediaAnalytics::sharedInstance()-&gt;stop("name",&amp;nbsp;0); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> click </td> 
   <td colname="col2"> <p> Notifies the media module that the media item has been clicked. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax cpp">
      void&amp;nbsp;click(QString&amp;nbsp;name,&amp;nbsp;double&amp;nbsp;offset); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax cpp">
      ADBMediaAnalytics::sharedInstance()-&gt;close("name",&amp;nbsp;0); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> track </td> 
   <td colname="col2"> <p>Sends a track action call (no page view) for the current media state. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax cpp">
      track(QString&amp;nbsp;name,&amp;nbsp;QHash&lt;QString,&amp;nbsp;QString&gt;&amp;nbsp;additionalData&amp;nbsp;=&amp;nbsp;QHash&lt;QString,&amp;nbsp;QString&gt;()); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax cpp">
      ADBMediaAnalytics::sharedInstance()-&gt;track("name",&amp;nbsp;null); 
    </codeblock> </td> 
  </tr> 
 </tbody> 
</table>

