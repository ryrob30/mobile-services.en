---
description: The following Acquisition methods are provided by the Android library 
keywords: android;library;mobile;sdk
seo-description: The following Acquisition methods are provided by the Android library 
seo-title: Acquisition Methods
solution: Marketing Cloud,Analytics
title: Acquisition Methods
topic: Developer and implementation
uuid: 22ec432f-e7ae-4e89-be07-26206bbeacf8
index: y
internal: n
snippet: y
---

# Acquisition Methods{#acquisition-methods}

The following Acquisition methods are provided by the Android library:

<table id="table_889B0204C0D54B52901DE3BFEA6D11F3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Method </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>campaignStartForApp </p> </td> 
   <td colname="col2"> <p>Allows developers to start an app acquisition campaign as if the user clicked a link. This is helpful for creating manual acquisition links and handling the app store redirect yourself. </p> <p><b>Syntax</b> </p> 
    <codeblock class="syntax java">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;campaignStartForApp(final&amp;nbsp;String&amp;nbsp;appId,&amp;nbsp;final&amp;nbsp;Map&lt;String,&amp;nbsp;Object&gt;&amp;nbsp;data); 
    </codeblock> <p><b>Example</b> </p> 
    <codeblock class="syntax java">
      Acquisition.campaignStartForApp("0652024f-adcd-49f9-9bd7-2552a4564d2f",&nbsp;new&nbsp;HashMap&lt;String,&nbsp;Object&gt;()&nbsp;{{ 
     
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;put("custom.key",&nbsp;"value"); 
     
}}); 
    </codeblock> </td> 
  </tr> 
 </tbody> 
</table>

