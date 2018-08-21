---
description: Here is a list of the Audience Manager methods that are provided by the Android library.
keywords: android;library;mobile;sdk
seo-description: Here is a list of the Audience Manager methods that are provided by the Android library.
seo-title: Audience Manager Methods
solution: Marketing Cloud,Analytics
title: Audience Manager Methods
topic: Developer and implementation
uuid: 607591ed-5859-49ea-88f1-186342356ac5
index: y
internal: n
snippet: y
translate: y
---

# Audience Manager Methods

The SDK currently supports multiple [!DNL  Adobe Experience Cloud Solutions], including [!DNL  Analytics], [!DNL  Target], [!DNL  Audience Manager], and the [!DNL  Experience Cloud ID Service]. Methods are prefixed according to the solution. For example, Experience Cloud ID methods are prefixed with ` audience manager`. 

If Audience Manager is configured in your JSON file, a signal that contains lifecycle metrics is sent with your lifecycle hit. 

<table id="table_7AEDAD7F33A44B3AA387420D262F7235"> 
 <tbody> 
  <tr> 
   <td colname="col1"> getVisitorProfile </td> 
   <td colname="col2"> <p>Returns the visitor profile that was most recently obtained and, if no signal has been submitted, returns <span class="codeph"> null </span>. The visitor profile is saved in <span class="codeph"> SharedPreferences </span> for easy access across multiple launches of your app. </p> <p> 
     <ul id="ul_D9B977E456804B36B49E07B29E4ECA4C"> 
      <li id="li_02F9B258EAB34C2698543D457C39A325"> <p><b>Syntax</b> 
        <codeblock class="syntax java">
          public&amp;nbsp;static&amp;nbsp;HashMap&amp;lt;String,&amp;nbsp;Object&amp;gt;&amp;nbsp;getVisitorProfile(); 
        </codeblock> </p> </li> 
      <li id="li_0D2D2CC732DD4DCEBFE5281821A43485"> <p><b>Example</b> 
        <codeblock class="syntax java">
          HashMap&amp;lt;String,&amp;nbsp;Object&amp;gt;&amp;nbsp;visitorProfile&amp;nbsp;=&amp;nbsp;AudienceManager.getVisitorProfile(); 
        </codeblock> </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> getDpid </td> 
   <td colname="col2"> <p>Returns the current DPID. </p> <p> 
     <ul id="ul_59121E5ECC6644DA89C7B430CD593960"> 
      <li id="li_6BBBFA5BA833439093109757D9A7FD18"> <p><b>Syntax</b> 
        <codeblock class="syntax java">
          public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;getDpid(); 
        </codeblock> </p> </li> 
      <li id="li_794E1B35BFEE4CD194A245C757C20DDC"> <p> <b>Example</b> 
        <codeblock class="syntax java">
          String&amp;nbsp;dpid&amp;nbsp;=&amp;nbsp;AudienceManager.getDpid(); 
        </codeblock> </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> getDpuuid </td> 
   <td colname="col2"> <p>Returns the current DPUUID. </p> <p> 
     <ul id="ul_F9240759D11447FFBEA4821CCBAD3B65"> 
      <li id="li_F9BCFC7729144E83B4F38E8AF56D1903"> <p><b>Syntax</b> 
        <codeblock class="syntax java">
          public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;getDpuuid(); 
        </codeblock> </p> </li> 
      <li id="li_C481236567E040BD971D97C3AE1FE85E"> <p> <b>Example</b> 
        <codeblock class="syntax java">
          String&amp;nbsp;dpuuid&amp;nbsp;=&amp;nbsp;AudienceManager.getDpuuid(); 
        </codeblock> </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> setDpidAndDpuuid </td> 
   <td colname="col2"> <p>Sets the DPID and DPUUID, and these values are sent with each signal. </p> <p> 
     <ul id="ul_75B98A06CD474AF2A9369BD2A7D7C815"> 
      <li id="li_1FE70CEDCBA64CA098AD74CBAA73F1C5"> <p><b>Syntax</b> 
        <codeblock class="syntax java">
          public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;setDpidAndDpuuid(String&amp;nbsp;dpid,&amp;nbsp;String&amp;nbsp;dpuuid); 
        </codeblock> </p> </li> 
      <li id="li_D8705B6ACAFA40A49719CE6F4C78200B"> <p> <b>Example</b> 
        <codeblock class="syntax java">
          AudienceManager.setDpidAndDpuuid("myDpid",&amp;nbsp;"myDpuuid"); 
        </codeblock> </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> signalWithData </td> 
   <td colname="col2"> <p>Sends audience management a signal with traits and gets the matching segments returned in a block callback. </p> <p> 
     <ul id="ul_7087C4602A64431C955F08C68E28B5B0"> 
      <li id="li_161399F0213746B6A36AF87BCD920DF2"> <p><b>Syntax:</b> 
        <codeblock class="syntax java">
          public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;signalWithData(Map&amp;lt;String,&amp;nbsp;Object&amp;gt;&amp;nbsp;data,&amp;nbsp;AudienceManagerCallback&amp;lt;Map&amp;lt;String,&amp;nbsp;Object&amp;gt;&amp;gt;&amp;nbsp;callback); 
        </codeblock> </p> </li> 
      <li id="li_2EE3EA64D7BF43C9BD5E6EE0A3C7912A"> <p> <b>Example:</b> 
        <codeblock class="syntax java">
          HashMap&nbsp;aamTraits&nbsp;=&nbsp;new&nbsp;HashMap&lt;String,&nbsp;Object&gt;(); 
         aamTraits.put("trait",&nbsp;"b"); 
         AudienceManager.signalWithData(aamTraits,&nbsp;new&nbsp;AudienceManager.AudienceManagerCallback&lt;Map&lt;String,&nbsp;Object&gt;&gt;()&nbsp;{ 
         &nbsp;@Override 
         &nbsp;public&nbsp;void&nbsp;call(Map&lt;String,&nbsp;Object&gt;&nbsp;item)&nbsp;{ 
         &nbsp;&nbsp;//&nbsp;segments&nbsp;come&nbsp;back&nbsp;here,&nbsp;normally&nbsp;found&nbsp;in&nbsp;the&nbsp;segs&nbsp;object&nbsp;of&nbsp;your&nbsp;json 
         &nbsp;} 
         }); 
        </codeblock> </p> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

