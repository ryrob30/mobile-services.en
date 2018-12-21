---
description: Here is the list of Adobe Target methods that are provided by the iOS library.
seo-description: Here is the list of Adobe Target methods that are provided by the iOS library.
seo-title: iOS Target Methods for Adobe Mobile Services
solution: Marketing Cloud,Analytics
title: Target Methods for iOS
topic: Developer and implementation
uuid: 692bcda1-02ba-4902-bd65-15888adf1952
---

# Target Methods for iOS {#target-methods}

Here is the list of Adobe Target methods that are provided by the iOS library.

The SDK currently has support for multiple [!DNL Adobe Experience Cloud Solutions], including [!DNL Analytics], [!DNL Target], [!DNL Audience Manager], and the [!DNL Experience Cloud ID service]. Methods are prefixed according to the solution. For example, [!DNL Target] methods are prefixed with `target`.

>[!TIP]
>
>[Lifecycle Metrics](../metrics.md) are sent as parameters to each mbox load.

## Class Reference : ADBTargetLocationRequest

**Properties**

```java
NSString *name; 
NSString *defaultContent; 
NSMutableDictionary *parameters;
```

**String Constants**

>[!TIP]
>
>The following constants are for ease of use when you set keys for custom parameters.

```java
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
>* If you are using SDKs **before** version 4.14.0, see [https://developers.adobetarget.com/api/#input-parameters](https://developers.adobetarget.com/api/#input-parameters) for parameters limitations. 
>
>* If you are using SDKs version 4.14.0 **or after**, see [https://developers.adobetarget.com/api/#batch-input-parameters](https://developers.adobetarget.com/api/#batch-input-parameters) for parameters limitations. 

### targetLoadRequest:​callback

`targetLoadRequest:​callback:`

Sends request to your configured Target server and returns the string value of the offer that is generated in a block `callback`.

**Syntax:**

```java
+ (void) targetLoadRequest:(ADBTargetLocationRequest \*)request
                    callback:(void (^)(NSString \*content))callback;
```

**Example:**

```java
\[ADBMobile targetLoadRequest:myRequest
                      callback:^(NSString \*content) {
                           // do something with content
 }\];
```

### targetLoadRequestWithName Location

`targetLoadRequestWithName:defaultContent:profileParameters:orderParameters:mboxParameters:requestLocationParameters:callback:`

Sends a request to your configured Target server and returns the string value of the offer that is generated in a block callback.

**Syntax:**

```java
+ (void) targetLoadRequestWithName:(nullable NSString \*)name
                     defaultContent:(nullable NSString \*)defaultContent
                   profileParameters:(nullable NSDictionary \*)profileParameters
                      orderParameters:(nullable NSDictionary \*)orderParameters
                        mboxParameters:(nullable NSDictionary \*)mboxParameters 
             requestLocationParameters:(nullable NSDictionary \*)requestLocationParameters 
                              callback:(nullable void (^)(NSString\* \_\_nullable content))callback;
```

**Returns:** N/A

**Parameters:**

|Name:  |Description: |
|--- |--- |
|name|**Type**: NSString * <br>Name of the Target mbox/location that you want to retrieve.|
|defaultContent|**Type**: NSString * <br>Value returned in the callback if the Target server is unreachable, or the user does not qualify for the campaign.|
|profileParameters|**Type**: NSDictionary * <br>Values in this dictionary will go in the "profileParameters" object in the request to Target.|
|orderParameters|**Type**: NSDictionary * <br>Values in this dictionary will go in the "order" object in the request to Target.|
|mboxParameters|**Type**: NSDictionary * <br>Values in this dictionary will go in the "mboxParameters" object in the request to Target.|
|requestLocationParameters|**Type**: NSDictionary * <br>Values in this dictionary will go in the "requestLocation" object in the request to Target.|
|callback|**Type**: Function <br>This method will be called with the content of the offer from the Target server. If the Target server is unreachable, or the user does not qualify for the campaign, defaultContent will be returned.|

**Example:**

```java
\[ADBMobile targetLoadRequestWithName:@"myHeroBanner"
                       defaultContent:@"defaultHeroBanner.png"
                     profileParameters:@{@"age":@"20-29"} 
                       orderParameters:nil 
                        mboxParameters:@{@"customParam":@"customValue"}
              requestLocationParameters:@{@"host":@"my.hostname.com"}
                                callback:^(NSString \*content){ 
                                       // do something with content 
                                       myImageView.image = \[UIImage imageNamed:content\];
                                     }\];
```

For more information about the underlying Target API, see the [Delivery documentation on the Target Developers website](https://docs.adobe.com/dev/products/target/reference/delivery.html) .

### targetLoadRequestWithName mbox

`targetLoadRequestWithName:defaultContent:profileParameters:orderParameters:mboxParameters:callback:`

Sends request to your configured Target server and returns the string value of the offer generated in a block callback.

**Syntax:**

```java
+ (void) targetLoadRequestWithName:(nullable NSString \*)name
         defaultContent:(nullable NSString \*)defaultContent
          profileParameters:(nullable NSDictionary \*)profileParameters
             orderParameters:(nullable NSDictionary \*)orderParameters
               mboxParameters:(nullable NSDictionary \*)mboxParameters
                      callback:(nullable void (^)(NSString\* \_\_nullable content))callback;
```

**Example:**

```java
\[ADBMobile targetLoadRequestWithName:@"mboxName"
              defaultContent:@"defaultContent" 
           profileParameters:@{@"profile-parameter-key": @"profile-parameter-value"}
           orderParameters:@{@"order-parameter-key": @"order-parameter-value"}
                mboxParameters:@{@"mbox-parameter-key": @"mbox-parameter-value"}
                  callback:^(NSString\* content) {
                              //do something with content 
                          }                            }\];
```

### targetCreateOrder​ConfirmRequestWithName:​orderId:​orderTotal:​productPurchasedId:​parameters

`targetCreateOrder​ConfirmRequestWithName:​orderId:​orderTotal:​productPurchasedId:​parameters:`

Creates an `ADBTargetLocationRequest`.

**Syntax:**

```java
+ (ADBTargetLocationRequest \*)  targetCreateOrderConfirmRequestWithName:(NSString \*)name 
                                orderId:(NSString \*)orderId 
                             orderTotal:(NSString \*)orderTotal 
                     productPurchasedId:(NSString \*)productPurchasedId
                              parameters:(NSDictionary \*)parameters;
```

### targetCreateRequestWithName:​​defaultContent:​parameters

Convenience constructor to create an ADBTargetLocationRequest object with the given parameters.

**Syntax:**

```java
+ (ADBTargetLocationRequest \*)  targetCreateRequestWithName:(NSString \*)name 
              defaultContent:(NSString \*)defaultContent 
                   parameters:(NSDictionary \*)parameters;
```

**Example:**

```java
ADBTargetLocationRequest \*myRequest =  \[ADBMobile targetCreateRequestWithName:@"heroBanner"                          defaultContent:@"default.png"
                              parameters:nil\];
```

### targetThirdPartyID

Returns the third-party ID.

**Syntax:**

```java
+ (nullable NSString \*) targetThirdPartyID;
```

**Example:**

```java
NSString \*thirdPartyId = \[ADBMobile targetThirdPartyID\];
```

### targetSetThirdPartyID

`targetSetThirdPartyID:`

Sets the third-party ID.

**Syntax:**

```java
+ (void) targetSetThirdPartyID:(nullable NSString \*)thirdPartyID;
```

**Example:**

```java
\[ADBMobile targetSetThirdPartyID:@"thirdPartyID"\];
```

### targetClearCookies

Clears any target cookies from your app.

>[!Tip]
>
>Since version 4.10.0 of the SDK, Target no longer uses cookies. This method resets the thirdPartyID and sessionID.

**Syntax:**

```java
+ (void) targetClearCookies;
```

**Example:**

`\[ADBMobile targetClearCookies\];`

### targetPcID

Returns the PcID.

**Syntax:**

`+ (nullable NSString \*) targetPcID;`

**Example:**

`NSString \*myTargetPcID = \[ADBMobile targetPcID\];`

### targetSessionID

Returns the SessionID.

**Syntax:**

`+ (nullable NSString \*) targetPcID;`

**Example:**

`NSString \*myTargetSessionID = \[ADBMobile targetSessionID\];`

**Example:**

```java
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
