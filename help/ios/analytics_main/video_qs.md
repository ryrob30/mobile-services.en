---
description: Here is some information about measuring video on iOS by using milestone video measurement.
seo-description: Here is some information about measuring video on iOS by using milestone video measurement.
seo-title: Video Analytics
solution: Marketing Cloud,Analytics
title: Video Analytics
topic: Developer and implementation
uuid: 1249b94c-c0fb-4a05-a7a4-10372f868d1c
index: y
internal: n
snippet: y
translate: y
---

# Video Analytics

Here is some information about measuring video on iOS by using milestone video measurement.

>[!TIP]
>
>During video playback, frequent "heartbeat" calls are sent to this service to measure time played. These heartbeat calls are sent every 10 seconds, which results in granular video engagement metrics and more accurate video fallout reports. For more information, see [Measuring Video in Adobe Analytics using Video Heartbeat](https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/hbvideo/).

The general process to measure video is very similar across all platforms. This content provides a basic overview of the developer tasks with code samples.

This topic contains the following information:

* [Map Player Events to Analytics Variables](../analytics_main/video_qs.md#section_E84987F878AB4A3A83AE700FEC4C9D4D) 
* [Configure Media Settings](../analytics_main/video_qs.md#section_929945D4183C428AAF3B983EFD3E2500) 
* [Track Player Events](../analytics_main/video_qs.md#section_C7F43AECBC0D425390F7FCDF3035B65D) 
* [Classes](../analytics_main/video_qs.md#section_16838332727348F990305C0C6B0D795C) 
* [Media Measurement Class and Method Reference](../analytics_main/video_qs.md#section_50DF9359A7B14DF092634C8E913C77FE)

## Map Player Events to Analytics Variables {#section_E84987F878AB4A3A83AE700FEC4C9D4D}

The following table lists the media data that is sent to Analytics. Use processing rules to map the context data in the ** Context Data Variable** column to an Analytics variable as described in the **Variable Type** column. 

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
   <td colname="col3"> <p>(Required) Collects the name of the video, as specified in the implementation, when a visitor views the video in some way. You can add classifications for this variable. </p> <p>(Optional) The Custom Insight variable provides video pathing information. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> a.media.name </p> </td> 
   <td colname="col2"> <p>Custom Insight (s.prop) </p> </td> 
   <td colname="col3"> <p>(Optional) Provides video pathing information. Pathing must be enabled for this variable by ClientCare. </p> <p>Event type: Custom Insight (s.prop) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> a.media.segment </p> </td> 
   <td colname="col2"> <p>eVar </p> <p>Default expiration: Page view </p> </td> 
   <td colname="col3"> <p>(Required) Collects video segment data, including the segment name and the order in which the segment occurs in the video. </p> <p>This variable is populated by enabling the <span class="codeph"> segmentByMilestones </span> variable when tracking player events automatically, or by setting a custom segment name when tracking player events manually. </p> <p>For example, when a visitor views the first segment in a video, SiteCatalyst might collect the following in the Segments eVar: </p> <p> <span class="codeph"> 1:M:0-25 </span> </p> <p>The default video data collection method collects data at the following points: </p> <p> 
     <ul id="ul_000B139999134146B36122048D67E6E1"> 
      <li id="li_85B115023B37463B885FDB739ED04FBA">video start (play) </li> 
      <li id="li_F4A8EB8BD1CC428B8ADE2AE584A03943">segment begin </li> 
      <li id="li_035B131F9B3C4437A9749DF41D558B47">video end (stop) </li> 
     </ul> </p> <p>Analytics counts the first segment view at the start of the segment, when the visitor starts watching. Subsequent segment views as the segment begins. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> a.contentType </p> </td> 
   <td colname="col2"> <p>eVar </p> <p>Default expiration: Page view </p> </td> 
   <td colname="col3"> <p>Collects data about the type of content that is viewed by a visitor. Hits sent by video measurement are assigned a content type of <span class="codeph"> video </span>. </p> <p>This variable does not need to be reserved exclusively for video tracking. Having other content report content type by using this same variable lets you analyze the distribution of visitors across the different types of content. For example, you could tag other content types using values such as “article" or “product page" using this variable. </p> <p>From a video measurement perspective, Content Type allows you to identify video visitors and calculate video conversion rates. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> a.media.timePlayed </p> </td> 
   <td colname="col2"> <p>Event </p> <p>Type: Counter </p> </td> 
   <td colname="col3"> <p>Counts the time, in seconds, spent watching a video since the last data collection process (image request). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> a.media.view </p> </td> 
   <td colname="col2"> <p>Event </p> <p>Type: Counter </p> </td> 
   <td colname="col3"> <p>Indicates that a visitor has viewed some portion of a video. </p> <p>However, it does not provide any information about how much, or what part, of a video the visitor viewed. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>a.media.segmentView </p> </td> 
   <td colname="col2"> <p>Event </p> <p>Type: Counter </p> </td> 
   <td colname="col3"> <p>Indicates that a visitor has viewed some portion of a video segment. </p> <p>However, it does not provide any information about how much, or what part, of a video the visitor viewed. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> .media.complete </p> </td> 
   <td colname="col2"> <p>Event </p> <p>Type: Counter </p> </td> 
   <td colname="col3"> <p>Indicates that a user has viewed a complete video. By default, the complete event is measured 1 second before the end of the video. </p> <p>During implementation, you can specify how many seconds from the end of the video you would like to consider a view complete. For live video and other streams that do not have a defined end, you can specify a custom point to measure completes, for example, after a specific time viewed. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Configure Media Settings {#section_929945D4183C428AAF3B983EFD3E2500}

Configure an `ADBMediaSettings` object with the settings you want to use to track video:

```
ADBMediaSettings *mediaSettings = [ADBMobile mediaCreateSettingsWithName:MEDIA_NAME  
length:MEDIA_LENGTH playerName:PLAYER_NAME playerID:PLAYER_ID]; 
 
// milestone tracking. Use either standard milestones (percentage of total length) 
// or offset milestones (seconds elapsed from the beginning of the video) 
mediaSettings.milestones = @"25,50,75"; 
mediaSettings.segmentByMilestones = YES; 
 
mediaSettings.offsetMilestones = @"60,120"; 
mediaSettings.segmentByOffsetMilestones = YES; 
 
// seconds tracking - sends a hit every x seconds 
mediaSettings.trackSeconds = 30; // sends a hit every 30 seconds 
 
// open the video 
[ADBMobile mediaOpenWithSettings:mediaSettings callback:nil]; 
 
// You are now ready to play the video, for example, [movieViewController.moviePlayer play]; 
// Note the the mediaPlay, mediaStop and mediaClose methods are called in the 
// event handlers described in the next section
```

## Track Player Events {#section_C7F43AECBC0D425390F7FCDF3035B65D}

To measure video playback, The `mediaPlay`, `mediaStop`, and `mediaClose` methods need to be called at the appropriate times. For example, when the player is paused, `mediaStop`. `mediaPlay` is called when playback starts or is resumed.

The following example demonstrates configuring notifications and calling the media methods to measure video:

```
// configure notifications for when the video is finished, and when the 
media playback state changes 
 
- (void) configureNotifications:(MPMoviePlayerController *) movieController { 
 [[NSNotificationCenter defaultCenter] 
  addObserver: self 
  selector: @selector(mediaFinishedCallback:) 
  name: MPMoviePlayerPlaybackDidFinishNotification 
  object: movieController]; 
  
 [[NSNotificationCenter defaultCenter] 
  addObserver: self 
  selector: @selector(mediaPlaybackChangedCallback:) 
  name: MPMoviePlayerPlaybackStateDidChangeNotification 
  object: movieController]; 
} 
 
// define your notification callbacks. 
 
- (void) mediaFinishedCallback: (NSNotification*) notification { [ADBMobile mediaClose:MEDIA_NAME];} 
 
- (void) mediaPlaybackChangedCallback: (NSNotification*) notification { 
 MPMoviePlayerController *mediaController = notification.object; 
 if (mediaController.playbackState == MPMoviePlaybackStatePlaying) { 
  [ADBMobile mediaPlay:MEDIA_NAME offset: isnan(mediaController.currentPlaybackTime) ? 0.0 : mediaController.currentPlaybackTime]; 
 } 
 else if (mediaController.playbackState == MPMoviePlaybackStateSeekingBackward) { 
  [ADBMobile mediaStop:MEDIA_NAME offset:mediaController.currentPlaybackTime]; 
 } 
 else if (mediaController.playbackState == MPMoviePlaybackStateSeekingForward) { 
  [ADBMobile mediaStop:MEDIA_NAME offset:mediaController.currentPlaybackTime]; 
 } 
 else if (mediaController.playbackState == MPMoviePlaybackStatePaused) { 
  [ADBMobile mediaStop:MEDIA_NAME offset:mediaController.currentPlaybackTime]; 
 } 
 else if (mediaController.playbackState == MPMoviePlaybackStateInterrupted) { 
  [ADBMobile mediaStop:MEDIA_NAME offset:mediaController.currentPlaybackTime]; 
 } 
 else if (mediaController.playbackState == MPMoviePlaybackStateStopped) { 
  [ADBMobile mediaStop:MEDIA_NAME offset:mediaController.currentPlaybackTime]; 
 } 
}
```

## Classes {#section_16838332727348F990305C0C6B0D795C}

**Class: ADBMediaSettings**

```
bool segmentByMilestones; 
bool segmentByOffsetMilestones; 
double length; 
NSString *channel; 
NSString *name; 
NSString *playerName; 
NSString *playerID; 
NSString *milestones; 
NSString *offsetMilestones; 
NSUInteger trackSeconds; 
NSUInteger completeCloseOffsetThreshold; 
// settings used for ad tracking. For  
bool isMediaAd; 
double parentPodPosition; 
NSString *CPM; 
NSString *parentName; 
NSString *parentPod; 

```

** Class: ADBMediaState**

```
bool ad; 
bool clicked; 
bool complete; 
bool eventFirstTime; 
double length; 
double offset; 
double percent; 
double segmentLength; 
double timePlayed; 
double timePlayedSinceTrack; 
double timestamp; 
NSDate *openTime  
NSString *name 
NSString *playerName 
NSString *mediaEvent 
NSString *segment 
NSUInteger milestone 
NSUInteger offsetMilestone 
NSUInteger segmentNum 
NSUInteger eventType
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
   <td colname="col1"> mediaCreateSettings​WithName:​length:​playerName:​playerID: </td> 
   <td colname="col2"> <p> Returns an <span class="codeph"> ADBMediaSettings </span> object with specified parameters. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      +&nbsp;(ADBMediaSettings&nbsp;*)&nbsp;mediaCreateSettingsWithName:(NSString&nbsp;*)name&nbsp; 
     
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;length:(double)length&nbsp; 
     
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;playerName:(NSString&nbsp;*)playerName&nbsp; 
     
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;playerID:(NSString&nbsp;*)playerID; 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMediaSettings&nbsp;*myCatSettings&nbsp;=&nbsp;&nbsp; 
     
&nbsp;&nbsp;&nbsp;&nbsp;[ADBMobile&nbsp;mediaCreateSettingsWithName:@"catVideo"&nbsp; 
     
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;length:85&nbsp; 
     
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;playerName:@"catVideoPlayer"&nbsp; 
     
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;playerID:@"catPlayerId"]; 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> mediaAdCreateSettings​WithName:​length:​playerName:​parentName:​parentPod:​parentPodPosition:​CPM: </td> 
   <td colname="col2"> <p> Returns an <span class="codeph"> ADBMediaSettings </span> object for use with tracking an ad video. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      +&nbsp;(ADBMediaSettings&nbsp;*)&nbsp;mediaAdCreateSettingsWithName:(NSString&nbsp;*)name&nbsp; 
     
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;length:(double)length&nbsp; 
     
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;playerName:(NSString&nbsp;*)playerName&nbsp; 
     
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;parentName:(NSString&nbsp;*)parentName&nbsp; 
     
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;parentPod:(NSString&nbsp;*)parentPod&nbsp; 
     
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;parentPodPosition:(double)parentPodPosition&nbsp; 
     
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;CPM:(NSString&nbsp;*)CPM; 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMediaSettings&nbsp;*mySettings&nbsp;=&nbsp;&nbsp; 
     
&nbsp;&nbsp;&nbsp;&nbsp;[ADBMobile&nbsp;mediaAdCreateSettingsWithName:@"ad"&nbsp; 
     
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;length:30&nbsp; 
     
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;playerName:@"adPlayer"&nbsp; 
     
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;parentName:@"catVideo"&nbsp; 
     
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;parentPod:@"catCollection"&nbsp; 
     
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;parentPodPosition:2&nbsp; 
     
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;CPM:nil];&nbsp; 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> mediaOpenWithSettings:​callback: </td> 
   <td colname="col2"> <p> Opens an <span class="codeph"> ADBMediaSettings </span> object for tracking. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      +&nbsp;(void)&nbsp;mediaOpenWithSettings:(ADBMediaSettings&nbsp;*)settings 
     
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;callback:(void&nbsp;(^)(ADBMediaState&nbsp;*mediaState))callback; 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      [ADBMobile&nbsp;mediaOpenWithSettings:mySettings&nbsp;callback:^(ADBMediaState&nbsp;*mediaState)&nbsp;{ 
     
&nbsp;&nbsp;&nbsp;//&nbsp;do&nbsp;something&nbsp;with&nbsp;media&nbsp;state&nbsp;if&nbsp;you&nbsp;want 
     
}];

    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> mediaClose: </td> 
   <td colname="col2"> <p> Closes the media item named <i>name</i>. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      +&amp;nbsp;(void)&amp;nbsp;mediaClose:(NSString&amp;nbsp;*)name; 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      [ADBMobile&amp;nbsp;mediaClose:@"kittiesPlaying"]; 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> mediaPlay:​offset: </td> 
   <td colname="col2"> <p> Plays the media item named <i>name</i> at the given <i>offset</i> (in seconds). </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      +&amp;nbsp;(void)&amp;nbsp;mediaPlay:(NSString&amp;nbsp;*)name&amp;nbsp;offset:(double)offset; 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      [ADBMobile&amp;nbsp;mediaPlay:@"cats"&amp;nbsp;offset:25]; 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> mediaComplete:​offset: </td> 
   <td colname="col2"> <p> Manually mark the media item as complete at the <i>offset</i> provided (in seconds). </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      +&amp;nbsp;(void)&amp;nbsp;mediaComplete:(NSString&amp;nbsp;*)name&amp;nbsp;offset:(double)offset; 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      [ADBMobile&amp;nbsp;mediaComplete:@"meowzah"&amp;nbsp;offset:90]; 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> mediaStop:​offset: </td> 
   <td colname="col2"> <p> Notifies the media module that the video has been stopped or paused at the given <i>offset</i>. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      +&amp;nbsp;(void)&amp;nbsp;mediaStop:(NSString&amp;nbsp;*)name&amp;nbsp;offset:(double)offset; 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      [ADBMobile&amp;nbsp;mediaStop:@"toonses"&amp;nbsp;offset:30]; 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> mediaClick:​offset: </td> 
   <td colname="col2"> <p> Notifies the media module that the media item has been clicked. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      +&amp;nbsp;(void)&amp;nbsp;mediaClick:(NSString&amp;nbsp;*)name&amp;nbsp;offset:(double)offset; 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      [ADBMobile&amp;nbsp;mediaClick:@"soManyCats"&amp;nbsp;offset:47]; 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> mediaTrack:​withData: </td> 
   <td colname="col2"> <p>Sends a track action call (no page view) for the current media state. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      +&amp;nbsp;(void)&amp;nbsp;mediaTrack:(NSString&amp;nbsp;*)name&amp;nbsp;withData:(NSDictionary&amp;nbsp;*)data; 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c"></codeblock> </td> 
  </tr> 
 </tbody> 
</table>

