---
description: The Adobe Target prefetch feature uses the iOS Mobile SDKs to fetch offer content as few times as possible by caching the server responses.
seo-description: The Adobe Target prefetch feature uses the iOS Mobile SDKs to fetch offer content as few times as possible by caching the server responses.
seo-title: Prefetch offer content in iOS
title: Prefetch offer content in iOS
uuid: fef58042-65e2-4579-b8f1-d21554d2af57
index: y
internal: n
snippet: y
---

# Prefetch offer content in iOS{#prefetch-offer-content-in-ios}

The Adobe Target prefetch feature uses the iOS Mobile SDKs to fetch offer content as few times as possible by caching the server responses.

This process reduces the load time, prevents multiple network calls, and allows Adobe Target to be notified which mbox was visited by the mobile app user. All content will be retrieved and cached during the prefetch call, and this content will be retrieved from the cache for all future calls that contain cached content for the specified mbox name.

Prefetch content does not persist across launches. The prefetch content is cached as long as the application lives or until the `clearPrefetchCache()` method is called.

>[!IMPORTANT]
>
>Target prefetch APIs have been available since SDK version 4.14.0. For more information about parameter limitations, see [https://developers.adobetarget.com/api/#batch-input-parameters](https://developers.adobetarget.com/api/#batch-input-parameters).

In SDK version 4.14 or later, if specified, the `environmentId` is picked from the ADBMobileConfig.json file when initiating a v2 batch mbox TnT call. If no `environmentId` is specified in this file, no environment parameter is sent in TNT batch mbox call, and offer is delivered for the default environment.

For example:

```
if (MobileConfig.getInstance().mobileUsingTarget()){ 
            long environmentID = MobileConfig.getInstance().getEnvironmentID(); 
            if(environmentID != 0L){ 
                parametersJson.put(TargetJson.ENVIRONMENT_ID, environmentID); 
            } 
        }
```

## Pre-fetch Methods {#section_05967F1F3A554B0FBC2C08A954554BDE}

Here are the methods that you can use for prefetch in iOS:

<table id="table_5690297F6526421698A01BAF995776B5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>targetPrefetchContent </p> </td> 
   <td colname="col2"> <p>Sends a prefetch request with an array of locations to the configured Target server and returns the request status in the provided callback. </p> <p><b>Syntax</b> </p> <p> 
     <codeblock class="syntax objective-c">
       (void)&nbsp;targetPrefetchContent:(nonnull&nbsp;NSArray&nbsp;*)targetPrefetchObjectArray 
      
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;withProfileParameters:(nullable&nbsp;NSDictionary&nbsp;*)profileParameters 
      
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;callback:(nullable&nbsp;void(^)(BOOL&nbsp;success))callback;

     </codeblock> </p> <p><b>Parameters</b> 
     <table id="table_F9566AA2648843AC93674C376C3B2B08">  
     </table> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>targetLoadRequests </p> </td> 
   <td colname="col2"> <p>Executes a batch request for multiple mbox locations that are specified in the requests array. &amp;nbsp;Each object in the array contains a callback function, which will be invoked when content is available for its given mbox location. </p> <p> <p>Important:  If the content for the requested locations is already cached, it will be returned immediately in the provided callback. Otherwise, the SDK will send a network request to the Target servers to retrieve the content. </p> </p> <p>Syntax: 
     <codeblock class="syntax objective-c">
       (void)&nbsp;targetLoadRequests:(nonnull&nbsp;NSArray&nbsp;*)requests 
      
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;withProfileParameters:(nullable&nbsp;NSDictionary&nbsp;*)profileParameters;

     </codeblock> </p> <p><b>Parameters</b>: </p> <p> 
     <table id="table_52BA3E5A5A0F4CDB87F156E52DEA6284">  
     </table> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>targetPrefetchClearCache </p> </td> 
   <td colname="col2"> <p>Clears the data that was cached by Target Prefetch. </p> <p><b>Syntax</b>: </p> <p> 
     <codeblock class="syntax objective-c">
       (void)&amp;nbsp;targetPrefetchClearCache; 
     </codeblock> </p> <p><b>Parameters</b>: N/A </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>targetRequestObjectWithName </p> </td> 
   <td colname="col2"> <p>Creates and returns an instance of <span class="codeph"> TargetRequestObject </span> with the provided data. </p> <p><b>Syntax</b>: </p> <p> 
     <codeblock class="syntax objective-c">
       +&nbsp;(nullable&nbsp;ADBTargetRequestObject&nbsp;*)&nbsp;targetRequestObjectWithName:(nonnull&nbsp;NSString&nbsp;*)name&nbsp;

defaultContent:(nonnull&nbsp;NSString&nbsp;*)defaultContent

mboxParameters:(nullable&nbsp;NSDictionary&nbsp;*)mboxParameters&nbsp;

callback:(nullable&nbsp;void&nbsp;(^)(NSString*&nbsp;__nullable&nbsp;content))callback;

     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>createTargetPrefetchObject </p> </td> 
   <td colname="col2"> <p>Creates and returns an instance of <span class="codeph"> TargetPrefetchObject </span> with the provided data. </p> <p><b>Syntax</b>: </p> <p> 
     <codeblock class="syntax objective-c">
       +&nbsp;(nullable&nbsp;ADBTargetPrefetchObject&nbsp;*)&nbsp;targetPrefetchObjectWithName:(nonnull&nbsp;NSString&nbsp;*)name&nbsp;

mboxParameters:(nullable&nbsp;NSDictionary&nbsp;*)mboxParameters;

     </codeblock> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Public Classes {#section_A273E53F069E4327BBC8CE4910B37888}

Here are the public classes that support pre-fetch in iOS :

**Class Reference: TargetPreFetchObject**

Encapsulates the mbox name and the parameters that are used for mbox prefetch.

<table id="table_987E9D0D9B76495A9ED9EF851AFCAD16"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Property </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>name </p> </td> 
   <td colname="col2"> <p><b>Type</b>: NSString* </p> <p>The NSString value that represents the name for the location/mbox you want to retrieve. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>mboxParameters </p> </td> 
   <td colname="col2"> <p><b>Type</b>: NSDictionary* </p> <p>An optional dictionary that contains the key-value pairs of mbox parameters. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>orderParameters </p> </td> 
   <td colname="col2"> <p><b>Type</b>: NSDictionary* </p> <p>Dictionary that contains the key-value pairs of order parameters. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>productParameters </p> </td> 
   <td colname="col2"> <p><b>Type</b>: NSDictionary* </p> <p>Dictionary that contains the key-value pairs of product parameters. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Class Reference: TargetRequestObject **

This class encapsulates the mbox name, default content, mbox parameters and the return callback used for Target location requests.

<table id="table_47A7702703144124B6CC2974FF24FD05"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Property </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>name </p> </td> 
   <td colname="col2"> <p><b>Type</b>: NSString* </p> <p>Name of the requested location. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>mboxParameters </p> </td> 
   <td colname="col2"> <p><b>Type</b>: </p> <p>The NSString value that represents the name for the location/mbox you want to retrieve. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>defaultContent </p> </td> 
   <td colname="col2"> <p><b>Type</b>: NSString* </p> <p>The default content that will be returned if Target servers are unreachable. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>callback </p> </td> 
   <td colname="col2"> <p><b>Type</b>: Function </p> When the batch requests Target locations, callback will be invoked when content is available for this location. </td> 
  </tr> 
 </tbody> 
</table>

## Code Sample {#section_BF7F49763D254371B4656E17953D520C}

Here is an example of how to prefetch content by using the iOS SDKs:

```
/** 
 * Prefetch Content 
 */ 
  
    NSDictionary *mboxParameters1 = @{@"status":@"platinum"}; 
    NSDictionary *productParameters1 = @{@"id":@"24D3412", 
                                        @"categoryId":@"Books"}; 
    NSDictionary *orderParameters1 = @{@"id":@"ADCKKIM", 
                                      @"total":@"344.30", 
                                      @"purchasedProductIds":@"34, 125, 99"};

    NSDictionary *mboxParameters2 = @{@"userType":@"Paid"}; 
    NSDictionary *productParameters2 = @{@"id":@"764334", 
                                         @"categoryId":@"Online"}; 
  
    NSArray *purchaseIDs = @[@"id1",@"id2"]; 
    NSDictionary *orderParameters2 = @{@"id":@"4t4uxksa", 
                                       @"total":@"54.90", 
                                       @"purchasedProductIds":purchaseIDs};

    // Creating Prefetch Objects 
    ADBTargetPrefetchObject *prefetch1 = [ADBMobile targetPrefetchObjectWithName:@"logo" mboxParameters:mboxParameters1]; 
    prefetch1.productParameters = productParameters1; 
    prefetch1.orderParameters = orderParameters1; 
  
    ADBTargetPrefetchObject *prefetch2 = [ADBMobile targetPrefetchObjectWithName:@"buttonColor" mboxParameters:mboxParameters2]; 
    prefetch2.productParameters = productParameters2; 
    prefetch2.orderParameters = orderParameters2; 
                                           
    // Creating prefetch Array 
    NSArray *prefetchArray = @[prefetch1,prefetch2]; 
  
    // Creating Profile parameters 
    NSDictionary *profileParmeters = @{@"age":@"20-32"};

    // Target API Call 
    [ADBMobile targetPrefetchContent:prefetchArray withProfileParameters:profileParmeters callback:^(BOOL isSuccess){ 
       // do something with the Boolean result 
    }];

```

Here is an example of the batch `loadRequest` by using the iOS SDKs: 

```
/** 
 * Batch loadRequest  
 */ 
  
   NSDictionary *mboxParameters1 = @{@"status":@"platinum"}; 
   NSDictionary *productParameters1 = @{@"id":@"24D3412", 
                                        @"categoryId":@"Books"}; 
   NSDictionary *orderParameters1 = @{@"id":@"ADCKKIM", 
                                      @"total":@"344.30", 
                                      @"purchasedProductIds":@"34, 125, 99"};

    NSDictionary *mboxParameters2 = @{@"userType":@"Paid"}; 
    NSDictionary *productParameters2 = @{@"id":@"764334", 
                                         @"categoryId":@"Online"}; 
    NSArray *purchaseIDs = @[@"id1",@"id2"]; 
    NSDictionary *orderParameters2 = @{@"id":@"4t4uxksa", 
                                       @"total":@"54.90", 
                                       @"purchasedProductIds":purchaseIDs};

    ADBTargetRequestObject *request1 = [ADBMobile targetRequestObjectWithName:@"logo" defaultContent:@"BlueWhale" mboxParameters:mboxParameters1 callback:^(NSString *content){ 
        // do something with the received content 
    }]; 
  
    request1.productParameters = productParameters1; 
    request1.orderParameters = orderParameters1;

    ADBTargetRequestObject *request2 = [ADBMobile targetRequestObjectWithName:@"buttonColor" defaultContent:@"red" mboxParameters:mboxParameters2 callback:^(NSString *content){ 
        // do something with the received content 
    }]; 
    request2.productParameters = productParameters1; 
    request2.orderParameters = orderParameters1;

    // create request object array 
    NSArray *requestArray = @[request1,request2]; 
  
    // Call the API 
    [ADBMobile targetLoadRequests:requestArray withProfileParameters:profileParmeters];
```

## Additional Information {#section_A454BAD1CD49423E86C71BAEE06125FD}

Here is some additional information about these samples:

* `ProductParameters` only allows the following keys:

    * `id` 
    * `categoryId`

* `OrderParameters` only allows the following keys:

    * `id` 
    * `total` 
    * `purchasedProductIds`

* `purchasedProducts` accepts an array of strings.

