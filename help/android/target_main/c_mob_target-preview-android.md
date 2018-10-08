---
description: Target Preview allows you to easily perform end-to-end QA for Target activities and preview these activities on your device.
seo-description: Target Preview allows you to easily perform end-to-end QA for Target activities and preview these activities on your device.
seo-title: Target Preview on Android
title: Target Preview on Android
uuid: 5b296429-e696-47fa-a877-ee05effbcd5a
index: y
internal: n
snippet: y
translate: y
---

# Target Preview on Android

Target Preview allows you to easily perform end-to-end QA for Target activities and preview these activities on your device.

<a id="section_481A75DFFC584DD7AA294941298BABCB"></a>

For more information on how to set up and use Target Preview, go to [Target Mobile Preview]( https://marketing.adobe.com/resources/help/en_US/target/target/target-mobile-preview.html).

<a id="section_6DC3DFF0D575468AB1403C2242111873"></a>

>[!IMPORTANT]
>
>To use Target Preview, you need SDK version 4.14.0 or later.

<a id="section_164F54A1D2DE4167B6A7D85B2E983637"></a>

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
     <codeblock class="syntax java">
       public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;setPreviewRestartDeeplink(String&amp;nbsp;deeplink); 
     </codeblock> </p> <p><b>Example</b> </p> <p> 
     <codeblock class="syntax java">
       Target.setPreviewRestartDeeplink(“myapp://myhost”); 
     </codeblock> </p> </td> 
  </tr> 
 </tbody> 
</table>

