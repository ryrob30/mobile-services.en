---
description: The following Acquisition methods are provided by the iOS library 
seo-description: The following Acquisition methods are provided by the iOS library 
seo-title: Acquisition Methods
solution: Marketing Cloud,Analytics
title: Acquisition Methods
uuid: 6d7fc1c3-4c3f-4987-a4c8-8d7418c17792
index: y
internal: n
snippet: y
translate: y
---

# Acquisition Methods

The following methods are supported: 

<table id="table_AEFBC9C64319444AAD463E15A2400338"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Method </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>acquisitionCampaignStartForApp:data: </p> </td> 
   <td colname="col2"> <p>Allows developers to start an app acquisition campaign as if the user had clicked a link. This is helpful for creating manual acquisition links and handling the app store redirect yourself, such as with an <span class="codeph"> SKStoreView </span>. </p> <p> <b>Syntax:</b> </p> 
    <codeblock>
      +&amp;nbsp;(void)&amp;nbsp;acquisitionCampaignStartForApp:(NSString&amp;nbsp;*)appId&amp;nbsp;data:(NSDictionary&amp;nbsp;*)data; 
    </codeblock> <p> <b>Example: </b> </p> 
    <codeblock>
      &amp;nbsp;[ADBMobile&amp;nbsp;acquisitionCampaignStartForApp:@"0652024f-adcd-49f9-9bd7-2552a4564d2f"&amp;nbsp;data:@{@"custom.key":@"value"}]; 
    </codeblock> </td> 
  </tr> 
 </tbody> 
</table>

