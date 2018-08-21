---
description: Here are the Experience Cloud ID methods that are provided by the Android library.
keywords: android;library;mobile;sdk
seo-description: Here are the Experience Cloud ID methods that are provided by the Android library.
seo-title: Experience Cloud ID Service Methods
solution: Marketing Cloud,Analytics
title: Experience Cloud ID Service Methods
topic: Developer and implementation
uuid: 07b73898-888d-4d4e-b2e0-9b647c88225c
index: y
internal: n
snippet: y
translate: y
---

# Experience Cloud ID Service Methods

The SDK currently supports multiple [!DNL  Adobe Experience Cloud Solutions], including [!DNL  Analytics], [!DNL  Target], [!DNL  Audience Manager], and the [!DNL  Experience Cloud ID Service]. 

Methods are prefixed according to the solution. For example, Experience Cloud ID methods are prefixed with ` visitor`. For more information, see [ Experience Cloud ID Configuration ](../c_marketing_cloud/mcvid.md#concept_B623676073854D3DAE724082E22ED91A). 



<table id="table_60F88A4468C3426CA3F3A51AD9163543"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Method </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> public static String appendToURL(final String URL) </td> 
   <td colname="col2"> <p>Appends Adobe visitor data to a URL string for use with the Adobe JavaScript library. You must have Mobile SDK 4.12+ to use this method. For more information, see <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-appendvisitorid.html" format="html" scope="external"> Append Visitor ID Helper Function </a>. </p> <p type="important">Note:  This method can cause a blocking network call. Do not call this on time-sensitive threads. </p> <p> 
     <ul id="ul_36072D6BC19C44D98AE3CA9E67D18B3F"> 
      <li id="li_58EF302412C14C9AB4FCE48E0A02B033"> <p><b>Input: </b> <span class="codeph"> URL&amp;lt;java.lang.String&amp;gt; </span> </p> <p> A required URL string to which the visitor information is appended. </p> </li> 
      <li id="li_9EDB3CB103B7410CB754F920211154D4"> <p> <b>Output:</b> <span class="codeph"> URL&amp;lt;java.lang.String&amp;gt; </span> </p> <p> String with the visitor information appended. </p> </li> 
     </ul> </p> <p><b>Example:</b> </p> 
    <codeblock class="syntax java">
      String&nbsp;urlSample&nbsp;=&nbsp;"http://example.com";&nbsp; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;String&nbsp;urlWithAdobeVisitorInfo&nbsp;=&nbsp;Visitor.appendToURL(urlSample);&nbsp; 
      
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Intent&nbsp;i&nbsp;=&nbsp;new&nbsp;Intent(Intent.ACTION_VIEW);&nbsp; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;i.setData(Uri.parse(urlWithAdobeVisitorInfo));&nbsp; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;startActivity(i);&nbsp; 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> getMarketingCloudId </td> 
   <td colname="col2"> <p>Retrieves the Experience Cloud ID from the visitor ID service. </p> <p> 
     <ul id="ul_4780AE39F60248E58D9B4D72589BCE8C"> 
      <li id="li_817B5517979B40E891D01D230AD99D85"> <p><b>Syntax:</b> 
        <codeblock class="syntax c">
          public&amp;nbsp;static&amp;nbsp;String&amp;nbsp;getMarketingCloudId(); 
        </codeblock> </p> </li> 
      <li id="li_9B59481BF6E541E3918CACBA92D026F4"> <p> <b>Example:</b> 
        <codeblock class="syntax c">
          String&amp;nbsp;mcid&amp;nbsp;=&amp;nbsp;Visitor.getMarketingCloudId(); 
        </codeblock> </p> </li> 
     </ul> </p> <p> <p type="important">Note:  This method can cause a blocking network call and should <b>not</b> be called from a UI thread. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>syncIdentifiers </p> </td> 
   <td colname="col2"> <p>With the Experience Cloud ID, you can set additional customer IDs that can be associated with each visitor. The Visitor API accepts multiple customer IDs for the same visitor, with a customer type identifier to separate the scope of the different customer IDs. This method corresponds to <span class="codeph"> setCustomerIDs </span> in the JavaScript library. </p> <p> 
     <ul id="ul_3C0B6EA5B4D8402BB4866EA7D42FFA62"> 
      <li id="li_02C27EB8D2FE442AB3A4D7DA32847CB9"> <p><b>Syntax:</b> 
        <codeblock class="syntax c">
          public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;syncIdentifiers(Map&amp;lt;String,&amp;nbsp;String&amp;gt;&amp;nbsp;identifiers); 
        </codeblock> </p> </li> 
      <li id="li_94424FD06F584B02877F4B81FDEC715F"> <p> <b>Example:</b> 
        <codeblock class="syntax c">
          Map&lt;String,&nbsp;String&gt;&nbsp;identifiers&nbsp;=&nbsp;new&nbsp;HashMap&lt;String,&nbsp;String&gt;(); 
         identifiers.put("idType",&nbsp;"idValue"); 
         Visitor.syncIdentifiers(identifiers); 
        </codeblock> </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>syncIdentifer </p> </td> 
   <td colname="col2"> <p>Synchronizes the provided identifier type and value to the Visitor ID service. Pass in the <span class="codeph"> authenticationState </span> as one of the following values: </p> <p> 
     <ul id="ul_879E676003F34EDE9D7ABC6844B6373E"> 
      <li id="li_E6DBEE85828049A8BB7FEEDBA9343E8F"> <span class="codeph"> VisitorID.VisitorIDAuthenticationState.VISITOR_ID_AUTHENTICATION_STATE_UNKNOWN </span> </li> 
      <li id="li_EAD578000219442C8ED7CC51CF70434E"> <span class="codeph"> VisitorID.VisitorIDAuthenticationState.VISITOR_ID_AUTHENTICATION_STATE_AUTHENTICATED </span> </li> 
      <li id="li_7830D6EA6DCB48C6A13BD9E76BB0698B"> <span class="codeph"> VisitorID.VisitorIDAuthenticationState.VISITOR_ID_AUTHENTICATION_STATE_LOGGED_OUT </span> </li> 
     </ul> </p> <p> 
     <ul id="ul_CB02C85E7DC9486FB0ADBCEFD04E6ABB"> 
      <li id="li_60D35403594147C69C324FF4618294A4"> <p><b>Syntax:</b> 
        <codeblock class="syntax c">
          public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;syncIdentifier(final&amp;nbsp;String&amp;nbsp;identifierType,&amp;nbsp;final&amp;nbsp;String&amp;nbsp;identifier,&amp;nbsp;final&amp;nbsp;VisitorID.VisitorIDAuthenticationState&amp;nbsp;authenticationState); 
        </codeblock> </p> </li> 
      <li id="li_64859AAEBFC640AA9AD95CA7E320574E"> <p> <b>Example:</b> 
        <codeblock class="syntax c">
          Visitor.syncIdentifier("myIdType",&amp;nbsp;"valueForUser",&amp;nbsp;VisitorID.VisitorIDAuthenticationState.VISITOR_ID_AUTHENTICATION_STATE_LOGGED_OUT); 
        </codeblock> </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>syncIdentifiers </p> </td> 
   <td colname="col2"> <p>Synchronizes the provided identifiers to the ID service. Pass in the <span class="codeph"> authenticationState </span> as one of the following values: </p> <p> 
     <ul id="ul_5A3288AC328F4785A0605C5102CCCA21"> 
      <li id="li_8FF8371EC1844ED899FBA38E048F13FF"> <span class="codeph"> VisitorID.VisitorIDAuthenticationState.VISITOR_ID_AUTHENTICATION_STATE_UNKNOWN </span> </li> 
      <li id="li_F3A56B0168724E989B080343FCC4DF36"> <span class="codeph"> VisitorID.VisitorIDAuthenticationState.VISITOR_ID_AUTHENTICATION_STATE_AUTHENTICATED </span> </li> 
      <li id="li_275FB84A9AEA4A6D8C44B4C2C4A4E445"> <span class="codeph"> VisitorID.VisitorIDAuthenticationState.VISITOR_ID_AUTHENTICATION_STATE_LOGGED_OUT </span> </li> 
     </ul> </p> <p> 
     <ul id="ul_2B53483E78CB4E1AB4E5E6187722EDD7"> 
      <li id="li_CD4F603282E645389F5203CC9765B38C"> <p><b>Syntax:</b> 
        <codeblock class="syntax c">
          public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;syncIdentifiers(final&amp;nbsp;Map&amp;lt;String,&amp;nbsp;String&amp;gt;&amp;nbsp;identifiers,&amp;nbsp;final&amp;nbsp;VisitorID.VisitorIDAuthenticationState&amp;nbsp;authenticationState); 
        </codeblock> </p> </li> 
      <li id="li_AAA31F380DEF4A4DB444D53486B55FCE"> <p><b>Example:</b> 
        <codeblock class="syntax c">
          Map&lt;String,&nbsp;String&gt;&nbsp;identifiers&nbsp;=&nbsp;new&nbsp;HashMap&lt;String,&nbsp;String&gt;(); 
         &nbsp;identifiers.put("myIdType",&nbsp;"valueForUser"); 
         &nbsp;Visitor.syncIdentifiers(identifiers,&nbsp;VisitorID.VisitorIDAuthenticationState.VISITOR_ID_AUTHENTICATION_STATE_AUTHENTICATED); 
        </codeblock> </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>getIdentifiers </p> </td> 
   <td colname="col2"> <p>Retrieves a list of read-only <span class="codeph"> ADBVisitorID </span> objects. </p> <p> 
     <ul id="ul_820880295D3B47D68B829575AD9B81FE"> 
      <li id="li_964355E5F91C4976826F6A0BAAEEB9BC"> <p><b>Syntax:</b> 
        <codeblock class="syntax c">
          public&amp;nbsp;static&amp;nbsp;List&amp;lt;VisitorID&amp;gt;&amp;nbsp;getIdentifiers(); 
        </codeblock> </p> </li> 
      <li id="li_7D81B2F7B0F84091B39DD45FA4B542E9"> <p> <b>Example:</b> 
        <codeblock class="syntax c">
          List&amp;lt;VisitorID&amp;gt;&amp;nbsp;myVisitorIDs&amp;nbsp;=&amp;nbsp;Visitor.getIdentifiers(); 
        </codeblock> </p> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>


## Public Methods {#section_8AC744B431A3438C9B45629CA3EA0F51}


```
public class VisitorID { 
 public final String idOrigin; 
 public final String idType; 
 public final String id; 
 public VisitorIDAuthenticationState authenticationState; 
 
 public enum VisitorIDAuthenticationState { 
  VISITOR_ID_AUTHENTICATION_STATE_UNKNOWN(0), 
     VISITOR_ID_AUTHENTICATION_STATE_AUTHENTICATED(1), 
     VISITOR_ID_AUTHENTICATION_STATE_LOGGED_OUT(2); 
 } 
}
```
