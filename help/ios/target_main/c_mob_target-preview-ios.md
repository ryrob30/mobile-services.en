---
description: Target Preview allows you to easily perform end-to-end QA for Target activities and preview these activities on your device.
seo-description: Target Preview allows you to easily perform end-to-end QA for Target activities and preview these activities on your device.
seo-title: Target Preview on iOS
title: Target Preview on iOS
uuid: 9af9d81a-3d22-48b2-a322-7c56c3bdc16d
index: y
internal: n
snippet: y
translate: y
---

# Target Preview on iOS

Target Preview allows you to easily perform end-to-end QA for Target activities and preview these activities on your device.

<a id="section_A79B6EEB46AE4EC084B7ADEB6D8D3EDA"></a>

For more information on how to set up and use Target Preview, go to [Target Mobile Preview]( https://marketing.adobe.com/resources/help/en_US/target/target/target-mobile-preview.html).

<a id="section_0BD2239BA4F74F369D587FE4706E78B6"></a>

>[!NOTE]
>
>To use Target Preview, you need SDK version 4.14.0 or later.

<a id="section_055C6F90EA7548199187A0F26090A37F"></a>

** Target Preview Method** 

<table id="table_5238B149CD5B47028EF76DA8CCC10951"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Method </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <span class="codeph"> setPreviewRestartDeeplink </span> </td> 
   <td colname="col2"> <p>Sets an app deeplink that will be triggered when preview selections are applied in the Preview mode. </p> <p><b>Syntax</b> </p> <p> 
     <codeblock class="syntax objective c">
       +&nbsp;(void)&nbsp;targetPreviewRestartDeepLink:(nullable&nbsp;NSString&nbsp;*)callbackURL;

     </codeblock> </p> <p><b>Example</b> </p> <p> 
     <codeblock class="syntax objective c">
       [ADBMobile&amp;nbsp;targetPreviewRestartDeepLink:@"&amp;nbsp;myapp://myhost"]; 
     </codeblock> </p> </td> 
  </tr> 
 </tbody> 
</table>

