---
description: List of Audience Manager methods provided by the Universal Windows Platform library.
seo-description: List of Audience Manager methods provided by the Universal Windows Platform library.
seo-title: Audience Manager methods
solution: Marketing Cloud,Analytics
title: Audience Manager methods
topic: Developer and implementation
uuid: efbe8f33-7f53-40a6-b7aa-a36ac718c047
---

# Audience Manager methods{#audience-manager-methods}

List of Audience Manager methods provided by the Universal Windows Platform library.

The SDK currently has support for multiple [!DNL Adobe Experience Cloud Solutions], including [!DNL Analytics], [!DNL Target], and [!DNL Audience Manager]. Methods are prefixed according to the solution. Audience Manager methods are prefixed with "AudienceManager."

>[!NOTE]
>
>When you consume winmd methods from winJS (JavaScript), all methods automatically have their first letter lowercased.

If audience manager is configured in your JSON file, a signal containing lifecycle metrics is sent in with your lifecycle hit. 

<table id="table_7AEDAD7F33A44B3AA387420D262F7235"> 
 <tbody> 
  <tr> 
   <td colname="col1"> GetVisitorProfile <p>winJS: getVisitorProfile </p> </td> 
   <td colname="col2"> <p>Returns the visitor profile that was most recently obtained. Returns <span class="codeph"> null </span> if no signal has been submitted yet. Visitor profile is saved in <span class="codeph"> SharedPreferences </span> for easy access across multiple launches of your app. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax csharp">
      static&amp;nbsp;Windows::Foundation::Collections::IMap&lt;Platform::String^,&amp;nbsp;Platform::Object^&gt;&amp;nbsp;^GetVisitorProfile(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax javascript">
      var&nbsp;ADB&nbsp;=&nbsp;ADBMobile; 
     
var&nbsp;profile&nbsp;=&nbsp;ADB.AudienceManager.getVisitorProfile(); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> GetDpid <p>winJS: getDpid </p> </td> 
   <td colname="col2"> <p>Returns the current DPID. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax csharp">
      static&amp;nbsp;Platform::String&amp;nbsp;^GetDpid(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax javascript">
      var&nbsp;ADB&nbsp;=&nbsp;ADBMobile; 
     
var&nbsp;dpid&nbsp;=&nbsp;ADB.AudienceManager.getDpid(); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> GetDpuuid <p>winJS: getDpuuid </p> </td> 
   <td colname="col2"> <p>Returns the current DPUUID. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax csharp">
      static&amp;nbsp;Platform::String&amp;nbsp;^GetDpuuid(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax javascript">
      var&nbsp;ADB&nbsp;=&nbsp;ADBMobile; 
     
var&nbsp;dpuuid&nbsp;=&nbsp;ADB.AudienceManager.getDpuuid(); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SetDpidAndDpuuid <p>winJS: setDpidAndDpuuid </p> </td> 
   <td colname="col2"> <p>Sets the DPID and DPUUID. If DPID and DPUUID are set, they will be sent with each signal. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax csharp">
      static&amp;nbsp;void&amp;nbsp;SetDpidAndDpuuid(Platform::String&amp;nbsp;^dpid,&amp;nbsp;Platform::String&amp;nbsp;^dpuuid); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax javascript">
      var&nbsp;ADB&nbsp;=&nbsp;ADBMobile; 
     
ADB.AudienceManager.setDpidAndDpuuid("newDpid",&nbsp;"newDpuuid"); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SignalWithData <p>winJS: signalWithData </p> </td> 
   <td colname="col2"> <p>Sends audience management a signal with traits and get the matching segments returned in a block callback. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax csharp">
      static&amp;nbsp;Windows::Foundation::IAsyncOperation&lt;Windows::Foundation::Collections::IMap&lt;Platform::String^,&amp;nbsp;Platform::Object^&gt;&amp;nbsp;^&gt;&amp;nbsp;^SignalWithData(Windows::Foundation::Collections::IMap&lt;Platform::String^,&amp;nbsp;Platform::Object^&gt;&amp;nbsp;^data); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax javascript">
      var&nbsp;ADB&nbsp;=&nbsp;ADBMobile; 
     
var&nbsp;traits&nbsp;=&nbsp;new&nbsp;Windows.Foundation.Collections.PropertySet(); 
     
traits["trait"]&nbsp;=&nbsp;"b"; 
     
ADB.AudienceManager.signalWithData(traits).then(function(visitorProfile)&nbsp;{ 
     
&nbsp;&nbsp;//&nbsp;segments&nbsp;come&nbsp;back&nbsp;here&nbsp;in&nbsp;"visitorProfile",&nbsp;normally&nbsp;found&nbsp;in&nbsp;the&nbsp;"segs"&nbsp;object&nbsp;of&nbsp;your&nbsp;json 
     
}); 
    </codeblock> </td> 
  </tr> 
 </tbody> 
</table>

