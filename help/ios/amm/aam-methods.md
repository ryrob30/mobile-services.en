---
description: Here is a list of the Audience Manager methods that are provided by the iOS library.
seo-description: Here is a list of the Audience Manager methods that are provided by the iOS library.
seo-title: Audience Manager Methods
solution: Marketing Cloud,Analytics
title: Audience Manager Methods
topic: Developer and implementation
uuid: 97658bd6-4c4f-4875-abe9-36dad4ec8bae
index: y
internal: n
snippet: y
---

# Audience Manager Methods{#audience-manager-methods}

Here is a list of the Audience Manager methods that are provided by the iOS library.

 The SDK currently supports multiple [!DNL Adobe Experience Cloud Solutions], including [!DNL Analytics], [!DNL Target], [!DNL Audience Manager], and the [!DNL Experience Cloud ID service]. Methods are prefixed according to the solution, and [!DNL Audience Manager] methods are prefixed with " `audience`."

If [!DNL Audience Manager] is configured in your JSON file, a signal that contains lifecycle metrics is sent with `application:didFinishLaunchingWithOptions:`. 

<table id="table_7AEDAD7F33A44B3AA387420D262F7235"> 
 <tbody> 
  <tr> 
   <td colname="col1"> audienceVisitorProfile </td> 
   <td colname="col2"> <p>Returns the visitor profile that was most recently obtained and, if no signal has been submitted, returns <span class="codeph"> null </span>. The visitor profile is saved in <span class="codeph"> NSUserDefaults </span> for easy access across multiple launches of your app. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      +&amp;nbsp;(NSDictionary&amp;nbsp;*)&amp;nbsp;audienceVisitorProfile; 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      NSDictionary&amp;nbsp;*profile&amp;nbsp;=&amp;nbsp;[ADBMobile&amp;nbsp;audienceVisitorProfile]; 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> audienceDpid </td> 
   <td colname="col2"> <p>Returns the current DPID. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      +&amp;nbsp;(NSString&amp;nbsp;*)&amp;nbsp;audienceDpid; 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      NSString&amp;nbsp;*currentDpid&amp;nbsp;=&amp;nbsp;[ADBMobile&amp;nbsp;audienceDpid]; 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> audienceDpuuid </td> 
   <td colname="col2"> <p>Returns the current DPUUID. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      +&amp;nbsp;(NSString&amp;nbsp;*)&amp;nbsp;audienceDpuuid; 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      NSString&amp;nbsp;*currentDpuuid&amp;nbsp;=&amp;nbsp;[ADBMobile&amp;nbsp;audienceDpuuid]; 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> audienceSetDpid:​dpuuid: </td> 
   <td colname="col2"> <p>Sets the DPID and DPUUID. When set, both will be appended to each signal. </p> <p> 
     <ul id="ul_E14E9E7C733C4236866845E911CE5E40"> 
      <li id="li_30CBAFEB63604FEB8F894B956691403B">The <b>Data Provider ID (DPID)</b> is the data partner ID that is assigned by Audience Manager. </li> 
      <li id="li_83949D77027F433980F0C1F2BA93FA20">The <b>Data Provider Unique User ID (DPUUID)</b> is the data provider's unique ID for the user. </li> 
     </ul> </p> <p> <p>Important:  Before version 4.13.x, DPUUID was not automatically encoded. Starting in version 4.13.x, the SDK first un-encodes the value that was passed in and then re-encodes this value. This process ensures that the SDK does not break backwards compatibility. </p> </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      +&nbsp;(void)&nbsp;audienceSetDpid:(NSString&nbsp;*)dpid&nbsp; 
     
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;dpuuid:(NSString&nbsp;*)dpuuid; 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      [ADBMobile&nbsp;audienceSetDpid:@"290" 
     
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;dpuuid:@"99301393920493"]; 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> audienceReset </td> 
   <td colname="col2"> <p>Resets the Audience Manager UUID and purges the current visitor profile. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      +&amp;nbsp;(void)&amp;nbsp;audienceReset; 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      [ADBMobile&amp;nbsp;audienceReset]; 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> audienceSignalWithData::​callback: </td> 
   <td colname="col2"> <p>Sends audience management a signal with traits and gets the matching segments that are returned in a block callback. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      +&nbsp;(void)&nbsp;audienceSignalWithData:(NSDictionary&nbsp;*)data&nbsp; 
     
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;callback:(void&nbsp;(^)(NSDictionary&nbsp;*response))callback; 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      [ADBMobile&nbsp;audienceSignalWithData:traits&nbsp; 
     
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;callback:^(NSDictionary&nbsp;*response)&nbsp;{ 
     
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;//&nbsp;do&nbsp;something&nbsp;with&nbsp;returned&nbsp;segments 
     
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}]; 
    </codeblock> </td> 
  </tr> 
 </tbody> 
</table>

**Example:**

```
// setup your traits dictionary 
NSDictionary *traits = @{@"trait":@"b"}; 
// submit your signal and take action on results 
[ADBMobile audienceSignalWithData:traits  
                         callback:^(NSDictionary *response) { 
                             // do something with visitor segments here 
                             if ([response[@"gender"] isEqualToString:@"male"]) { 
                             // do something with gender  
                             } 
                         }];
```

