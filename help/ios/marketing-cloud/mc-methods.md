---
description: Here are the Experience Cloud ID service methods that are provided by the iOS library.
seo-description: Here are the Experience Cloud ID service methods that are provided by the iOS library.
seo-title: Experience Cloud ID Service Methods
solution: Marketing Cloud,Analytics
title: Experience Cloud ID Service Methods
topic: Developer and implementation
uuid: cdd307bc-8b7d-47a8-b77e-00902b9e2968
index: y
internal: n
snippet: y
---

# Experience Cloud ID Service Methods{#experience-cloud-id-service-methods}

Here are the Experience Cloud ID service methods that are provided by the iOS library.

The SDK currently supports multiple [!DNL Adobe Experience Cloud Solutions], including [!DNL Analytics], [!DNL Target], [!DNL Audience Manager], and the [!DNL Experience Cloud Visitor ID service].

Methods are prefixed according to the solution, and Experience Cloudr ID methods are prefixed with `visitor`. For more information, see [Enabling the Experience Cloud ID](../marketing-cloud/mcvid.md#section_79F984271C3B4366B7B04F864F4FF8C2). 

<table id="table_913992F10785483FAE4BF9FA7068B93D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Method </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> + (nullable NSURL *) visitorAppendToURL: (nullable NSURL *) url; </td> 
   <td colname="col2"> <p>Appends Adobe visitor data to a URL string for use with the Adobe JavaScript library. To use this method, you must have Mobile SDK 4.12+. For more information, see <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-appendvisitorid.html" format="html" scope="external"> Append Visitor ID Helper Function) </a>. </p> <p>Important:  This method can cause a blocking network call. Do not call this on time-sensitive threads. </p> <p> 
     <ul id="ul_F7970549BB464136AFABA977FFEA06F5"> 
      <li id="li_83423274208E490593A2E03A13BEB6D7"> <p><b>Input: </b> <span class="codeph"> URL&lt;NSURL&gt; </span> </p> <p> A required URL string that the visitor information will be appended to. </p> </li> 
      <li id="li_2E841AF38A4346FCB6B72EDEE4DD33AC"> <p> <b>Output:</b> <span class="codeph"> URL&lt;NSURL&gt; </span> </p> <p> String with the visitor info appended. </p> </li> 
     </ul> </p> <p><b>Example:</b> </p> 
    <codeblock class="syntax java">
      NSURL&nbsp;*url&nbsp;=&nbsp;[NSURL&nbsp;URLWithString:@"https://www.example.com"];&nbsp; 
     
NSURL&nbsp;*decoratedURL&nbsp;=&nbsp;[ADBMobile&nbsp;visitorAppendToURL:&nbsp;url];&nbsp; 
     
[[UIApplication&nbsp;sharedApplication]&nbsp;openURL:&nbsp;decoratedURL];&nbsp; 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> visitorMarketingCloudID </td> 
   <td colname="col2"> <p>Retrieves the Experience Cloud ID from the ID service. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      +&amp;nbsp;(NSString&amp;nbsp;*)&amp;nbsp;visitorMarketingCloudID; 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      NSString&amp;nbsp;*mcid&amp;nbsp;=&amp;nbsp;[ADBMobile&amp;nbsp;visitorMarketingCloudID]; 
    </codeblock> <p> <p>Important:  This method can cause a blocking network call and should <b>not</b> be called from a UI thread. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>visitorSyncIdentifiers: </p> </td> 
   <td colname="col2"> <p>With the Experience Cloud ID, you can set additional customer IDs that can be associated with each visitor. The Visitor API accepts multiple Customer IDs for the same visitor, with a customer type identifier to separate the scope of the different customer IDs. This method corresponds to <span class="codeph"> setCustomerIDs </span> in the JavaScript library. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      +&amp;nbsp;(void)&amp;nbsp;visitorSyncIdentifiers:(NSDictionary&amp;nbsp;*)identifiers; 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      [ADBMobile&amp;nbsp;visitorSyncIdentifiers:@{@"idType":@"idValue"}]; 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>visitorSyncIdentifiers:authenticationState: </p> </td> 
   <td colname="col2"> <p>Synchronizes the provided identifiers to the ID service. Pass in the <span class="codeph"> authState </span> as one of the following values: </p> 
    <ul id="ul_883756054E3143CCAB47397D2ED9E952"> 
     <li id="li_0F5598092E1D4382829BEBA4178001D2"> <span class="codeph"> ADBMobileVisitorAuthenticationStateUnknown </span> </li> 
     <li id="li_9848ACF9EC814B0FA8333E6F07E79FA9"> <span class="codeph"> ADBMobileVisitorAuthenticationStateAuthenticated </span> </li> 
     <li id="li_D257470950094883A28865FE5BF10C46"> <span class="codeph"> ADBMobileVisitorAuthenticationStateLoggedOut </span> </li> 
    </ul> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      +&amp;nbsp;(void)&amp;nbsp;visitorSyncIdentifiers:(nullable&amp;nbsp;NSDictionary&amp;nbsp;*)identifiers&amp;nbsp;authenticationState:(ADBMobileVisitorAuthenticationState)authState; 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      [ADBMobile&amp;nbsp;visitorSyncIdentifiers:@{@"myIdType":@"valueForUser"}&amp;nbsp;authenticationState:ADBMobileVisitorAuthenticationStateAuthenticated]; 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>visitorSyncIdentifierWithType:identifier:authenticationState: </p> </td> 
   <td colname="col2"> <p>Synchronizes the provided identifier type and value to the ID service. Pass in the <span class="codeph"> authState </span> as one of the following values: </p> 
    <ul id="ul_6E660CF959E643718CF32BF9397E840E"> 
     <li id="li_5B2138C3D64F4832BF64BF7CB2F3AB06"> <span class="codeph"> ADBMobileVisitorAuthenticationStateUnknown </span> </li> 
     <li id="li_90F611DDDFDB427E8AAA9F6FCAB93999"> <span class="codeph"> ADBMobileVisitorAuthenticationStateAuthenticated </span> </li> 
     <li id="li_3E394F1F26FB40F9B38DA7DAFB916368"> <span class="codeph"> ADBMobileVisitorAuthenticationStateLoggedOut </span> </li> 
    </ul> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      +&amp;nbsp;(void)&amp;nbsp;visitorSyncIdentifierWithType:(nullable&amp;nbsp;NSString&amp;nbsp;*)identifierType&amp;nbsp;identifier:(nullable&amp;nbsp;NSString&amp;nbsp;*)identifier&amp;nbsp;authenticationState:(ADBMobileVisitorAuthenticationState)authState; 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      [ADBMobile&amp;nbsp;visitorSyncIdentifierWithType:@"myIdType"&amp;nbsp;identifier:@"valueForUser"&amp;nbsp;authenticationState:ADBMobileVisitorAuthenticationStateLoggedOut]; 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>visitorGetIDs </p> </td> 
   <td colname="col2"> <p>Retrieves an array of read-only <span class="codeph"> ADBVisitorID </span> objects. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      +&amp;nbsp;(nullable&amp;nbsp;NSArray&amp;nbsp;*)&amp;nbsp;visitorGetIDs; 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      NSArray&amp;nbsp;*myVisitorIDs&amp;nbsp;=&amp;nbsp;[ADBMobile&amp;nbsp;visitorGetIDs]; 
    </codeblock> </td> 
  </tr> 
 </tbody> 
</table>

## ADBVisitorID interface {#section_2FF74454D25C4ADABAC5E43CBFAAEC26}

**Public Methods:**

```
- (nullable NSString *) idType; 
- (nullable NSString *) identifier; 
- (ADBMobileVisitorAuthenticationState) authenticationState; 

```

## ADBMobileVisitorAuthenticationState enum {#section_A55A3F336DDF4F838900632087F51430}

```
ADBMobileVisitorAuthenticationStateUnknown, 
ADBMobileVisitorAuthenticationStateAuthenticated, 
ADBMobileVisitorAuthenticationStateLoggedOut
```

