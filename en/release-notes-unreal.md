## Game > Gamebase > Release Notes > Unreal

### 2.33.1 (2022. 02. 22.)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v2.33.1/GamebaseSDK-Unreal.zip)

#### Bug Fixes
* Fixed an error that occurred when running the iOS build.

### 2.33.0 (2022.01.25)

[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v2.33.0/GamebaseSDK-Unreal.zip)

#### Added Features
* Added a 'purchase abuse automatic release' function.
    * [Game > Gamebase > Unreal SDK User Guide > Authentication > GraceBan](./unreal-authentication/#graceban)
    * The purchase abuse automatic release function allows users who should be banned due to purchase abuse automatic lockdown to be banned after ban suspension status.
    * When a user is in ban suspension status, if the user satisfies all of the release conditions within the set period of time, the user will be able to play normally.
    * If the user does not satisfy the conditions within the period, the user is banned.
* Games that use the purchase abuse automatic release function must always check the value of AuthToken.member.graceBanInfo API after login. If a valid GraceBanInfo object that is not null is returned, the user must be informed of the ban release conditions, period, etc.
    * In-game access control for users who are in ban suspension status must be handled by the game.
* Added a new forced mapping API, which removes the inconvenience of having to try IdP login once more when performing forced mapping.
    * [Game > Gamebase > Unreal SDK User Guide > Authentication > Mapping > Add Mapping Forcibly](./unreal-authentication/#add-mapping-forcibly)
* Added an API that allows you to log in to the corresponding account when an AUTH_ADD_MAPPING_ALREADY_MAPPED_TO_OTHER_MEMBER(3302) error occurs after calling Gamebase.AddMapping().
    * [Game > Gamebase > Unreal SDK User Guide > Authentication > Mapping > Change Login with ForcingMappingTicket](./unreal-authentication/#change-login-with-forcingmappingticket)
* Added the **GamebaseEventCategory::ServerPushAppKickOutMessageReceived** type to GamebaseEventCategory of GamebaseEventHandler.
    * For information on how to use this event, refer to the following document.
    * [Game > Gamebase > Unreal SDK User Guide > ETC > Additional Features > Gamebase Event Handler > Server Push](./unreal-etc/#server-push)
* Added the **GamebaseEventCategory::LoggedOut** type to GamebaseEventCategory of GamebaseEventHandler.
    * This type is applied when login is required because the Gamebase Access Token has expired.
    * [Game > Gamebase > Unreal SDK User Guide > ETC > Additional Features > Gamebase Event Handler > Logged Out](./unreal-etc/#logged-out)
* Added a new API that allows you to change settings of the common terms and conditions window.
    * [Game > Gamebase > Unreal SDK User Guide > UI > Terms > showTermsView](./unreal-ui/#showtermsview)

#### Feature Updates
* Added and changed error codes
    * Changed the error code mapped to the GamebaseErrorCode::UNKNOWN_ERROR error from 999 to 9999.
    * Newly added the GamebaseErrorCode::SOCKET_UNKNOWN_ERROR error mapped to the error code 999.
    
#### Platform-specific Changes
* [Gamebase Android SDK 2.33.0](./release-notes-android/#2330-20220125)
* [Gamebase iOS SDK 2.33.0](./release-notes-ios/#2330-20220125)

### 2.26.1 (2021.11.23)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v2.26.1/GamebaseSDK-Unreal.zip)

#### Bug Fixes
* Fixed a typo of Finnish language on GamebaseDisplayLanguageCode
    * Finish → Finnish

### 2.26.0 (2021.09.28)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v2.26.0/GamebaseSDK-Unreal.zip)

#### Added Features
* Added a common Terms and Conditions feature
	* Added an API that opens the Terms and Conditions webview
	* Added an API that views the Terms and Conditions list and agreement status per user
	* Added an API that stores the user agreement data on the Gamebase server

#### Feature Updates
* Changed to display the Customer Center without login if the Customer Center type is TOAST organization product (Online Contact).
* Changed the internal launching URL
* Removed Android multidex-related setting from Gamebase

### 2.19.2 (2021.06.29)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v2.19.2/GamebaseSDK-Unreal.zip)

#### Bug Fixes
* Fixed a crash that occurs when the Close button is clicked while onEventCallback is not registered when calling the Image Notification ShowImageNotices API
* Android setting tools -  Fixed a problem where Enable Hangame and Enable Weibo did not work properly

### 2.19.1 (2021.02.09)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v2.19.1/GamebaseSDK-Unreal.zip)

#### Bug Fixes
* Fixed a compile error caused by files excluded during Unity Build

### 2.19.0 (2021.01.26)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v2.19.0/GamebaseSDK-Unreal.zip)

#### More Features
* (Unreal) SDK distribution: accumulated features from 2.16.0 to 2.19.0 reflected
	* [Android Settings Tool](https://docs.toast.com/en/Game/Gamebase/en/unreal-started/#android-settings) provided: please use this settings tool rather than modifying the Gamebase_Android_UPL.xml file.
	* Customer Center feature added	
	* Authentication for Hangame, Weibo added
	* Galaxy Store added
	* Localized product information added in the Paid Item information field: localizedTitle, localizedDescription
	* Android settings tool provided
	* Unreal 4.26 supported

### ### 2.15.0 (October 27, 2020)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v2.15.0/GamebaseSDK-Unreal.zip)

#### More Features
- Added the Unreal SDK feature: SDK 2.15.0
    - Added GamebaseEventHandler that integrates all existing event systems
        * It includes the ServerPush and Observer features and checks promotion transaction event and push event.
    * Added API
    	* Added an API that can be used to send a transaction request with product ID, enter additional information (UserPayload), and check them after the transaction is complete
    	* Display image notification: showImageNotices
    	* Check the Push token information: queryTokenInfo
    * Added a feature that allows foreground apps to receive push notifications using the NotificationOption setting if push token is registered.
    * Added the WebViewConfiguration contentMode setting

#### Feature Updates
* [SDK] 2.15.0
    * (Unreal) TOAST SDK update: Android(0.23.0), iOS(0.26.0), Unity(0.21.0)  

#### Bug Fixes
* [SDK] 2.15.0    
    * (Unreal) Fixed an issue where the ProGuard declaration was missing in the transaction module

### ### 2.9.1 (August 25, 2020)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v2.9.1/GamebaseSDK-Unreal.zip)

#### More Features
* [SDK] 2.9.1
    * (Unreal) Supports Unreal 4.22 ~ 4.25
    * (Unreal) Supports PLCrashReporter Issue: [Guide](http://docs.toast.com/en/Game/Gamebase/en/unreal-started/#ios-settings)

#### Feature Updates
* [SDK] 2.9.1
    * (Unreal) Updated Gamebase SDK version for iOS within iOS Plugin (2.9.1)
    * (Unreal) Fixed the missing part of UObject referencing 

### 2.9.0 (May 12, 2020)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v2.9.0/GamebaseSDK-Unreal.zip)

#### More Features
* [SDK] 2.9.0
	* (Unreal) Newly released SDK