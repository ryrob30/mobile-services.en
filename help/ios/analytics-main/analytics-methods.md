---
description: Here is a list of Adobe Analytics methods that are provided by the iOS library.
seo-description: Here is a list of Adobe Analytics methods that are provided by the iOS library.
seo-title: Analytics Methods
solution: Marketing Cloud,Analytics
title: Analytics Methods
topic: Developer and implementation
uuid: d49fe6de-cb32-4b96-9891-c567310e59a6
index: y
internal: n
snippet: y
---

# Analytics Methods{#analytics-methods}

Here is a list of Adobe Analytics methods that are provided by the iOS library.

 The SDK currently has support for multiple [!DNL Adobe Experience Cloud Solutions], including [!DNL Analytics], [!DNL Target], [!DNL Audience Manager], and the [!DNL Experience Cloud ID service]. Methods are prefixed according to the solution. [!DNL Experience Cloud ID] methods are prefixed with `track`.

Each of these methods is used to send data into your [!DNL Adobe Analytics] report suite. 

<table id="table_164CA94BE9BD44E59F60389A6D148DF0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Method </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> trackState:​data: </td> 
   <td colname="col2"> <p>States are the views that are available in your app, such as <span class="codeph"> home dashboard </span>, <span class="codeph"> app settings </span>, <span class="codeph"> cart </span>, and so on. These states are similar to pages on a website, and <span class="codeph"> trackState </span> calls increment page views. </p> <p>If <span class="codeph"> state </span> is empty, it displays as <i>app name app version (build)</i> in reports. If you see this value in reports, ensure you are setting <span class="codeph"> state </span> in each <span class="codeph"> trackState </span> call. </p> <p>Tip:  This is the only tracking call that increments page views. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      +&nbsp;(void)&nbsp;trackState:(NSString&nbsp;*)state&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;data:(NSDictionary&nbsp;*)data; 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      [ADBMobile&nbsp;trackState:@"loginScreen"&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;data:nil]; 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trackAction:​data: </td> 
   <td colname="col2"> <p>Tracks an action in your app. </p> <p>Actions that you want to measure, such as <span class="codeph"> logons </span>, <span class="codeph"> banner taps </span>, <span class="codeph"> feed subscriptions </span>, and other metrics, occur in your app. </p> <p>Tip:  If you have code that might run while the app is in the background (for example, a background data retrieval), use <span class="codeph"> trackActionFromBackground </span> instead. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      +&nbsp;(void)&nbsp;trackAction:(NSString&nbsp;*)action&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;data:(NSDictionary&nbsp;*)data; 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      [ADBMobile&nbsp;trackAction:@"heroBannerTouched"&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;data:nil]; 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trackingIdentifier </td> 
   <td colname="col2"> <p>Retrieves the analytics tracking identifier. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      +&amp;nbsp;(NSString&amp;nbsp;*)&amp;nbsp;trackingIdentifier; 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      NSString&amp;nbsp;*trackingId&amp;nbsp;=&amp;nbsp;[ADBMobile&amp;nbsp;trackingIdentifier]; 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trackActionFromBackground:​data: </td> 
   <td colname="col2"> <p> Tracks an action that occurred in the background, which suppresses lifecycle events from firing in certain scenarios. </p> <p>Tip:  This method should only be called in code that runs while your app is in the background. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      +&nbsp;(void)&nbsp;trackActionFromBackground:(NSString&nbsp;*)action&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;data:(NSDictionary&nbsp;*)data; 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      [ADBMobile&nbsp;trackActionFromBackground:@"downloadedUpdate"&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;data:nil]; 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trackLocation:​data: </td> 
   <td colname="col2"> <p>Sends the current x y coordinates. </p> <p>Also uses points of interest that are defined in the <span class="codeph"> ADBMobileConfig.json </span> file to determine if the location provided as a parameter is in any of your POIs. If the current coordinates are in a defined POI, a context data variable is populated and sent with the <span class="codeph"> trackLocation </span> call. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      +&nbsp;(void)&nbsp;trackLocation:(CLLocation&nbsp;*)location&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;data:(NSDictionary&nbsp;*)data; 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      [ADBMobile&nbsp;trackLocation:userLocation&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;data:nil]; 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trackBeacon:​data: </td> 
   <td colname="col2"> <p>Tracks when a users enters proximity of a beacon. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      +&nbsp;(void)&nbsp;trackLocation:(CLBeacon&nbsp;*)beacon&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;data:(NSDictionary&nbsp;*)data; 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      [ADBMobile&nbsp;trackBeacon:beacon&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;data:nil]; 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trackingClearCurrentBeacon </td> 
   <td colname="col2"> <p>Clears beacons data after a user leaves the proximity of the beacon. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      +&amp;nbsp;(void)&amp;nbsp;trackingClearCurrentBeacon; 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      [ADBMobile&amp;nbsp;trackingClearCurrentBeacon]; 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trackLifetimeValueIncrease:​data: </td> 
   <td colname="col2"> <p> Adds <span class="codeph"> amount </span> to the user's lifetime value. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      +&nbsp;(void)&nbsp;trackLifetimeValueIncrease:(NSDecimalNumber&nbsp;*)amount&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;data:(NSDictionary&nbsp;*)data; 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      [ADBMobile&nbsp;trackLifetimeValueIncrease:30&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;data:nil]; 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trackTimedActionStart:​data: </td> 
   <td colname="col2"> <p>Start a timed action with name <span class="codeph"> action </span>. </p> <p> If you call this method for an action that has already started, the previous timed action is overwritten. </p> <p>Tip:  This call does not send a hit. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      +&nbsp;(void)&nbsp;trackTimedActionStart:(NSString&nbsp;*)action&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;data:(NSDictionary&nbsp;*)data; 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      [ADBMobile&nbsp;trackTimedActionStart:@"cartToCheckout"&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;data:nil]; 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trackTimedActionUpdate:​data: </td> 
   <td colname="col2"> <p> Pass in <span class="codeph"> data </span> to update the context data associated with the given <span class="codeph"> action </span>. </p> <p>The <span class="codeph"> data </span> that is passed in is appended to the existing data for the action, and if the same key is already defined for <span class="codeph"> action </span>, overwrites the data. </p> <p>Tip:  This call does not send a hit. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      +&nbsp;(void)&nbsp;trackTimedActionUpdate:(NSString&nbsp;*)action&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;data:(NSDictionary&nbsp;*)data; 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      [ADBMobile&nbsp;trackTimedActionUpdate:@"cartToCheckout"&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;data:@{@"quantity":@"3"}]; 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trackTimedActionEnd:​logic: </td> 
   <td colname="col2"> <p> End a timed action. </p> <p>If you provide <span class="codeph"> block </span>, you will have access to the final time values and be able to manipulate <span class="codeph"> data </span> prior to sending the final hit. </p> <p>Tip:  If you provide <span class="codeph"> block </span>, you must return <span class="codeph"> YES </span> to send a hit. Passing in <span class="codeph"> nil </span> for <span class="codeph"> block </span> sends the final hit. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      +&nbsp;(void)&nbsp;trackTimedActionEnd:(NSString&nbsp;*)action&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;logic:(BOOL&nbsp;(^)&nbsp;(NSTimeInterval&nbsp;inAppDuration,&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;NSTimeInterval&nbsp;totalDuration,&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;NSMutableDictionary&nbsp;*data))block; 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      [ADBMobile&nbsp;trackTimedActionEnd:@"cartToCheckout"&nbsp;&nbsp;&nbsp;&nbsp;logic:^(NSTimeInterval&nbsp;inApp,&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;NSTimeInterval&nbsp;total,&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;NSMutableDictionary&nbsp;*data)&nbsp;{&nbsp;&nbsp;&nbsp;&nbsp;data[@"price"]&nbsp;=&nbsp;@"49.95";&nbsp;&nbsp;&nbsp;&nbsp;return&nbsp;YES;&nbsp;&nbsp;&nbsp;}];
    </codeblock> </td>
  </tr>
  <tr> 
   <td colname="col1"> trackingTimedActionExists </td> 
   <td colname="col2"> <p>Returns whether a timed action is in progress. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      +&amp;nbsp;(BOOL)&amp;nbsp;trackingTimedActionExists:(NSString&amp;nbsp;*)action; 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      BOOL&amp;nbsp;*actionExists&amp;nbsp;=&amp;nbsp;[ADBMobile&amp;nbsp;trackingTimedActionExists]; 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trackingSendQueuedHits </td> 
   <td colname="col2"> <p> <i>Requires SDK 4.1</i> </p> <p>Regardless of how many hits are currently queued, forces the library to send all hits in the offline queue. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      +&amp;nbsp;(void)&amp;nbsp;trackingSendQueuedHits; 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      [ADBMobile&amp;nbsp;trackingSendQueuedHits]; 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trackingGetQueueSize </td> 
   <td colname="col2"> <p>Retrieves the number of hits currently in the offline queue. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      +&amp;nbsp;(NSUInteger)&amp;nbsp;trackingGetQueueSize; 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      NSUInteger&amp;nbsp;*queueSize&amp;nbsp;=&amp;nbsp;[ADBMobile&amp;nbsp;trackingGetQueueSize]; 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trackingClearQueue </td> 
   <td colname="col2"> <p>Clears all hits from the offline queue. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      +&amp;nbsp;(void)&amp;nbsp;trackingClearQueue; 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      [ADBMobile&amp;nbsp;trackingClearQueue]; 
    </codeblock> <p> <p>Warning:  Use caution when clearing the queue manually. This process cannot be reversed. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trackPushMessageClickThrough </td> 
   <td colname="col2"> <p>Tracks a push message click-through. </p> <p> <p>Important:  This method does not increment page views. </p> </p> <p><b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      +&amp;nbsp;(void)&amp;nbsp;trackPushMessageClickThrough:(NSDictionary&amp;nbsp;*)userInfo; 
    </codeblock> <p><b>Example:</b> </p> 
    <codeblock class="syntax c">
      -&nbsp;(void)application:(UIApplication&nbsp;*)application&nbsp;didReceiveRemoteNotification:(NSDictionary&nbsp;*)userInfo&nbsp;fetchCompletionHandler:(void&nbsp;(^)(UIBackgroundFetchResult))completionHandler&nbsp;{&nbsp;&nbsp;&nbsp;&nbsp;//&nbsp;only&nbsp;send&nbsp;the&nbsp;hit&nbsp;if&nbsp;the&nbsp;app&nbsp;is&nbsp;not&nbsp;active&nbsp;&nbsp;&nbsp;&nbsp;if&nbsp;(application.applicationState&nbsp;!=&nbsp;UIApplicationStateActive)&nbsp;{&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ADBMobile&nbsp;trackPushMessageClickThrough:userInfo];&nbsp;&nbsp;&nbsp;&nbsp;}&nbsp;&nbsp;&nbsp;&nbsp;completionHandler(UIBackgroundFetchResultNoData);}
    </codeblock> </td> 
  </tr> 
 </tbody> 
</table>
