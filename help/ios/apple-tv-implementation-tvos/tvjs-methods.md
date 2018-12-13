---
description: Here is a list of TVJS methods that are provided by the tvOS library.
seo-description: Here is a list of TVJS methods that are provided by the tvOS library.
seo-title: TVJS Methods
solution: Marketing Cloud,Analytics
title: TVJS Methods
topic: Developer and implementation
uuid: a7bfa85a-0d6e-4f51-9a9e-70429c2a9806
index: y
internal: n
snippet: y
---

# TVJS Methods{#tvjs-methods}

Here is a list of TVJS methods that are provided by the tvOS library.

This section contains the following information

* [Configuration Methods](../apple-tv-implementation-tvos/tvjs-methods.md#section_5F82FD2F6A0546B3B4E80DF832E11634) 
* [Analytics Methods](../apple-tv-implementation-tvos/tvjs-methods.md#section_F3DB9BE225F84F86BE5F8D15164C0379) 
* [Audience Manager Methods](../apple-tv-implementation-tvos/tvjs-methods.md#section_0155C4DF04644EDAAF6159C420A158DE) 
* [ID Service Methods](../apple-tv-implementation-tvos/tvjs-methods.md#section_BEB6DA612EA4423FB354B65ECC941335) 
* [Target Methods](../apple-tv-implementation-tvos/tvjs-methods.md#section_F9F7EC2B9B7C41AFBCA2458F9F138634)

## Configuration Methods {#section_5F82FD2F6A0546B3B4E80DF832E11634}

<table id="table_913992F10785483FAE4BF9FA7068B93D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Method </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> version </td> 
   <td colname="col2"> <p>Returns the current version of the Adobe Mobile library. </p> <p> 
     <ul id="ul_958417DB0E5A4285A1AE09DAEC635520"> 
      <li id="li_AF13CA2FC0034A4591AB91C4F4BEAE06"> <p><b>Syntax</b>: 
        <codeblock class="syntax c">
          version() 
        </codeblock> </p> </li> 
      <li id="li_52A126CBB44D418D9EC60672222D41FE"> <p><b>Returns</b>: String </p> </li> 
      <li id="li_3FECAD5A887642F79ED96535E43A44E8"> <p><b>Parameters</b>: None </p> </li> 
      <li id="li_988877E0D2F34826BD8BC77B7E8A2AED"> <p> <b>Example</b>: 
        <codeblock class="syntax c">
          var&amp;nbsp;sdkVersion&amp;nbsp;=&amp;nbsp;ADBMobile.version(); 
        </codeblock> </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> privacyStatus </td> 
   <td colname="col2"> <p>Returns the NSUInteger representation of the privacy status enum for current user. </p> <p>Here are the options: 
     <ul id="ul_5F5AA956D45C47E8A0901072E0772101"> 
      <li id="li_BA19A233B6C441ECB74E398681414919"> <p> <span class="codeph"> ADBMobilePrivacyStatusOptIn (1) </span>: Hits are sent immediately. </p> </li> 
      <li id="li_D85A1839565147788B6A38BF31ADD604"> <p> <span class="codeph"> ADBMobilePrivacyStatusOptOut (2) </span>: Hits are discarded. </p> </li> 
      <li id="li_1FC7574A04D942E387338FC07A89E278"> <p> <span class="codeph"> ADBMobilePrivacyStatusUnknown (3) </span>: If offline tracking is enabled, hits are saved until the privacy status changes to opt-in (then hits are sent) or opt-out (then hits are discarded). </p> <p>If offline tracking is not enabled, hits are discarded until the privacy status changes to opt-in. </p> </li> 
     </ul> </p> <p> 
     <ul id="ul_783EECCC83704786BD93C16133102D86"> 
      <li id="li_CB949263850141E79031936D20C9C90E"> <p>Default: The default value is set in <span class="filepath"> ADBMobileConfig.json </span>. </p> </li> 
      <li id="li_5E4FBE2A27E245859DCD6A8A88551074"> <p> <b>Syntax</b>: 
        <codeblock class="syntax c">
          privacyStatus() 
        </codeblock> </p> </li> 
      <li id="li_50AF3B2A308F4CF9BAA5B68B781AD7C3"> <p><b>Returns</b>: Number </p> </li> 
      <li id="li_8470FF681B9048248F627EF33B634027"> <p><b>Parameters</b>: None </p> </li> 
      <li id="li_612D1F707A4E4C8BBF023E1105D2B9C6"> <p> <b>Example</b>: </p> 
       <codeblock class="syntax c">
         var&amp;nbsp;privacyStatus&amp;nbsp;=&amp;nbsp;ADBMobile.privacyStatus(); 
       </codeblock> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> setPrivacyStatus </td> 
   <td colname="col2"> <p>Sets the privacy status for the current user to one of the following values: </p> 
    <ul id="ul_25266E9D0D18461595D961C7C5E92AA6"> 
     <li id="li_6082634A863E4B609678CE82BC7D6927"> <p> <span class="codeph"> ADBMobilePrivacyStatusOptIn </span>: Hits are sent immediately. </p> </li> 
     <li id="li_6D3417F73C82486A9F81A0CD29517C1F"> <p> <span class="codeph"> ADBMobilePrivacyStatusOptOut </span>: Hits are discarded. </p> </li> 
     <li id="li_7DFED463E6114965978CC01B1A705E35"> <p> <span class="codeph"> ADBMobilePrivacyStatusUnknown </span>: If offline tracking is enabled, hits are saved until the privacy status changes to opt-in (then hits are sent) or opt-out (then hits are discarded). </p> <p>If offline tracking is not enabled, hits are discarded until the privacy status changes to opt-in. </p> </li> 
    </ul> <p> 
     <ul id="ul_578D13087578407686D0EA8E3DF17954"> 
      <li id="li_16E7BA3C646F459DB1BAD1B51935063C"> <p><b>Syntax</b>: 
        <codeblock class="syntax c">
          setPrivacyStatus(privacyStatus) 
        </codeblock> </p> </li> 
      <li id="li_540385EBD0A14F6C8B2E755CB2E8899D"> <p><b>Returns</b>: N/A </p> </li> 
      <li id="li_4A0755D586434DEFB5C29393BDC2F833"> <p><b>Parameters</b>: </p> <p>  </p>
       <table id="table_2A58128097274AD6A192C1B41DC2AD6A">  
       </table> </li> 
      <li id="li_C5F9C066D2D84AB98C91E7B7CECF079A"> <p> <b>Example</b>: 
        <codeblock class="syntax c">
          ADBMobile.setPrivacyStatus(ADBMobilePrivacyStatusOptIn); 
        </codeblock> </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> lifetimeValue </td> 
   <td colname="col2"> <p>Returns the lifetime value of the current user. </p> <p> 
     <ul id="ul_CBF90B9BF4C24984B7B1E03AD529B5B2"> 
      <li id="li_4D95A5179AEA4B7A987A49C51089B876"> <p>Default: 0 </p> </li> 
      <li id="li_6C3D730D7B4E406291FF81595D3E387B"> <p> <b>Syntax</b>: 
        <codeblock class="syntax c">
          lifetimeValue() 
        </codeblock> </p> </li> 
      <li id="li_718A3B05594144389268D11D41F13520"> <p><b>Returns</b>: Number </p> </li> 
      <li id="li_20D218EB05E7442880B7CEF585FE6244"> <p><b>Parameters</b>: None </p> </li> 
      <li id="li_3FED12ED5F3D4CF480445AAA5998E8FB"> <p> <b>Example</b>: 
        <codeblock class="syntax c">
          var&amp;nbsp;ltv&amp;nbsp;=&amp;nbsp;ADBMobile.lifetimeValue(); 
        </codeblock> </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> userIdentifier </td> 
   <td colname="col2"> <p>Returns the user identifier if a custom identifier has been set. Returns nil if a custom identifier is not set. </p> <p>Default: <span class="codeph"> nil </span> </p> <p> <p>Important:  If your app upgrades from the Experience Cloud 3.x to 4.x SDK, the previous custom or automatically generated visitor ID is retrieved and stored as the custom user identifier. This preserves visitor data between SDK upgrades. For new installations on the 4.x SDK, user identifier is <span class="codeph"> nil </span> until set. </p> </p> <p> 
     <ul id="ul_490C3753D6F04C738677BB5451936C70"> 
      <li id="li_5617874667A444B48E03B48FED3CA68B"> <p><b>Syntax:</b> 
        <codeblock class="syntax c">
          userIdentifier() 
        </codeblock> </p> </li> 
      <li id="li_B1A9F0CA45F246DE8A370F9BA667414E"> <p><b>Returns</b>: String </p> </li> 
      <li id="li_78206E883AC447A7B1E3A4A6FE7B974D"> <p><b>Parameters</b>: None </p> </li> 
      <li id="li_95E56A40EAF3420A92AAABEB699ACD37"> <p> <b>Example</b>: 
        <codeblock class="syntax c">
          var&amp;nbsp;uid&amp;nbsp;=&amp;nbsp;ADBMobile.userIdentifier(); 
        </codeblock> </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> setUserIdentifier </td> 
   <td colname="col2"> <p>Sets the user identifier. </p> <p> 
     <ul id="ul_213C84084FEC430896BFC6D2043C784B"> 
      <li id="li_1ACC4A18FC8A4C6FB1D010ED0348D919"> <p><b>Syntax</b>: 
        <codeblock class="syntax c">
          setUserIdentifier(userId) 
        </codeblock> </p> </li> 
      <li id="li_15CB1785895C49DEAF0C56CFA31F8D87"> <p><b>Returns</b>: N/A </p> </li> 
      <li id="li_5B81BF6844B04922B503584C2A388DA8"> <p><b>Parameters</b>: </p> <p>  </p>
       <table id="table_978994F8ACE94F64B43CA8E282606AD4">  
       </table> </li> 
      <li id="li_9D55613047E043E1BB9BF602879035CC"> <p> <b>Example</b>: </p> 
       <codeblock class="syntax c">
         ADBMobile.setUserIdentifier(‘myUserId’); 
       </codeblock> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> setAdvertisingIdentifier </td> 
   <td colname="col2"> <p>Sets the IDFA in the SDK, and the IDFA will be sent in lifecycle if it has been set in the SDK. The IDFA can also be accessed in Signals (Postbacks). </p> <p> <p>Important:  Retrieve the IDFA from Apple APIs only if you are using an ad service. If you retrieve IDFA, and are not using it properly, your app might be rejected. </p> </p> <p> 
     <ul id="ul_0DC83AB6E9F14201808281BDB97DB26F"> 
      <li id="li_E2587E4CD69542C7A7A069C6AB4D82D7"> <p><b>Syntax</b>: 
        <codeblock class="syntax c">
          setAdvertisingIdentifier(idfa) 
        </codeblock> </p> </li> 
      <li id="li_7CDB12AACF5C4245A37A6707015DD977"> <p><b>Returns</b>: N/A </p> </li> 
      <li id="li_86ADB4AFCFEC4D1BACF5462A8BA73B31"> <p><b>Parameters</b>: </p> <p>  </p>
       <table id="table_22C2DF8C0555445E98E2E70B67C91105">  
       </table> </li> 
      <li id="li_BB002A4FC26D432A9B8598F060DC21C7"> <p> <b>Example</b>: 
        <codeblock class="syntax c">
          ADBMobile.setAdvertisingIdentifier(‘myIdfa’);
        </codeblock> </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> setDebugLogging </td> 
   <td colname="col2"> <p>Sets the debug logging preference. </p> <p> 
     <ul id="ul_A48C2551052D4180BBCDCB186C2EC49C"> 
      <li id="li_7D8CE632A6324FF383AB595089B5F208"> <p><b>Syntax</b>: 
        <codeblock class="syntax c">
          setDebugLogging(logging) 
        </codeblock> </p> </li> 
      <li id="li_D363AAFAF2D6476A9705E12B181E08FC"> <p><b>Returns</b>: N/A </p> </li> 
      <li id="li_90928747F2994FBE98D5835F1883D937"> <p><b>Parameters</b>: </p> <p>  </p>
       <table id="table_93322649F9794F8AB3D375C24DF94C66">  
       </table> </li> 
      <li id="li_76775E99B11146DCA86CA4E507AE9493"> <p> <b>Example</b>: 
        <codeblock class="syntax c">
          ADBMobile.setDebugLogging(true); 
        </codeblock> </p> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Analytics Methods {#section_F3DB9BE225F84F86BE5F8D15164C0379}

<table id="table_87B8A118591A4F30AB64D8FF1B22ABFD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Method </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> trackStateData </td> 
   <td colname="col2"> <p>Tracks an app state with optional context data. States are the views that are available in your app, such as <span class="codeph"> home dashboard </span>, <span class="codeph"> app settings </span>, cart, and so on. These states are similar to pages on a website, and <span class="codeph"> trackState </span> calls increment page views. </p> <p>If the state is empty, it displays as <span class="codeph"> app name app version (build) </span> in reports. If you see this value in reports, ensure you set the state in each <span class="codeph"> trackState </span> call. </p> <p> <p>Tip:  This is the only tracking call that increments page views. </p> </p> <p> 
     <ul id="ul_D454A0B0AD7D45E489B1F03A6C8EE6C0"> 
      <li id="li_22A084EF9A2F4EF88FBF21A9A7C191D3"> <p><b>Syntax</b>: 
        <codeblock class="syntax c">
          trackStateData(stateName&amp;nbsp;[,&amp;nbsp;contextData]) 
        </codeblock> </p> </li> 
      <li id="li_96E8644072424BB99DDC6271A00A7843"> <p><b>Returns</b>: N/A </p> </li> 
      <li id="li_FB0626D510BD499C9726426C66E6FB5C"> <p><b>Parameters</b>: </p> <p>  </p>
       <table id="table_BC87723047C94EF59395C266583FC087">  
       </table> </li> 
      <li id="li_B87953E1672A4B51A8083EC3C764659E"> <p> <b>Example</b>: 
        <codeblock class="syntax c">
          ADBMobile.trackStateData(‘homepage’,&amp;nbsp;{‘userid’:12345}); 
        </codeblock> </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trackActionData </td> 
   <td colname="col2"> <p>Tracks an action in your app. Actions are the things that happen in your app that you want to measure, such as <span class="codeph"> logons </span>, <span class="codeph"> banner taps </span>, <span class="codeph"> feed subscriptions </span>, and other metrics. </p> <p> 
     <ul id="ul_A62F1BCE4A164587B34F831103A2E5E4"> 
      <li id="li_8EAF665F0A52476E9975BC414B6D2097"> <p><b>Syntax</b>: 
        <codeblock class="syntax c">
          trackActionData(actionName&amp;nbsp;[,&amp;nbsp;contextData]) 
        </codeblock> </p> </li> 
      <li id="li_AE9451F82DF349CA999CB862ACCE9870"> <p><b>Returns</b>: N/A </p> </li> 
      <li id="li_F2CA502960B94302BA1399BC5FED7F44"> <p><b>Parameters</b>: </p> <p>  </p>
       <table id="table_D7480076D25E4924950D687B876C97EB">  
       </table> </li> 
      <li id="li_602A6660978E478DB274200E490819F5"> <p> <b>Example</b>: 
        <codeblock class="syntax c">
          ADBMobile.trackActionData(‘likeClicked’,&amp;nbsp;{‘imageName’:’funnyKitty’}); 
        </codeblock> </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trackLocationWithLatLonData </td> 
   <td colname="col2"> <p>Sends the current latitude and longitude coordinates. </p> <p>Also uses points of interest (POI) that are defined in the <span class="filepath"> ADBMobileConfig.json </span> file to determine whether the location that you entered as a parameter is within any of your POI. If the current coordinates are within a defined POI, a context data variable is populated and sent with the <span class="codeph"> trackLocation </span> call. </p> <p> 
     <ul id="ul_1411A5AB0A5847DBADBF8EDD4B53F959"> 
      <li id="li_2D10CC74896B42D1927D026DE18A899A"> <p><b>Syntax</b>: 
        <codeblock class="syntax c">
          trackLocationWithLatLonData(lat,&amp;nbsp;lon&amp;nbsp;[,&amp;nbsp;contextData]); 
        </codeblock> </p> </li> 
      <li id="li_88313D01FDE04BC5B79550C517877CA4"> <p><b>Returns</b>: N/A </p> </li> 
      <li id="li_26AA148382314662B1092DC14E298637"> <p><b>Parameters</b>: </p> <p>  </p>
       <table id="table_277F32B311474166893CD266B25945F0">  
       </table> </li> 
      <li id="li_93EC636D2ED24865BFA68059EF304925"> <p> <b>Example</b>: 
        <codeblock class="syntax c">
          ADBMobile.trackLocationWithLatLonData(43.36,&amp;nbsp;-116.12,&amp;nbsp;null); 
        </codeblock> </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trackLifetimeValueIncreaseJsData </td> 
   <td colname="col2"> <p>Adds an amount to the user's lifetime value. </p> <p> 
     <ul id="ul_45EFF7C8D30F4DB0BD34D82494F62FD5"> 
      <li id="li_A318239D1ED5438CA47918790EE68C69"> <p><b>Syntax</b>: 
        <codeblock class="syntax c">
          trackLifetimeValueIncreaseJsData(increaseAmount) 
        </codeblock> </p> </li> 
      <li id="li_7FFE799E701D4F9EA68BEA8B2665B9CD"> <p><b>Returns</b>: N/A </p> </li> 
      <li id="li_118FD870368A4D02A1B380412AC254EF"> <p><b>Parameters</b>: </p> <p>  </p>
       <table id="table_A2DED382C25644A1A4C012BAE2FD7B0A">  
       </table> </li> 
      <li id="li_7845FA5C7D4F44BCA827EF4C3EE3FB45"> <p> <b>Example</b>: 
        <codeblock class="syntax c">
          ADBMobile.trackLifetimeValueIncreaseJsData(5);

        </codeblock> </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trackTimedActionStartData </td> 
   <td colname="col2"> <p>Start a timed action with name action. </p> <p>If you call this method for an action that has already started, the previous timed action is overwritten. </p> <p> <p>Tip:  This call does not send a hit. </p> </p> <p> 
     <ul id="ul_51C655E600CB4D84B87B2541C67F22BB"> 
      <li id="li_541D00146C7D45C4B757202F847BEA2D"> <p><b>Syntax</b>: 
        <codeblock class="syntax c">
          trackTimedActionStartData(name&amp;nbsp;[,&amp;nbsp;contextData]) 
        </codeblock> </p> </li> 
      <li id="li_B080EA0BE45F490F8F7A40B801771EA0"> <p><b>Returns</b>: N/A </p> </li> 
      <li id="li_474810A03D0B4E17B4560C487D08C2B1"> <p><b>Parameters</b>: </p> <p>  </p>
       <table id="table_30814A756AF8432DAE14CFF704AE8DDB">  
       </table> </li> 
      <li id="li_7223F5D489A341EBAABD4FC0A94D092B"> <p> <b>Example</b>: 
        <codeblock class="syntax c">
          ADBMobile.trackTimedActionStartData(‘level1’,&nbsp;{‘userId’:42423});

        </codeblock> </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trackTimedActionUpdateData </td> 
   <td colname="col2"> <p>Pass in data to update the context data that is associated with the given action. </p> <p>The data passed in is appended to the existing data for the given action, and if the same key is already defined for action, the data is overwritten. </p> <p> <p>Tip:  This call does not send a hit. </p> </p> <p> 
     <ul id="ul_831A36171E4E41D987DD888600D74F48"> 
      <li id="li_E3638BA962A4407AB0B1C4612B6B7268"> <p><b>Syntax</b>: 
        <codeblock class="syntax c">
          trackTimedActionUpdateData(name&amp;nbsp;[,&amp;nbsp;contextData]) 
        </codeblock> </p> </li> 
      <li id="li_D8D5AF0CB3764E55A7324386D9711F55"> <p><b>Returns</b>: N/A </p> </li> 
      <li id="li_437DB664987E48B48F6B810C82A80C2D"> <p><b>Parameters</b>: </p> <p>  </p>
       <table id="table_7D82A8B3B4FA44EEB17545662D6E1D2E">  
       </table> </li> 
      <li id="li_FB813B136E1C498EA05FC5D20BE5D9E7"> <p> <b>Example</b>: 
        <codeblock class="syntax c">
          ADBMobile.trackTimedActionUpdateData(‘level1’);
        </codeblock> </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trackTimedActionEndJsLogic </td> 
   <td colname="col2"> <p>End a timed action. </p> <p>If you provide a callback function, you can access the final time values. If no callback is provided, or if the callback returns true, the Adobe SDK automatically sends a hit. When a <span class="codeph"> false </span> is returned from the callback, the timed action hit will be suppressed. </p> <p> 
     <ul id="ul_13556F59ECE94EAEAA0A8F25A1F2EEB7"> 
      <li id="li_26757771A42749129EFA5DB99FA8156B"> <p><b>Syntax</b>: 
        <codeblock class="syntax c">
          trackTimedActionEndJsLogic(name&amp;nbsp;[,&amp;nbsp;callback]) 
        </codeblock> </p> </li> 
      <li id="li_A58EB41A2E8049EB9567A195F0EE6393"> <p><b>Returns</b>: N/A </p> </li> 
      <li id="li_20CB7085082A411FB6B4A9D1E42A9189"> <p><b>Parameters</b>: </p> <p>  </p>
       <table id="table_6258076EE2D142F8ABB6AFB0CA246888">  
       </table> </li> 
      <li id="li_28E6521FD86248548C46A57B81DF6D16"> <p> <b>Example</b>: 
        <codeblock class="syntax c">
          ADBMobile.trackTimedActionEndJsLogic(‘level1’,&nbsp;function(inAppDuration,&nbsp;totalDuration,&nbsp;data)&nbsp;{&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;//&nbsp;do&nbsp;something&nbsp;with&nbsp;final&nbsp;values&nbsp;&nbsp;&nbsp;&nbsp;return&nbsp;true;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}); 
        </codeblock> </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trackingTimedActionExistsJs </td> 
   <td colname="col2"> <p>Returns whether a timed action is in progress. </p> <p> 
     <ul id="ul_2B7B6B80D54842E8805FDD54A8E3DAD4"> 
      <li id="li_6F460645BED8439A8C18F583514C0CB9"> <p><b>Syntax</b>: 
        <codeblock class="syntax c">
          trackingTimedActionExistsJs(name) 
        </codeblock> </p> </li> 
      <li id="li_D77125DB2324460B911B37A56462801D"> <p><b>Returns</b>: Bool </p> </li> 
      <li id="li_00AE4C4B8B754A0ABDEB33261DD168A6"> <p><b>Parameters</b>: </p> <p>  </p>
       <table id="table_982656774660432E94227FE0925F62A1">  
       </table> </li> 
      <li id="li_6F493E2EEA2D4112A06C9F3E2D247B49"> <p> <b>Example</b>: 
        <codeblock class="syntax c">
          var&amp;nbsp;actionExists&amp;nbsp;=&amp;nbsp;ADBMobile.trackTimedActionExistsJs(‘level1’); 
        </codeblock> </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trackingIdentifier </td> 
   <td colname="col2"> <p>Returns the automatically generated visitor identifier. </p> <p>This is an app-specific unique visitor ID that is generated by Adobe’s servers. If Adobe's servers cannot be reached at the time of generation, the ID is generated by using Apple's CFUUID. The value is generated at the initial launch and is stored and used from that point. This ID is preserved between app upgrades, is saved and restored during the standard application back up process, and is removed when the app is uninstalled. </p> <p> <p>Tip:  If your app upgrades from the Experience Cloud 3.x to 4.x SDK, the previous custom or automatically generated visitor ID is retrieved and stored as the custom user identifier. This preserves visitor data between SDK upgrades. For new installations on the 4.x SDK, the user identifier is <span class="codeph"> nil </span>, and the tracking identifier is used. For more information, see the <span class="codeph"> userIdentifier </span> row below. </p> </p> <p> 
     <ul id="ul_4B92F545713E4A7E95D0C0E96281B6A9"> 
      <li id="li_0DAFAF59F0004394981FB0F1406F9563"> <p><b>Syntax</b>: 
        <codeblock class="syntax c">
          trackingIdentifier() 
        </codeblock> </p> </li> 
      <li id="li_84A9D7B67D6A4D429E4228BE17A11CB2"> <p><b>Returns</b>: String </p> </li> 
      <li id="li_903905949CAA49F1B4AED3C4D43ADB5F"> <p><b>Parameters</b>: None </p> </li> 
      <li id="li_8710CE6551B343AAA776F094E524F190"> <p> <b>Example</b>: 
        <codeblock class="syntax c">
          var&amp;nbsp;trackingId&amp;nbsp;=&amp;nbsp;ADBMobile.trackingIdentifier(); 
        </codeblock> </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trackingSendQueuedHits </td> 
   <td colname="col2"> <p>Forces the library to send all hits in the offline queue no matter how many are currently queued. </p> <p> 
     <ul id="ul_ACFA32ACD2BA4FA2A07BB9FBC6B0D4CE"> 
      <li id="li_1C96B1A5F740478EB6554F4DCC9D910F"> <p><b>Syntax</b>: 
        <codeblock class="syntax c">
          trackingSendQueuedHits() 
        </codeblock> </p> </li> 
      <li id="li_59A495604E384480ADA923066E4164AF"> <p><b>Returns</b>: N/A </p> </li> 
      <li id="li_A9007854437F4A6BA6D093EEE2FF487B"> <p><b>Parameters</b>: None </p> </li> 
      <li id="li_C09FC2E1F68144CBA0FC4618CD0B0EE9"> <p> <b>Example</b>: 
        <codeblock class="syntax c">
          ADBMobile.trackingSendQueuedHits();
        </codeblock> </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trackingClearQueue </td> 
   <td colname="col2"> <p>Clears all hits from the offline queue. </p> <p> 
     <ul id="ul_080E7BAC0AB74E67BD4A6FB330341749"> 
      <li id="li_313C637638444EE5AD360AF63FF7D839"> <p><b>Syntax</b>: 
        <codeblock class="syntax c">
          trackingClearQueue() 
        </codeblock> </p> </li> 
      <li id="li_AF91B5A557704CEEB11E950634260695"> <p><b>Returns</b>: N/A </p> </li> 
      <li id="li_95912889D6E84B57AAE68C2F2B1225A9"> <p><b>Parameters</b>: None </p> </li> 
      <li id="li_9E50CC71FCF942F78BFAF15DBC7B85F3"> <p> <b>Example</b>: 
        <codeblock class="syntax c">
          ADBMobile.trackingClearQueue(); 
        </codeblock> </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trackingGetQueueSize </td> 
   <td colname="col2"> <p>Retrieves the number of hits currently in the offline queue. </p> <p> 
     <ul id="ul_03A89A02E63B4DE0869A6CEDD3F65411"> 
      <li id="li_27A042DFAD754004A7496831D33213CB"> <p><b>Syntax</b>: 
        <codeblock class="syntax c">
          trackingGetQueueSize() 
        </codeblock> </p> </li> 
      <li id="li_3572E81F62E14E57B697D97D24E00A49"> <p><b>Returns</b>: Number </p> </li> 
      <li id="li_612F255D512448DFA60343E54786B2E6"> <p><b>Parameters</b>: None </p> </li> 
      <li id="li_7B9F95EEF92D460FADD805A3BF614528"> <p> <b>Example</b>: 
        <codeblock class="syntax c">
          var&nbsp;queueSize&nbsp;=&nbsp;ADBMobile.trackingGetQueueSize();
        </codeblock> </p> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Audience Manager Methods {#section_0155C4DF04644EDAAF6159C420A158DE}

<table id="table_D5671FC9017B4FAE8C3D9ABB7C176385"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Method </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> audienceVisitorProfile </td> 
   <td colname="col2"> <p>Returns the visitor profile that was most recently obtained. </p> <p>Returns <span class="codeph"> null </span> if no signal has been submitted yet. The visitor profile is saved in <span class="filepath"> NSUserDefaults </span> for easy access across multiple launches of your app. </p> <p> 
     <ul id="ul_072C97BCBCF34A869274D3F81541C0C8"> 
      <li id="li_7CFDAA51F2734DD8BE2CE6823B90086F"> <p><b>Syntax</b>: 
        <codeblock class="syntax c">
          audienceVisitorProfile() 
        </codeblock> </p> </li> 
      <li id="li_F46FBB37F692478D86937700B3D06897"> <p><b>Returns</b>: Object </p> </li> 
      <li id="li_6C0BB405D5414E86B7F2191B83A3999A"> <p><b>Parameters</b>: None </p> </li> 
      <li id="li_A636BB2D06464E1982D3E77828B80AA4"> <p> <b>Example</b>: </p> 
       <codeblock class="syntax c">
         var&amp;nbsp;profile&amp;nbsp;=&amp;nbsp;ADBMobile.audienceVisitorProfile(); 
       </codeblock> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> audienceDpid </td> 
   <td colname="col2"> <p>Returns the current DPID. </p> <p> 
     <ul id="ul_A6723C586487480FB48B181FD6568196"> 
      <li id="li_15B2DFC4E01B4DAD8BB71EE51E431377"> <p><b>Syntax</b>: </p> 
       <codeblock class="syntax c">
         audienceDpid() 
       </codeblock> </li> 
      <li id="li_64D366D1B4414D9E996F4B48BD2D526F"> <p><b>Returns</b>: String </p> </li> 
      <li id="li_0C3FA3F818E64E3383A8F118222360BF"> <p><b>Parameters</b>: None </p> </li> 
      <li id="li_E9E35CA0FE624A4B8029567CAAD926C6"> <p> <b>Example</b>: </p> 
       <codeblock class="syntax c">
         var&amp;nbsp;dpid&amp;nbsp;=&amp;nbsp;ADBMobile.audienceDpid(); 
       </codeblock> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> audienceDpuuid </td> 
   <td colname="col2"> <p>Returns the current DPUUID. </p> <p> 
     <ul id="ul_2931446EADFD4900B32B517F9A87009A"> 
      <li id="li_7C6A8F6A7B804D20979520507E3F8353"> <p><b>Syntax:</b> </p> 
       <codeblock class="syntax c">
         audienceDpuuid() 
       </codeblock> </li> 
      <li id="li_78916BE104C844CDBD56B19444F30383"> <p><b>Returns</b>: String </p> </li> 
      <li id="li_233642FE1F234467A74244011013D18E"> <p><b>Parameters</b>: None </p> </li> 
      <li id="li_06AA7EBA5B7442619A2F7D2557693BBB"> <p> <b>Example</b>: </p> 
       <codeblock class="syntax c">
         var&nbsp;dpuuid&nbsp;=&nbsp;ADBMobile.audienceDpuuid();
       </codeblock> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> audienceSetDpidDpuuid </td> 
   <td colname="col2"> <p>Sets the <span class="codeph"> dpid </span> and <span class="codeph"> dpuuid </span>, and if they are set, they are sent with each signal. </p> <p> 
     <ul id="ul_2085879BA4154C84B3D145283E759E1D"> 
      <li id="li_B1DF802CB92F416CB5ACFBAFBB1E9157"> <p><b>Syntax</b>: 
        <codeblock class="syntax c">
          audienceSetDpidDpuuid(dpid,&amp;nbsp;dpuuid) 
        </codeblock> </p> </li> 
      <li id="li_83B9E5E020D54304AFB88047F3C1CAB1"> <p><b>Returns</b>: N/A </p> </li> 
      <li id="li_5226A3102759415A943EA8B8E437676E"> <p><b>Parameters</b>: </p> <p>  </p>
       <table id="table_B0A251CDEEEA470AAAB0EC3128ED0663">  
       </table> </li> 
      <li id="li_039FDC6661CB47AFAE78B2B67C4053AE"> <p> <b>Example</b>: 
        <codeblock class="syntax c">
          ADBMobile.audienceSetDpidDpuuid(‘myDpid’,&amp;nbsp;‘userDpuuid’); 
        </codeblock> </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> audienceSignalWithDataJsCallback </td> 
   <td colname="col2"> <p>Sends Audience Manager a signal with traits and gets the matching segments that are returned in a callback function. </p> <p> 
     <ul id="ul_7D32D7DBC647483CACB7FCA581F99B25"> 
      <li id="li_4679EDEB8FAC4B7DAB0AD909EA059F95"> <p><b>Syntax</b>: </p> 
       <codeblock class="syntax c">
         audienceSignalWithDataJsCallback(traits&amp;nbsp;[,&amp;nbsp;callback]) 
       </codeblock> </li> 
      <li id="li_7801DC61F5AF4A4BB3033A1CA1009928"> <p><b>Parameters</b>: </p> <p>  </p>
       <table id="table_D14A6B0C4D0C49668E0E6442D4042259">  
       </table> </li> 
      <li id="li_6FF5341F7787444D821A1A6475F39797"> <p> <b>Example</b>: 
        <codeblock class="syntax c">
          ADBMobile.audienceSignalWithDataJsCallback({‘trait’:’something’},&nbsp;function(profile)&nbsp;{&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;//&nbsp;do&nbsp;something&nbsp;with&nbsp;the&nbsp;user’s&nbsp;segments&nbsp;found&nbsp;in&nbsp;profile&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}); 
        </codeblock> </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> audienceReset </td> 
   <td colname="col2"> <p>Resets the Audience Manager UUID and purges the current visitor profile. </p> <p> 
     <ul id="ul_E5E1282096B14B93B407769B7804D689"> 
      <li id="li_3FEDCBBCFA44492BAD75243E27F5EDE7"> <p><b>Syntax:</b>: 
        <codeblock class="syntax c">
          audienceReset() 
        </codeblock> </p> </li> 
      <li id="li_27663936170E4148B55A9FEA10D8CFB0"> <p><b>Returns</b>: N/A </p> </li> 
      <li id="li_416FB2E8563045FE8B54A14D15479A70"> <p><b>Parameters</b>: None </p> </li> 
      <li id="li_A8A74ABFC8AD43F68C78BA49E978BA15"> <p> <b>Example</b>: 
        <codeblock class="syntax c">
          ADBMobile.audienceReset(); 
        </codeblock> </p> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## ID Service Methods {#section_BEB6DA612EA4423FB354B65ECC941335}

<table id="table_37452471A2454A1580F20E71F0BBF016"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Method </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> visitorMarketingCloudID </td> 
   <td colname="col2"> <p>Retrieves the Experience Cloud ID from the ID service. </p> <p> 
     <ul id="ul_1D3F035C09AA4979837ED85FEC3DEE99"> 
      <li id="li_4D511019CB0B4C65BFCDB34A13E92285"> <p><b>Syntax:</b> 
        <codeblock class="syntax c">
          visitorMarketingCloudID() 
        </codeblock> </p> </li> 
      <li id="li_3CCD61CD1EF54A44BA6FE6BD005DE48A"> <p><b>Returns</b>: String </p> </li> 
      <li id="li_8E3B6EEB46AF4288BD100D2DC9689809"> <p><b>Parameters</b>: None </p> </li> 
      <li id="li_D6F5AA5CF72048C58244A443F28B8BB8"> <p> <b>Example</b>: 
        <codeblock class="syntax c">
          var&amp;nbsp;mcid&amp;nbsp;=&amp;nbsp;ADBMobile.visitorMarketingCloudID(); 
        </codeblock> </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> visitorSyncIdentifiers </td> 
   <td colname="col2"> <p>In addition to the Experience Cloud ID, you can set additional customer IDs to be associated with each visitor. The Visitor API accepts multiple Customer IDs for the same visitor, with a customer type identifier to separate the scope of the different customer IDs. This method corresponds to <span class="filepath"> setCustomerIDs </span> in the JavaScript library. </p> <p> 
     <ul id="ul_F16A7ADC1A5946FFB6DD2DB4FA508E45"> 
      <li id="li_84E1F1FC1C16459990478CA16600F348"> <p><b>Syntax</b>: 
        <codeblock class="syntax c">
          visitorSyncIdentifiers(identifiers) 
        </codeblock> </p> </li> 
      <li id="li_7146D932519C453C831F3A7EC7552767"> <p><b>Returns</b>: N/A </p> </li> 
      <li id="li_AD2737FA90D14459AA52B07E41C7BC39"> <p><b>Parameters:</b> </p> <p>  </p>
       <table id="table_EC2F88D543EF44A4BA2A5C434AC6D26C">  
       </table> </li> 
      <li id="li_3A600E5A64904684A0ACAA26604BED55"> <p> <b>Example</b>: 
        <codeblock class="syntax c">
          ADBMobile.visitorSyncIdentifiers({‘idType’:’idValue’}); 
        </codeblock> </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> visitorSyncIdentifiersAuthenticationState </td> 
   <td colname="col2"> <p> Synchronizes the provided identifiers to the ID service. </p> <p> 
     <ul id="ul_638172BE3D064F08B9B7F23516DA610F"> 
      <li id="li_D1DD1D706FF64830A0D8E2A1904893E8"> <p><b>Syntax</b>: </p> 
       <codeblock class="syntax c">
         visitorSyncIdentifiersAuthenticationState(identifiers,&amp;nbsp;authState) 
       </codeblock> </li> 
      <li id="li_58DF06F855DC4208A4B187561D224D86"> <p><b>Returns</b>: N/A </p> </li> 
      <li id="li_4B546B12B1594E56AEA89D4D1B804AB4"> <p><b>Parameters</b>: </p> <p>  </p>
       <table id="table_035F8CC847934B9D9A30FA25505D5E74">  
       </table> </li> 
      <li id="li_853E658C7BDC41758793846200E270C0"> <p> <b>Example</b>: 
        <codeblock class="syntax c">
          ADBMobile.visitorSyncIdentifiersAuthenticationState({'myIdType':'valueForUser'},&amp;nbsp;ADBMobileVisitorAuthenticationStateLoggedOut); 
        </codeblock> </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> visitorSyncIdentifierWithTypeIdentifierAuthenticationState </td> 
   <td colname="col2"> <p> Synchronizes the provided identifier type and value to the ID service. </p> <p> 
     <ul id="ul_80D28A47C277486FA0E921024C056BD5"> 
      <li id="li_ADEA6CAE316E4090AF17F4438B744B04"> <p><b>Syntax</b>: 
        <codeblock class="syntax c">
          visitorSyncIdentifierWithTypeIdentifierAuthenticationState(idType,&amp;nbsp;identifier,&amp;nbsp;authState) 
        </codeblock> </p> </li> 
      <li id="li_06107B27AB35499E8C8E2FCE0BDBEBED"> <p><b>Returns</b>: N/A </p> </li> 
      <li id="li_7406351A83C24CA78919BB0FA4D424B0"> <p><b>Parameters</b>: </p> <p>  </p>
       <table id="table_DF42EAE30B604324B8E5E007BA6C8D30">  
       </table> </li> 
      <li id="li_70E17AC056D94B7ABCAF7ED8A90690F3"> <p> <b>Example:</b> 
        <codeblock class="syntax c">
          ADBMobile.visitorSyncIdentifierWithTypeIdentifierAuthenticationState('myIdType',&amp;nbsp;'valueForUser',&amp;nbsp;ADBMobileVisitorAuthenticationStateAuthenticated); 
        </codeblock> </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> visitorGetIDsJs </td> 
   <td colname="col2"> <p>Retrieves an array of read-only <span class="codeph"> ADBVisitorID </span> objects. The following code sample is an example of a VisitorID object: </p> 
    <codeblock>
      {&nbsp;&nbsp;&nbsp;&nbsp;idType:&nbsp;"abc",&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;authenticationState:&nbsp;1,&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;identifier:&nbsp;"123"} 
    </codeblock> <p> <b>Syntax</b>: </p> 
    <codeblock class="syntax c">
      visitorGetIDsJs() 
    </codeblock> <p><b>Returns</b>: Array[Object] </p> <p><b>Parameters</b>: None </p> <p> <b>Example</b>: </p> 
    <codeblock class="syntax c">
      var&amp;nbsp;myVisitorIds&amp;nbsp;=&amp;nbsp;ADBMobile.visitorGetIDsJs(); 
    </codeblock> </td> 
  </tr> 
 </tbody> 
</table>

## Target Methods {#section_F9F7EC2B9B7C41AFBCA2458F9F138634}

<table id="table_D93105E884F249ADBABA513E6E600931"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Method </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> targetThirdPartyID </p> </td> 
   <td colname="col2"> <p> Returns the third-party ID. </p> <p> 
     <ul id="ul_E665EC01B14E4AB78A02567ED190D076"> 
      <li id="li_33AE11DC237B4D83B68169FAAE19E0F7"> <p><b>Syntax</b>: </p> 
       <codeblock class="syntax c">
         targetThirdPartyID() 
       </codeblock> </li> 
      <li id="li_7A5839C0B7A746108C4B68D51EE98A6C"> <p><b>Returns</b>: String </p> </li> 
      <li id="li_3245FB96A8B94ACB8901783F78F69E6C"> <p><b>Parameters</b>: None </p> </li> 
      <li id="li_CABFAACD1226409F97CED87C7337BC48"> <p> <b>Example</b>: </p> 
       <codeblock class="syntax c">
         var&amp;nbsp;thirdPartyID&amp;nbsp;=&amp;nbsp;ADBMobile.targetThirdPartyID(); 
       </codeblock> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> targetSetThirdPartyID </p> </td> 
   <td colname="col2"> <p> Sets the third-party ID. </p> <p> 
     <ul id="ul_A0AB79D88B5C406F81E21AF2EDBE2E71"> 
      <li id="li_6BF95212C56F458AA82C1E02BAFEAA6E"> <p><b>Syntax</b>: 
        <codeblock class="syntax c">
          targetSetThirdPartyID(thirdPartyID) 
        </codeblock> </p> </li> 
      <li id="li_47E53C489A0446958EB093766D5C9809"> <p><b>Returns</b>: N/A </p> </li> 
      <li id="li_9C1BFA58BCC64476B226C51FB669BE38"> <p><b>Parameters</b>: </p> <p>  </p>
       <table id="table_CFF69D50952D4BA393EE9D491ED072F6">  
       </table> </li> 
      <li id="li_5A06A75B040549D899ADEFE4BFB34B80"> <p> <b>Example</b>: 
        <codeblock class="syntax c">
          ADBMobile.targetSetThirdPartyID(‘thirdPartyID’); 
        </codeblock> </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> targetPcID </p> </td> 
   <td colname="col2"> <p> Returns the PcID. </p> <p> 
     <ul id="ul_59E9262E02BE47B086AAEB342A83C1EF"> 
      <li id="li_68B1646EC19D4DCA8512CDCBDB2045E6"> <p><b>Syntax</b>: 
        <codeblock class="syntax c">
          targetPcID() 
        </codeblock> </p> </li> 
      <li id="li_5B7624D4CE54417B97BAC9348547245E"> <p><b>Returns</b>: String </p> </li> 
      <li id="li_BA9424ED2161472EB5B62D3D7FD73465"> <p><b>Parameters</b>: None </p> </li> 
      <li id="li_CC2AAEAB3E1D482B8588B7E0E111ABC7"> <p> <b>Example</b>: </p> </li> 
     </ul> </p> 
    <codeblock class="syntax c">
      var&amp;nbsp;pcID&amp;nbsp;=&amp;nbsp;ADBMobile.targetPcID(); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> targetSessionID </p> </td> 
   <td colname="col2"> <p> Returns the session ID. </p> <p> 
     <ul id="ul_ACEAA15E291C45DFAC40DDC129478102"> 
      <li id="li_A7E04E8C22A74B6FBE0645D1C5D5D289"> <p><b>Syntax</b>: 
        <codeblock class="syntax c">
          targetSessionID() 
        </codeblock> </p> </li> 
      <li id="li_DCED997628474AF194E1AEAD0C650F2B"> <p><b>Returns</b>: String </p> </li> 
      <li id="li_F15D9EC7527740389F1ADDAFDE4C428A"> <p><b>Parameters</b>: None </p> </li> 
      <li id="li_CF3D9B3F96924B4293CD96BDCCB47E9A"> <p> <b>Example</b>: 
        <codeblock class="syntax c">
          var&amp;nbsp;sessionID&amp;nbsp;=&amp;nbsp;ADBMobile.targetSessionID(); 
        </codeblock> </p> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>
