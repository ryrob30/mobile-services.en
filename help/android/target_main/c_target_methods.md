---
description: Here is the list of Adobe Target methods that are provided by the Android library.
keywords: android;library;mobile;sdk
seo-description: Here is the list of Adobe Target methods that are provided by the Android library.
seo-title: Target Methods
solution: Marketing Cloud,Analytics
title: Target Methods
topic: Developer and implementation
uuid: 0d35a271-8c56-4ee3-9c03-51ac0b6edb05
index: y
internal: n
snippet: y
translate: y
---

# Target Methods

The SDK currently supports multiple [!DNL  Adobe Experience Cloud Solutions], including [!DNL  Analytics], [!DNL  Target], [!DNL  Audience Manager], and the [!DNL  Experience Cloud ID Service]. Methods are prefixed according to the solution. For example, Experience Cloud ID methods are prefixed with ` target`. 


>[!TIP]
>
>[ Lifecycle Metrics ](../metrics.md#concept_77CA5CEB51D1418FB98EC7C044682A05) are sent as parameters to each mbox load. 



## Class Reference : TargetLocationRequest {#section_A8CC898922164E819EC730DC92A6742B}

**Properties:** 

```
javapublic String name; 
public String defaultContent; 
public HashMap<String, Object> parameters;
```
**String Constants** 


>[!TIP]
>
>The following constants are for ease of use when you set keys for custom parameters.



```
javapublic static final String TARGET_PARAMETER_ORDER_ID   = "orderId"; 
public static final String TARGET_PARAMETER_ORDER_TOTAL         = "orderTotal"; 
public static final String TARGET_PARAMETER_PRODUCT_PURCHASE_ID = "productPurchasedId"; 
public static final String TARGET_PARAMETER_CATEGORY_ID         = "categoryId"; 
public static final String TARGET_PARAMETER_MBOX_3RDPARTY_ID    = "mbox3rdPartyId"; 
public static final String TARGET_PARAMETER_MBOX_PAGE_VALUE     = "mboxPageValue"; 
public static final String TARGET_PARAMETER_MBOX_PC             = "mboxPC"; // pcId in cookie 
public static final String TARGET_PARAMETER_MBOX_SESSION_ID     = "mboxSession"; // sessionId in cookie 
public static final String TARGET_PARAMETER_MBOX_HOST           = "mboxHost";
```

<a id="section_E7D486365BA7404DA4A1756A582DA3B2"></a>


>[!IMPORTANT]
>
>
>* If you are using SDKs **before** version 4.14.0, see [ http://developers.adobetarget.com/api/#input-parameters ](http://developers.adobetarget.com/api/#input-parameters) for parameters limitations.
>* If you are using SDKs version 4.14.0 **or after**, see [ http://developers.adobetarget.com/api/#batch-input-parameters ](http://developers.adobetarget.com/api/#batch-input-parameters) for parameters limitations.







<table id="table_AD066582C8E2478A8DC0A59B78ACB443"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Method </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> <p>loadRequest </p> </td> 
   <td colname="col2"> <p>Sends <span class="codeph"> request </span> to your configured Target server and returns the string value of the offer that is generated in a block <span class="codeph"> callback </span>. </p> <p> <b>Syntax:</b> </p> <p> 
     <codeblock class="syntax java">
       public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;loadRequest(TargetLocationRequest&amp;nbsp;request,&amp;nbsp;TargetCallback&amp;lt;String&amp;gt;&amp;nbsp;callback); 
     </codeblock> </p> <p> <b>Example:</b> </p> <p> 
     <codeblock class="syntax java">
       Target.loadRequest(heroBannerRequest,&nbsp;new&nbsp;Target.TargetCallback&lt;String&gt;()&nbsp;{ 
      &nbsp;@Override 
      &nbsp;public&nbsp;void&nbsp;call(String&nbsp;item)&nbsp;{ 
      &nbsp;&nbsp;//&nbsp;do&nbsp;something&nbsp;with&nbsp;item 
      &nbsp;} 
      }); 
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p> <b>Syntax:</b> </p> <p> 
     <codeblock class="syntax java">
       public&nbsp;static&nbsp;void&nbsp;loadRequest(final&nbsp;String&nbsp;name,&nbsp;final&nbsp;String&nbsp;defaultContent,&nbsp;final&nbsp;Map&lt;String,&nbsp;Object&gt;&nbsp;profileParameters,&nbsp;final&nbsp;Map&lt;String,&nbsp;Object&gt;&nbsp;orderParameters, 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;final&nbsp;Map&lt;String,&nbsp;Object&gt;&nbsp;mboxParameters,&nbsp;final&nbsp;TargetCallback&lt;String&gt;&nbsp;callback) 
       
     </codeblock> </p> <p> <b>Example:</b> </p> <p> 
     <codeblock class="syntax java">
       Map&lt;String,&nbsp;Object&gt;&nbsp;profileParameters&nbsp;=&nbsp;new&nbsp;HashMap&lt;String,&nbsp;Object&gt;(); 
      profileParameters.put(“profile-parameter-key”,&nbsp;“profile-parameter-value”); 
       
      Map&lt;String,&nbsp;Object&gt;&nbsp;orderParameters&nbsp;=&nbsp;new&nbsp;HashMap&lt;String,&nbsp;Object&gt;(); 
      orderParameters.put(“order-parameter-key”,&nbsp;“order-parameter-value”); 
       
      Map&lt;String,&nbsp;Object&gt;&nbsp;mboxParameters&nbsp;=&nbsp;new&nbsp;HashMap&lt;String,&nbsp;Object&gt;(); 
      mboxParameters.put(“mbox-parameter-key”,&nbsp;“mbox-parameter-value”); 
      Target.loadRequest(“mboxName”,&nbsp;“defaultContent”,&nbsp;profileParameters,&nbsp;orderParameters,&nbsp;mboxParameters,&nbsp; 
      new&nbsp;TargetCallback&lt;String&gt;()&nbsp;{ 
      &nbsp;&nbsp;&nbsp;&nbsp;@Override 
      &nbsp;&nbsp;&nbsp;&nbsp;public&nbsp;void&nbsp;call&nbsp;(String&nbsp;item)&nbsp;{ 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Log.d(“Target&nbsp;Content”,&nbsp;item);&nbsp; 
      &nbsp;&nbsp;&nbsp;&nbsp;} 
      }); 
       
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>loadRequest </p> </td> 
   <td colname="col2"> <p> Sends <span class="codeph"> request </span> to your configured Target server and returns the string value of the offer that is generated in a block <span class="codeph"> callback </span>. </p> <p> <b>Syntax:</b> </p> <p> 
     <codeblock class="syntax java">
       public&nbsp;static&nbsp;void&nbsp;loadRequest(final&nbsp;String&nbsp;name,&nbsp;final&nbsp;String&nbsp;defaultContent,&nbsp;final&nbsp;Map&lt;String,&nbsp;Object&gt;&nbsp;profileParameters,&nbsp;final&nbsp;Map&lt;String,&nbsp;Object&gt;&nbsp;orderParameters, 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;final&nbsp;Map&lt;String,&nbsp;Object&gt;&nbsp;mboxParameters,&nbsp;final&nbsp;TargetCallback&lt;String&gt;&nbsp;callback) 
       
     </codeblock> </p> <p> <b>Example:</b> </p> <p> 
     <codeblock class="syntax java">
       Map&lt;String,&nbsp;Object&gt;&nbsp;profileParameters&nbsp;=&nbsp;new&nbsp;HashMap&lt;String,&nbsp;Object&gt;(); 
      profileParameters.put(“profile-parameter-key”,&nbsp;“profile-parameter-value”); 
       
      Map&lt;String,&nbsp;Object&gt;&nbsp;orderParameters&nbsp;=&nbsp;new&nbsp;HashMap&lt;String,&nbsp;Object&gt;(); 
      orderParameters.put(“order-parameter-key”,&nbsp;“order-parameter-value”); 
       
      Map&lt;String,&nbsp;Object&gt;&nbsp;mboxParameters&nbsp;=&nbsp;new&nbsp;HashMap&lt;String,&nbsp;Object&gt;(); 
      mboxParameters.put(“mbox-parameter-key”,&nbsp;“mbox-parameter-value”); 
      Target.loadRequest(“mboxName”,&nbsp;“defaultContent”,&nbsp;profileParameters,&nbsp;orderParameters,&nbsp;mboxParameters,&nbsp; 
      new&nbsp;TargetCallback&lt;String&gt;()&nbsp;{ 
      &nbsp;&nbsp;&nbsp;&nbsp;@Override 
      &nbsp;&nbsp;&nbsp;&nbsp;public&nbsp;void&nbsp;call&nbsp;(String&nbsp;item)&nbsp;{ 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Log.d(“Target&nbsp;Content”,&nbsp;item);&nbsp; 
      &nbsp;&nbsp;&nbsp;&nbsp;} 
      }); 
       
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>loadRequest </p> </td> 
   <td colname="col2"> <p>Sends a request to your configured <span class="keyword"> Target </span> server and returns the string value of the offer that is generated in a <span class="codeph"> TargetCallback </span>. </p> <p><b>Syntax:</b> </p> <p> 
     <codeblock class="syntax java">
       public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;loadRequest(final&amp;nbsp;String&amp;nbsp;name,&amp;nbsp;final&amp;nbsp;String&amp;nbsp;defaultContent,&amp;nbsp;final&amp;nbsp;Map&amp;lt;String,&amp;nbsp;Object&amp;gt;&amp;nbsp;profileParameters,&amp;nbsp;final&amp;nbsp;Map&amp;lt;String,&amp;nbsp;Object&amp;gt;&amp;nbsp;orderParameters,&amp;nbsp;final&amp;nbsp;Map&amp;lt;String,&amp;nbsp;Object&amp;gt;&amp;nbsp;mboxParameters,&amp;nbsp;final&amp;nbsp;Map&amp;lt;String,&amp;nbsp;Object&amp;gt;&amp;nbsp;requestLocationParameters,&amp;nbsp;final&amp;nbsp;TargetCallback&amp;lt;String&amp;gt;&amp;nbsp;callback); 
     </codeblock> </p> <p><b>Returns: </b>N/A </p> <p><b>Parameters:</b> </p> <p> 
     <table id="table_0CE7D4DE40464439A7D689E37D6B9D27">  
     </table> </p> <p><b>Example:</b> </p> 
    <codeblock class="syntax java">
      Map&lt;String,&nbsp;Object&gt;&nbsp;profileParameters&nbsp;=&nbsp;new&nbsp;HashMap&lt;String,&nbsp;Object&gt;(); 
     profileParameters.put(“profile-parameter-key”,&nbsp;“profile-parameter-value”); 
      
     Map&lt;String,&nbsp;Object&gt;&nbsp;orderParameters&nbsp;=&nbsp;new&nbsp;HashMap&lt;String,&nbsp;Object&gt;(); 
     orderParameters.put(“order-parameter-key”,&nbsp;“order-parameter-value”); 
      
     Map&lt;String,&nbsp;Object&gt;&nbsp;mboxParameters&nbsp;=&nbsp;new&nbsp;HashMap&lt;String,&nbsp;Object&gt;(); 
     mboxParameters.put(“mbox-parameter-key”,&nbsp;“mbox-parameter-value”); 
      
     Map&lt;String,&nbsp;Object&gt;&nbsp;requestLocationParameters&nbsp;=&nbsp;new&nbsp;HashMap&lt;String,&nbsp;Object&gt;(); 
     requestLocationParameters.put(“request-location-parameter-key”,&nbsp;“request-location-parameter-value”); 
      
     Target.loadRequest(“mboxName”,&nbsp;“defaultContent”,&nbsp;profileParameters,&nbsp;orderParameters,&nbsp;mboxParameters,&nbsp;requestLocationParameters,new&nbsp;TargetCallback&lt;String&gt;()&nbsp;{ 
     &nbsp;&nbsp;&nbsp;&nbsp;@Override 
     &nbsp;&nbsp;&nbsp;&nbsp;public&nbsp;void&nbsp;call&nbsp;(String&nbsp;item)&nbsp;{&nbsp; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Log.d(“Target&nbsp;Content”,&nbsp;item);&nbsp; 
     &nbsp;&nbsp;&nbsp;&nbsp;} 
     }); 
    </codeblock> <p>For more information about the underlying Target API, see <a href="https://docs.adobe.com/dev/products/target/reference/delivery.html" format="html" scope="external"> Delivery </a> in the Target Developer's help. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>createOrder​ConfirmRequest </p> </td> 
   <td colname="col2"> <p>Creates a <span class="codeph"> TargetLocationRequest </span> object with the given parameters. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax java">
      public&amp;nbsp;static&amp;nbsp;TargetLocationRequest&amp;nbsp;createOrderConfirmRequest(String&amp;nbsp;name,&amp;nbsp;String&amp;nbsp;orderId,&amp;nbsp;String&amp;nbsp;orderTotal,&amp;nbsp;String&amp;nbsp;productPurchasedId,&amp;nbsp;Map&amp;lt;String,&amp;nbsp;Object&amp;gt;&amp;nbsp;parameters); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax java">
      TargetLocationRequest&amp;nbsp;orderConfirm&amp;nbsp;=&amp;nbsp;Target.createOrderConfirmRequest("orderConfirm",&amp;nbsp;"order",&amp;nbsp;"47.88",&amp;nbsp;"3722",&amp;nbsp;null); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>createRequest </p> </td> 
   <td colname="col2"> <p>Creates a <span class="codeph"> TargetLocationRequest </span> object with the given parameters. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax java">
      public&amp;nbsp;static&amp;nbsp;TargetLocationRequest&amp;nbsp;createRequest(String&amp;nbsp;name,&amp;nbsp;String&amp;nbsp;defaultContent,&amp;nbsp;Map&amp;lt;String,&amp;nbsp;Object&amp;gt;&amp;nbsp;parameters); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax java">
      TargetLocationRequest&amp;nbsp;heroBannerRequest&amp;nbsp;=&amp;nbsp;Target.createRequest("heroBanner",&amp;nbsp;"default.png",&amp;nbsp;null); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>clearCookies </p> </td> 
   <td colname="col2"> <p>Clears any target cookies from your app. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax java">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;clearCookies(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax java">
      Target.clearCookies(); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>getPcID </p> </td> 
   <td colname="col2"> <p>Returns the pcID. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax java">
      public&amp;nbsp;static&amp;nbsp;String&amp;nbsp;getPcID(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax java">
      Target.getPcID(); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>getSessionID </p> </td> 
   <td colname="col2"> <p>Returns the session ID. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax java">
      public&amp;nbsp;static&amp;nbsp;String&amp;nbsp;getSessionID(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax java">
      Target.getSessionID(); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>setThirdPartyID </p> </td> 
   <td colname="col2"> <p> Sets the third-party ID. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax java">
      public&amp;nbsp;static&amp;nbsp;String&amp;nbsp;setThirdPartyID(final&amp;nbsp;String&amp;nbsp;thirdPartyId); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax java">
      Target.setThirdPartyID(“third-party-id”); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>getThirdPartyID </p> </td> 
   <td colname="col2"> <p> Returns the third-party ID. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax java">
      public&amp;nbsp;static&amp;nbsp;String&amp;nbsp;getThirdPartyID(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax java">
      String&amp;nbsp;thirdPartyId&amp;nbsp;=&amp;nbsp;Target.getThirdPartyID(); 
    </codeblock> </td> 
  </tr> 
 </tbody> 
</table>

