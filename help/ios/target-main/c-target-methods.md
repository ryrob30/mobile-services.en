---
description: Here is the list of Adobe Target methods that are provided by the iOS library.
seo-description: Here is the list of Adobe Target methods that are provided by the iOS library.
seo-title: Target Methods
solution: Marketing Cloud,Analytics
title: Target Methods
topic: Developer and implementation
uuid: 692bcda1-02ba-4902-bd65-15888adf1952
index: y
internal: n
snippet: y
---

# Target Methods{#target-methods}

Here is the list of Adobe Target methods that are provided by the iOS library.

 The SDK currently has support for multiple [!DNL Adobe Experience Cloud Solutions], including [!DNL Analytics], [!DNL Target], [!DNL Audience Manager], and the [!DNL Experience Cloud ID service]. Methods are prefixed according to the solution. For example, [!DNL Target] methods are prefixed with `target`.

>[!TIP]
>
>[Lifecycle Metrics](../metrics.md#concept_77CA5CEB51D1418FB98EC7C044682A05) are sent as parameters to each mbox load.

**Class Reference : ADBTargetLocationRequest**

**Properties**

```
NSString *name; 
NSString *defaultContent; 
NSMutableDictionary *parameters;
```

**String Constants**

>[!TIP]
>
>The following constants are for ease of use when you set keys for custom parameters.

```
NSString *const ADBTargetParameterOrderId; 
NSString *const ADBTargetParameterOrderTotal; 
NSString *const ADBTargetParameterProductPurchasedId; 
NSString *const ADBTargetParameterCategoryId; 
NSString *const ADBTargetParameterMbox3rdPartyId; 
NSString *const ADBTargetParameterMboxPageValue; 
NSString *const ADBTargetParameterMboxPc; 
NSString *const ADBTargetParameterMboxSessionId; 
NSString *const ADBTargetParameterMboxHost;
```

>[!IMPORTANT]
>
>* If you are using SDKs **before** version 4.14.0, see [http://developers.adobetarget.com/api/#input-parameters](http://developers.adobetarget.com/api/#input-parameters) for parameters limitations. 
>
>* If you are using SDKs version 4.14.0 **or after**, see [http://developers.adobetarget.com/api/#batch-input-parameters](http://developers.adobetarget.com/api/#batch-input-parameters) for parameters limitations. 
>

<table id="table_AD066582C8E2478A8DC0A59B78ACB443" class="codescroll"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Method </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>targetLoadRequest:​callback: </p> </td> 
   <td colname="col2"> <p>Sends <span class="codeph"> request </span> to your configured Target server and returns the string value of the offer that is generated in a block <span class="codeph"> callback </span>. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      +&nbsp;(void)&nbsp;targetLoadRequest:(ADBTargetLocationRequest&nbsp;*)request&nbsp; 
     
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;callback:(void&nbsp;(^)(NSString&nbsp;*content))callback; 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      [ADBMobile&nbsp;targetLoadRequest:myRequest&nbsp; 
     
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;callback:^(NSString&nbsp;*content)&nbsp;{ 
     
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;//&nbsp;do&nbsp;something&nbsp;with&nbsp;content 
     
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}]; 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>targetLoadRequestWithName:defaultContent:profileParameters:orderParameters:mboxParameters:requestLocationParameters:callback: </p> </td> 
   <td colname="col2"> <p>Sends a request to your configured <span class="keyword"> Target </span> server and returns the string value of the offer that is generated in a block callback. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      +&nbsp;(void)&nbsp;targetLoadRequestWithName:(nullable&nbsp;NSString&nbsp;*)name 
     
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;defaultContent:(nullable&nbsp;NSString&nbsp;*)defaultContent 
     
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;profileParameters:(nullable&nbsp;NSDictionary&nbsp;*)profileParameters 
     
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;orderParameters:(nullable&nbsp;NSDictionary&nbsp;*)orderParameters 
     
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;mboxParameters:(nullable&nbsp;NSDictionary&nbsp;*)mboxParameters 
     
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;requestLocationParameters:(nullable&nbsp;NSDictionary&nbsp;*)requestLocationParameters 
     
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;callback:(nullable&nbsp;void&nbsp;(^)(NSString*&nbsp;__nullable&nbsp;content))callback; 
    </codeblock> <p><b>Returns: </b>N/A </p> <p><b>Parameters:</b> </p> <p>  </p>
    <table id="table_181608D5BE66448DBD09A20003097ACF">  
    </table> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      [ADBMobile&nbsp;targetLoadRequestWithName:@"myHeroBanner" 
     
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;defaultContent:@"defaultHeroBanner.png" 
     
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;profileParameters:@{@"age":@"20-29"} 
     
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;orderParameters:nil 
     
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;mboxParameters:@{@"customParam":@"customValue"} 
     
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;requestLocationParameters:@{@"host":@"my.hostname.com"} 
     
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;callback:^(NSString&nbsp;*content){&nbsp; 
     
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;//&nbsp;do&nbsp;something&nbsp;with&nbsp;content 
     
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;myImageView.image&nbsp;=&nbsp;[UIImage&nbsp;imageNamed:content];&nbsp; 
     
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}]; 
    </codeblock> <p>For more information about the underlying Target API, see the <a href="https://docs.adobe.com/dev/products/target/reference/delivery.html" format="html" scope="external"> Delivery documentation on the Target Developers website </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>targetLoadRequestWithName:defaultContent:profileParameters:orderParameters:mboxParameters:callback: </p> </td> 
   <td colname="col2"> <p> Sends request to your configured <span class="keyword"> Target </span> server and returns the string value of the offer generated in a block <span class="codeph"> callback </span>. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      +&nbsp;(void)&nbsp;targetLoadRequestWithName:(nullable&nbsp;NSString&nbsp;*)name 
     
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;defaultContent:(nullable&nbsp;NSString&nbsp;*)defaultContent 
     
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;profileParameters:(nullable&nbsp;NSDictionary&nbsp;*)profileParameters 
     
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;orderParameters:(nullable&nbsp;NSDictionary&nbsp;*)orderParameters 
     
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;mboxParameters:(nullable&nbsp;NSDictionary&nbsp;*)mboxParameters 
     
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;callback:(nullable&nbsp;void&nbsp;(^)(NSString*&nbsp;__nullable&nbsp;content))callback; 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      [ADBMobile&nbsp;targetLoadRequestWithName:@"mboxName" 
     
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;defaultContent:@"defaultContent" 
     
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;profileParameters:@{@"profile-parameter-key":&nbsp;@"profile-parameter-value"} 
     
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;orderParameters:@{@"order-parameter-key":&nbsp;@"order-parameter-value"} 
     
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;mboxParameters:@{@"mbox-parameter-key":&nbsp;@"mbox-parameter-value"} 
     
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;callback:^(NSString*&nbsp;content)&nbsp;{ 
     
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;//do&nbsp;something&nbsp;with&nbsp;content 
     
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;} 
     
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}]; 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>targetCreateOrder​ConfirmRequestWithName:​orderId:​orderTotal:​productPurchasedId:​parameters: </p> </td> 
   <td colname="col2"> <p>Creates an <span class="codeph"> ADBTargetLocationRequest </span>. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      +&nbsp;(ADBTargetLocationRequest&nbsp;*)&nbsp; 
     
targetCreateOrderConfirmRequestWithName:(NSString&nbsp;*)name 
     
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;orderId:(NSString&nbsp;*)orderId 
     
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;orderTotal:(NSString&nbsp;*)orderTotal 
     
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;productPurchasedId:(NSString&nbsp;*)productPurchasedId 
     
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;parameters:(NSDictionary&nbsp;*)parameters; 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>targetCreateRequestWithName:​​defaultContent:​parameters </p> </td> 
   <td colname="col2"> <p>Convenience constructor to create an <span class="codeph"> ADBTargetLocationRequest </span> object with the given parameters. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      +&nbsp;(ADBTargetLocationRequest&nbsp;*)&nbsp; 
     
targetCreateRequestWithName:(NSString&nbsp;*)name&nbsp; 
     
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;defaultContent:(NSString&nbsp;*)defaultContent&nbsp; 
     
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;parameters:(NSDictionary&nbsp;*)parameters; 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBTargetLocationRequest&nbsp;*myRequest&nbsp;=&nbsp; 
     
[ADBMobile&nbsp;targetCreateRequestWithName:@"heroBanner"&nbsp; 
     
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;defaultContent:@"default.png"&nbsp; 
     
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;parameters:nil]; 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> targetThirdPartyID </p> </td> 
   <td colname="col2"> <p> Returns the third-party ID. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      +&amp;nbsp;(nullable&amp;nbsp;NSString&amp;nbsp;*)&amp;nbsp;targetThirdPartyID; 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      NSString&amp;nbsp;*thirdPartyId&amp;nbsp;=&amp;nbsp;[ADBMobile&amp;nbsp;targetThirdPartyID]; 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> targetSetThirdPartyID: </p> </td> 
   <td colname="col2"> <p> Sets the third-party ID. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      +&amp;nbsp;(void)&amp;nbsp;targetSetThirdPartyID:(nullable&amp;nbsp;NSString&amp;nbsp;*)thirdPartyID; 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      [ADBMobile&amp;nbsp;targetSetThirdPartyID:@"thirdPartyID"]; 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>targetClearCookies </p> </td> 
   <td colname="col2"> <p>Clears any target cookies from your app. </p> <p> <p>Tip:  Since version 4.10.0 of the SDK, <span class="keyword"> Target </span> no longer uses cookies. This method resets the <span class="codeph"> thirdPartyID </span> and <span class="codeph"> sessionID </span>. </p> </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      +&amp;nbsp;(void)&amp;nbsp;targetClearCookies; 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      [ADBMobile&amp;nbsp;targetClearCookies]; 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> targetPcID </p> </td> 
   <td colname="col2"> <p> Returns the PcID. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      +&amp;nbsp;(nullable&amp;nbsp;NSString&amp;nbsp;*)&amp;nbsp;targetPcID; 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      NSString&amp;nbsp;*myTargetPcID&amp;nbsp;=&amp;nbsp;[ADBMobile&amp;nbsp;targetPcID]; 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> targetSessionID </p> </td> 
   <td colname="col2"> <p> Returns the SessionID. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      +&amp;nbsp;(nullable&amp;nbsp;NSString&amp;nbsp;*)&amp;nbsp;targetPcID; 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      NSString&amp;nbsp;*myTargetSessionID&amp;nbsp;=&amp;nbsp;[ADBMobile&amp;nbsp;targetSessionID]; 
    </codeblock> </td> 
  </tr> 
 </tbody> 
</table>

**Example:**

```
// make your request 
ADBTargetLocationRequest *myRequest =  
 [ADBMobile targetCreateRequestWithName:@"heroBanner"  
                         defaultContent:@"default.png"  
                             parameters:nil]; 
// load your request 
[ADBMobile targetLoadRequest:myRequest  
                    callback:^(NSString *content) { 
                        // do something with content 
                        heroImage.image = [UIImage imageNamed:content];   
                    }];
```

