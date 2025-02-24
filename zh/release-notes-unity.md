## Game > Gamebase > Release Notes > Unity

### 2.39.0 (2022. 05. 10.)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v2.39.0/GamebaseSDK-Unity.zip)

#### 기능 추가
* 외부 SDK 업데이트: TOAST Unity SDK(0.25.4)

#### 버그 수정
* 초기화 전에 GetLaunchingInformations() API를 호출 시 JsonException이 발생하지 않도록 수정되었습니다.

#### 플랫폼별 변경 사항
* [Gamebase Android SDK 2.39.0](./release-notes-android/#2390-20220510)
* [Gamebase iOS SDK 2.39.0](./release-notes-ios/#2390-20220510)

### 2.38.0 (2022. 05. 03.)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v2.38.0/GamebaseSDK-Unity.zip)

#### 기능 추가
* 외부 SDK 업데이트: TOAST Unity SDK(0.25.3)

#### 기능 개선/변경
* Display Language의 중국어 번체(zh-TW) 언어셋에서 어색한 문장이 수정되었습니다.

#### 버그 수정
* (Android) API Level 24 미만에서 특정 API 호출 시 오류가 발생하지 않도록 수정되었습니다.
    * Gamebase.Purchase.RequestActivatedPurchases()
    * Gamebase.Purchase.RequestItemListOfNotConsumed()

#### 플랫폼별 변경 사항
* [Gamebase Android SDK 2.38.0](./release-notes-android/#2380-20220503)
* [Gamebase iOS SDK 2.38.0](./release-notes-ios/#2380-20220503)

### 2.37.0 (2022. 04. 26.)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v2.37.0/GamebaseSDK-Unity.zip)

#### 기능 추가
* 고객센터 URL 뒤에 파라미터를 추가할 수 있도록 다음 필드가 추가되었습니다.
    * GamebaseRequest.Contact.Configuration.additionalParameters

#### 플랫폼별 변경 사항
* [Gamebase Android SDK 2.37.0](./release-notes-android/#2370-20220426)
* [Gamebase iOS SDK 2.37.0](./release-notes-ios/#2370-20220426)

### 2.36.0 (2022. 04. 12.)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v2.36.0/GamebaseSDK-Unity.zip)

#### 기능 추가
* 외부 SDK 업데이트: TOAST Unity SDK(0.25.2)
* 결제 시 프로모션 여부를 알 수 있는 isPromotion 필드가 추가되었습니다.
    * GamebaseResponse.Purchase.PurchasableReceipt.isPromotion
* 결제 시 테스트 결제 여부를 알 수 있는 isTestPurchase 필드가 추가되었습니다.
    * GamebaseResponse.Purchase.PurchasableReceipt.isTestPurchase

#### 버그 수정
* 디바이스가 특정 문화권으로 설정되었을 때 결제 상품 가격 정보가 0으로 입력되는 오류가 수정되었습니다.
* (iOS) Push 알림 클릭 시 딥 링크가 동작하지 않는 이슈 수정되었습니다.
* (iOS) 프로젝트의 opientation이 Auto Rotation으로 설정되어 있고, 프로젝트 첫 씬에 포함된 MonoBehaviour의 Awake에서 Gamebase API 호출 시 웹뷰 등의 UI 출력이 정상적으로 동작하지 않는 오류가 수정되었습니다.

#### 플랫폼별 변경 사항
* [Gamebase Android SDK 2.36.0](./release-notes-android/#2360-20220412)
* [Gamebase iOS SDK 2.36.0](./release-notes-ios/#2360-20220412)

### 2.35.0 (2022. 03. 29.)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v2.35.0/GamebaseSDK-Unity.zip)

#### 기능 추가
* 외부 SDK 업데이트: TOAST Unity SDK(0.25.1)
* 약관이 표시되었는지 여부를 알 수 있는 API가 추가되었습니다.
    * Gamebase.Terms.IsShowingTermsView()
* 웹뷰에서 네비게이션 바를 숨길 수 있는 옵션이 추가되었습니다.
    * GamebaseRequest.Webview.GamebaseWebViewConfiguration.isNavigationBarVisible
* (Android) 웹뷰에서 폰트 사이즈를 고정할 수 있는 옵션이 추가되었습니다
    * GamebaseRequest.Webview.GamebaseWebViewConfiguration.enableFixedFontSize
* (Android) 약관 창에서 폰트 사이즈를 고정할 수 있는 옵션이 추가되었습니다
    * GamebaseRequest.Terms.GamebaseTermsConfiguration.enableFixedFontSize
* Setting Tool
    * (Android) Amazon 스토어가 추가되었습니다.
    * (Android) Huawei 스토어가 추가되었습니다.

#### 플랫폼별 변경 사항
* [Gamebase Android SDK 2.35.0](./release-notes-android/#2350-20220329)
* [Gamebase iOS SDK 2.35.0](./release-notes-ios/#2350-20220329)

### 2.34.1 (2022. 03. 15.)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v2.34.1/GamebaseSDK-Unity.zip)

#### 기능 추가
* 단말기에서 알림을 허용했는지 여부를 알 수 있는 API가 추가되었습니다.
    * Gamebase.Push.QueryNotificationAllowed

#### 버그 수정
* iOS에서 GamebaseWebViewConfiguration의 isBackButtonVisible 설정이 적용되지 않는 오류가 수정되었습니다.

#### 플랫폼별 변경 사항
* [Gamebase Android SDK 2.34.0](./release-notes-android/#2340-20220222)
* [Gamebase iOS SDK 2.34.1](./release-notes-ios/#2341-20220315)

### 2.34.0 (2022. 02. 22.)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v2.34.0/GamebaseSDK-Unity.zip)

#### 添加功能
* 添加了当调用共同条款API后可确认条款UI是否被显示的VO类。
    * **GamebaseResponse.Terms.ShowTermsViewResult**

#### 改善/更改功能
* 由于在Gamebase控制台中注册Kickout时可以设置是否显示kickout弹窗，因此以下字段已被deprecated。
    * **GamebaseConfiguration.enableKickoutPopup**
    
#### 各平台更改事项 
* [Gamebase Android SDK 2.34.0](./release-notes-android/#2340-20220222)
* [Gamebase iOS SDK 2.34.0](./release-notes-ios/#2340-20220222)

### 2.33.0 (2022.01.25)

[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v2.33.0/GamebaseSDK-Unity.zip)

#### 添加功能
* 添加了可更改共同条款窗设置的新API。
    * [Game > Gamebase > Unity SDK使用指南 > UI > Terms > showTermsView](./unity-ui/#showtermsview)

#### 改善/更改功能
* 添加或更改错误代码
    * GamebaseErrorCode.UNKNOWN_ERROR的错误代码从999更改为9999。
    * 添加了映射到999错误代码的GamebaseErrorCode.SOCKET_UNKNOWN_ERROR错误。
    
#### 各平台变更项目
* [Gamebase Android SDK 2.33.0](./release-notes-android/#2330-20220125)
* [Gamebase iOS SDK 2.33.0](./release-notes-ios/#2330-20220125)

### 2.32.0 (2021.12.28)

[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v2.32.0/GamebaseSDK-Unity.zip)

#### 改善/修复功能
* 在GamebaseEventHandler的GamebaseEventCategory中添加了**GamebaseEventCategory.SERVER_PUSH_APP_KICKOUT_MESSAGE_RECEIVED**类型。
    * 关于此事件的适用方法，请参考如下指南。
    * [Game > Gamebase > Unity SDK使用指南 > ETC > Additional Features > Gamebase Event Handler > Server Push](./unity-etc/#server-push)
* 添加了当Gamebase Access Token过期，登录时需要启动的**GamebaseEventCategory.LOGGED_OUT** GamebaseEventHandler category。
    * [Game > Gamebase > Unity SDK使用指南 > ETC > Additional Features > Gamebase Event Handler > Logged Out](./unity-etc/#logged-out)

#### 各平台变更项目
* [Gamebase Android SDK 2.32.0](./release-notes-android/#2320-20211228)
* [Gamebase iOS SDK 2.32.0](./release-notes-ios/#2320-20211228)

### 2.31.0 (2021.12.14)

[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v2.31.0/GamebaseSDK-Unity.zip)

#### 改善/修复功能
* 外部SDK升级 : TOAST Unity SDK(0.25.0)
* 可以更改Standalone维护弹窗“是否显示维护时间”。 
* Setting Tool
    * 添加了Payco IDP。
    * 需要删除以前的SettingTool后重新进行设置。 

#### 各平台变更项目
* [Gamebase Android SDK 2.31.0](./release-notes-android/#2310-20211214)
* [Gamebase iOS SDK 2.31.0](./release-notes-ios/#2310-20211214)

### 2.30.0 (2021.11.23)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v2.30.0/GamebaseSDK-Unity.zip)

#### 添加功能
* 为了改善强制映射时需要再次尝试IdP登录的不便，添加了一个新的强制映射API。
    * [Game > Gamebase > Unity SDK使用指南 > 认证 > Mapping > Add Mapping Forcibly](./unity-authentication/#add-mapping-forcibly)
* 为了解决调用Gamebase.AddMapping()后出现AUTH_ADD_MAPPING_ALREADY_MAPPED_TO_OTHER_MEMBER(3302)错误的问题，添加了可将帐户转换为已有的帐户后登录的API。
    * [Game > Gamebase > Unity SDK使用指南 > 认证 > Mapping > Change Login with ForcingMappingTicket](./unity-authentication/#change-login-with-forcingmappingticket)

#### 各平台变更项目
* [Gamebase Android SDK 2.30.0](./release-notes-android/#2300-20211123)
* [Gamebase iOS SDK 2.30.0](./release-notes-ios/#2300-20211123)

### 2.29.0 (2021.11.09)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v2.29.0/GamebaseSDK-Unity.zip)

#### 改善/修复功能
* 外部SDK升级 : TOAST Unity SDK(0.23.5)
* Setting Tool
    * 发布了v2.0.0版本。
    * 需要先删除已有的SettingTool后再进行设置。
    * 关于修改的信息和使用方法，请参考以下指南。 
        * [Game > Gamebase > Unity SDK使用指南 > 开始 > Specification of Setting Tool](./unity-started/#specification-of-setting-tool)

#### 修改程序错误
* 修改了GamebaseDisplayLanguageCode芬兰语错误。 
    * Finish → Finnish

#### 各平台变更项目
* [Gamebase Android SDK 2.29.0](./release-notes-android/#2290-20211109)
* [Gamebase iOS SDK 2.29.0](./release-notes-ios/#2290-2021109)

### 2.28.1 (2021.10.26)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v2.28.1/GamebaseSDK-Unity.zip)

#### 修改程序错误
* 修改了未设置(Android) DisplayLanguage时，使用错误值进行设置的问题。
* 修改了在(Standalone)前帧需要较长时间时发生的Timeout错误。 

### 2.28.0 (2021.09.28)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v2.28.0/GamebaseSDK-Unity.zip)

#### 添加功能
* 添加Kakaogame认证
* ”结算Abusing自动解除”功能已被添加。 
    * [Game > Gamebase > Unity SDK使用指南 > 认证 > GraceBan](./unity-authentication/#graceban)
    * 结算Abusing自动解除功能是当存在需通过”结算Abusing自动制裁”来禁止使用的用户时，禁止这些用户的使用之前先提供预约时间的功能。
    * 如果为”预约禁用”状态，在设定的时期内满足解除条件，则可正常玩游戏。
    * 若在所定的时期内未能满足条件，则会被禁用。
* 登录使用结算Abusing自动解除功能的游戏后，始终要确认AuthToken.member.graceBanInfo API值，如果返还GraceBanInfo对象，而不返还null，要向相关用户通知禁用解除条件、时期等。
    * 当需要控制处于预约禁用状态的用户进入游戏时，要在游戏中进行处理。

#### 各平台项目变更
* [Gamebase Android SDK 2.28.0](./release-notes-android/#2280-20210928)
* [Gamebase iOS SDK 2.28.0](./release-notes-ios/#2280-20210928)  

### 2.27.1 (2021.09.14)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v2.27.1/GamebaseSDK-Unity.zip)

#### 改善/修复功能
* Display Language功能已被改善。
    * 默认语言代码为**en**，但经过改善已可适用Gamebase控制台中设置的默认语言。
        * [Game > Gamebase > 控制台使用指南 > 应用程序 > App > 语言设置](https://docs.toast.com/en/Game/Gamebase/en/oper-app/#language-settings)

#### 修改错误
* 已修改只用英语显示”未注册的游戏版本”错误弹窗的问题。 
* 已修改维护弹窗不显示汉语的错误。

#### 各平台变更项目
* [Gamebase Android SDK 2.27.1](./release-notes-android/#2271-20210914)
* [Gamebase iOS SDK 2.27.1](./release-notes-ios/#2271-20210914)

### 2.27.0 (2021.08.24)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v2.27.0/GamebaseSDK-Unity.zip)

#### 改善/修复功能
* 外部SDK升级 : TOAST Unity SDK(0.23.2)
* 添加ONE Store V16商店

#### 修改错误
* 在Unity SDK 2.25.0中删除不应添加的文件。 
    * 路径 : Assets/Gamebase/Toast/IAP/Plugins

### 2.26.0 (2021.08.10)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v2.26.0/GamebaseSDK-Unity.zip)

#### 改善/修复功能
* Display Language功能已被改善。
    * 在Display Language语言集中添加了汉语简体(zh-CN)、汉语繁体(zh-TW)及泰国语(th)。
* 调用showTermsView API后，可创建PushConfiguration对象的基准被更改为；
    * 修改前
        * 仅当在条款项目中存在**接收Push**项目时，才返还有效的PushConfiguration，而不返还null。
        * 如果用户拒绝在白天和夜间接收广告性Push，PushConfiguration.pushEnabled则会创建为false。
    * 修改后
        * 如果显示了条款UI，将返还有效的PushConfiguration，而不始终返还null。
        * ShowTermsView返还的PushConfiguration对象的pushEnabled值始终为true。
    * 未修改项目
        * 若因已同意条款，未显示条款UI时，PushConfiguration将会返还为null。

#### 修改错误
* 已修改因终端机的语言代码和Push控制台中的语言代码不一致，而导致未能正常设置Push语言的问题。

### 2.25.0 (2021.07.26)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v2.25.0/GamebaseSDK-Unity.zip)

#### Added Features
* Added a monthly payment limit feature
    * If the monthly payment limit is exceeded, the **PURCHASE_LIMIT_EXCEEDED(4007)** error occurs.

#### Feature Updates
* The existence of a PushConfiguration object is ensured in terms and conditions with Push notification items
    * Until now, the PushConfiguration created as a result of calling the Gamebase.Terms.ShowTermsView API was null if the user declines to receive Push notifications in the terms and conditions UI. However, it has been changed so that the PushConfiguration object is always returned if there are Push notification items in the terms and conditions.
    * When user rejects push notifications, the PushConfiguration object is created as (consent to push notifications = false, consent to advertisement push notifications = false, consent to push notifications for advertisements at night = false).
    * If there is no Push notification item in the terms and conditions, the PushConfiguration object is null.
* Changed the minimum supported version of Unity: 2018.4.0f1
* External SDK Update: TOAST Unity SDK(0.23.0)

### 2.24.0(2021.06.29)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v2.24.0/GamebaseSDK-Unity.zip)

#### Feature Updates
* Change the internal launch URL

### 2.23.0(2021.06.14)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v2.23.0/GamebaseSDK-Unity.zip)

#### Feature Updates
* External SDK Update: TOAST Unity SDK(0.22.1)
* Removed warnings from Unity 2020.2 or later
* Improved initialization speed in Standalone and Unity Editor

#### Bug Fixes
* Fixed a problem where the PushConfiguration result is not null when ShowTermsView API is called even after agreeing to the terms

### 2.22.0(2021.05.25)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v2.22.0/GamebaseSDK-Unity.zip)

#### Feature Updates
* Updated the external SDK: TOAST Unity SDK(0.22.0)

### 2.21.0(2021.04.13)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v2.21.0/GamebaseSDK-Unity.zip)

#### More Features
* Japanese authentication for Hangame added.	

### 2.20.0(2021.02.09)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v2.20.0/GamebaseSDK-Unity.zip)

#### More Features
* Common Terms and Conditions added
	* Added an API that opens the Terms and Conditions webview
	* Added an API that views the Terms and Conditions list and agreement status per user
	* Added an API that saves the user agreement data on the Gamebase server

#### Feature Updates
* Changed to display the Customer Center without login if the Customer Center type is TOAST organization product (Online Contact).
* Removed warning logs
* Updated CEF 2.1.2 for Standalone WebView
	* Fixed an issue where a crash occurs when the URL length is longer than 2,048
	* Changed the library path to improve PostProcessBuild when building in Unity 2019
	* Fixed an occasional error arising out of not initializing the string
	* Fixed a bug where the webview does not open again after moving to another scene while using the GameBase webview

### 2.19.0 (December 29, 2020)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v2.19.0/GamebaseSDK-Unity.zip)

#### More Features
* [SDK] 2.19.0
	* (Common) Weibo authentication added
	
#### Feature Updates
* [SDK] 2.19.0
	* (Common) Launching status code added: beta service (205)

#### Bug Fixes
* [SDK] 2.19.0
    * (Unity) WebSocket에서 재시도 시 OutOfMemoryException이 발생하는 문제 수정

### 2.18.2 (December 15, 2020)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v2.18.2/GamebaseSDK-Unity.zip)

#### More Features
* [SDK] 2.18.2
	* (Common) additionalURL field added for the case of a developer's own Customer Center being opened
	* (Common) Localized product information added in the transaction item information: localizedTitle, localizedDescription

#### Feature Updates
* [SDK] 2.18.2
    * (Common) TOAST SDK update: [Android(0.24.2)](https://docs.toast.com/zh/TOAST/zh/toast-sdk/release-notes-android/#0242-20201124), [iOS(0.27.1)](https://docs.toast.com/zh/TOAST/zh/toast-sdk/release-notes-ios/#0271-20201124), [Unity(0.21.3)](https://docs.toast.com/zh/TOAST/zh/toast-sdk/release-notes-unity/#0213-20201124)
	* (Android) External SDK update to resolve encryption logic security warnings: Payco Login SDK (1.5.3), Hangame ID SDK (1.3.2)
	* (Android) Tencent Push module removed
	* (Android) The deprecated function in Gamebase Android SDK 2.6.0 removed
		* GamebaseConfiguration.Builder.setFCMSenderId()
		* GamebaseConfiguration.Builder.setTencentAccessKey()
		* GamebaseConfiguration.Builder.setTencentAccessId()
	* (iOS) showWebView: Returns error when invalid URL is delivered, delivered URL is used as is without encoding
	* (iOS) Changed to run the custom scheme regardless of letter case
	* (Unity) The following fields of GamebaseRequest.GamebaseConfiguration class deprecated: zoneType, fcmSenderId

#### Bug Fixes
* [SDK] 2.18.2
    * (Android) Fixed the issue where WebView custom scheme does not run on a 5.0 - 6.0 OS device

### 2.18.0 (November 10, 2020)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v2.18.0/GamebaseSDK-Unity.zip)

#### More Features
* Added Galaxy Store: SDK 2.18.0

#### Feature Updates
* [SDK] 2.18.0
    * (Android) TOAST SDK update: [Android(0.24.1)](https://docs.toast.com/zh/TOAST/zh/toast-sdk/release-notes-android/#0240-20201027) - Apply GooglePlay Billing Library v.3.0.1
    * (Android) Added the response for WebView SSL security warnings
    * (iOS) Added API that supports the SceneDelegate of iOS 13 or higher

#### Bug Fixes  
* [SDK] 2.18.1
    * (Android) Fixed an issue where a crash would occur after a Google transaction is approved in 2.18.0

### 2.17.1 (October 27, 2020)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v2.17.1/GamebaseSDK-Unity.zip)

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
* [SDK] 2.17.1
    * (Unity) Supports Unity 2017.2.5

#### Bug Fixes  
* [SDK] 2.17.1
    * (Unity) Fixed an issue where the latter API would not work when the image notification API and web view API were called in turn.

### 2.17.0 (October 13, 2020 )
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v2.17.0/GamebaseSDK-Unity.zip)

```
Contact our Customer Center if you want to use the Hangame authentication.
```

#### More Features
* Added Hangame IdP authentication: SDK 2.17.0

#### Feature Updates
* [SDK] 2.17.0
	* (Common) Supports the download feature when a Customer Center attachment image is clicked
	* (Common) TOAST SDK update: Android(0.23.2), Unity(0.21.2)
	* (iOS) Changed the type of TCGBMember.regDate and TCGBMember.lastLoginDate to long long.
	* (iOS) Changed the logic so that the title can be displayed again after changing URL and title in a web view

#### Bug Fixes  
* [SDK] 2.17.0
	* (iOS) PAYCO authentication: Fixed an issue where the logout callback would not return when logout was called after lastLoggedInProvider login
* [SDK] 2.17.1
	* (Android) Fixed an issue where a crash would occur in the kotlinx-coroutine module when ImageNotice API is called in 2.17.0
	
### 2.16.0 (September 22, 2020)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v2.16.0/GamebaseSDK-Unity.zip)

#### More Features
* Added a feature to Customer Center
	* [SDK] 2.16.0
		* (Common) Added API (Gamebase.Contact.requestContactURL): Returns Customer Center URL
		* (Common) Added the ContactConfiguration parameter so userName can be configured for Customer Center API
		
### 2.15.0 (August 25, 2020)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v2.15.0/GamebaseSDK-Unity.zip)

```
Updated Google Billing Client in the Gamebase SDK 2.15.0 version. 

For 'gamebase-adapter-purchase-google', to upgrade a version below Gamebase SDK 2.15.0 to more than 2.15.0,  
set 'Requires Update' for 'Game Client Version' of the previous version.

This is because, in order to execute reprocessing when an error occurs during purchasing an item,  
you may encounter an issue during reprocessing if a different billing client version is applied to each of many devices.   
```

#### More Features
* [SDK] 2.15.0
    * (Common) Added feature, for push token registration, to allow the app to receive push alarms even under Foreground with the NotificationOption setting  
    * (Common) Added Push API: Check token information of a push (Gamebase.Push.queryTokenInfo API)

#### Feature Updates
* [SDK] 2.15.0
    * (Common) TOAST SDK Updates: Android(0.23.0), iOS(0.26.0), Unity(0.21.0)
    * (iOS) Added the null check logic for the payload of payment

### 2.14.0 (August 11, 2020)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v2.14.0/GamebaseSDK-Unity.zip)

#### Feature Updates
* [SDK] 2.14.0
    * (iOS) Removed Constant Value of PAYCO IdP: Due to rejections made on Apple inspections thanks to PAYCO character strings 
    * (iOS, Unity) Adde the contentMode setting for TCGBWebViewConfiguration

### 2.13.0 (July 28, 2020)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v2.13.0/GamebaseSDK-Unity.zip)

#### More Features
* [SDK] 2.13.0
    * (Unity) Standalone: Added Show Notice on Image API     

#### Feature Updates
* [SDK] 2.13.0
    * (Android) Modified the logic of calculating the percentage of popup image for notice on image 
    * (iOS) Authenticate Sign In With Apple: Supported for iOS 12 or lower 

#### Bug Fixes
* [SDK] 2.13.0
    * (Android) Fixed an issue in which the ANDROID_ACTIVITY_DESTROYED(31) error is returned for the close callback when an webview is closed 
    * (Android) Fixed error in which the ProGuard declaraction is missing from the payment module 

### 2.12.0 (July 14, 2020)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v2.12.0/GamebaseSDK-Unity.zip)

#### More Features
* Image Notices: Shows image popups within a game according to exposed period and priority order
    * [SDK] 2.12.0: Added Show Image Notice API 

#### Feature Updates 
* [SDK] 2.12.0
    * (iOS) Updated Facebook SDK (7.1.1)
    * (iOS) Attempts Gamebase initialization with storeCode(default=AS) set for configuration 
    * (iOS) Fixed failed closing due to lack of the close button while printing webview which cannot load content 
    * (Unity) Updated TOAST Unity SDK (0.20.1.1)
    
### 2.11.0 (June 23, 2020)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v2.11.0/GamebaseSDK-Unity.zip)

#### More Features
* [SDK] 2.11.0
	* Added Purchase API: Request for payment with Product ID, and enter additional information (UserPayload) to be confirmed when payment is completed 

### 2.10.1 (June 9, 2020)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v2.10.1/GamebaseSDK-Unity.zip)

#### Feature Updates 
* [SDK] 2.10.1
	* (iOS) Updated to set device language if language code is not configured when user push setting is initialized 

#### Bug Fixes
* [SDK] 2.10.1
	* (Unity) Fixed failed login calls since ViewController is not configured at iOS Plugin 
 
### 2.10.0 (May 26, 2020)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v2.10.0/GamebaseSDK-Unity.zip)

#### More Features
* [SDK] 2.10.0
	* (Common) Added GamebaseEventHandler which has all previous event systems 
		* Includes ServerPush and Observer, and checks promotional purchase or push events 

#### Feature Updates 
* [SDK] 2.10.0 
	* (Unity) Updated CefWebview version with StandaloneWebviewAdapter: v2.0.4
		* Updated the logic of WebviewIndex validation  
		* Fixed infrequent error of NullReferenceException while Webview is created 
    * (Unity) GamebaseErrorCode에 소켓 연결에 관한 에러 코드 추가: SOCKET_CONNECTION_TIMEOUT, SOCKET_CONNECTION_FAIL

#### Bug Fixes
* [SDK] 2.9.1
    * (Andoird) 매핑 이후 지표 레벨이 null이 되어 결제 지표에 정상적으로 반영되지 않는 오류 수정
    * (iOS) unreal 엔진에서 빌드 하면, warning을 빌드 오류로 판정해서 빌드가 안되는 부분을 수정

### 2.9.1 (April 29, 2020)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v2.9.1/GamebaseSDK-Unity.zip)

#### Bug Fixes
* [SDK] 2.9.1 
	* (Unity) Fixed a error which occurs when client service status is changed after initialized on console 
		* Versions at Issue: v2.8.0 or higher	
		* Platforms at Issue: Standalone, WebGL, and Editor

### 2.9.0 (April 28, 2020)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v2.9.0/GamebaseSDK-Unity.zip)

#### More Features
* Suspension of Membership Withdrawal 
	* [SDK 2.9.0]
		* (Common) Added API: Apply for suspension of withdrawal, Cancel application for suspension of withdrawal, Immediately withdraw while on suspension, and Check if user's withdrawal is suspended  

#### Feature Updates
* [SDK 2.9.0]
	* (Common) Updated TOAST SDK: Android(v0.21.0), iOS(v0.23.0), Unity(0.20.1)
	* (Common) Updated Payco Login SDK: Android(v1.5.0), iOS(v1.4.0)

### 2.8.1 (April 14, 2020)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v2.8.1/GamebaseSDK-Unity.zip)

#### Feature Updates 
* [SDK] 2.8.1 
	* (Common) Added internal indicators to check Analytics delivery results
	
### 2.8.0 (March 24, 2020)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v2.8.0/GamebaseSDK-Unity.zip)

#### More Features 
* [SDK] 2.8.0
	* (Common) Added more purchase and product information, such as product type and regional prices 
	* (Unity) Updated CefWebview to v2.0.1 within StandaloneWebviewAdapter 
		* When the PopupType is PASS_INFO, popup data can be delivered without a popup 

#### Feature Updates 
* [SDK] 2.8.0 
	* (Common) Updated to further show a popup to move to stores when it fails to initialize on an app version not registered on console 
	* (Android) Fixed codes that may fail due to initialization timing when payment-related API is called immediately after login 

### 2.7.2 (March 10, 2020)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v2.7.2/GamebaseSDK-Unity.zip)

#### Feature Updates
- [SDK] 2.7.2 
  	- (Unity) Updated FacebookAdapter  
    		- Compatibility testig from v7.9.4 to v7.18.1 
    		- Null exception handling   
  	- (Unity) Updated StandaloneWebviewAdapter 
    		- Added the feature of exporting webpages in texture 
    		- Support multiple webviews  
    		- Added the option of deleting cookies  
    		- Supports sizing of texture  
		- Supports showing/hiding the scrollbar 
    		- Notifies the completion of page loading  
    		- Supports transparent background
  	- (Unity) Fixed an error which occurs when Android/iOS is selected from Editor and Initialize API is called 

### 2.7.0 (January 21, 2020)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v2.7.0/GamebaseSDK-Unity.zip)

#### More Features
* [SDK] 2.7.0
	* (Unity) Supports NaverCafePLUG 

#### Bug Fixes
* [SDK] 2.7.0
	* (Android) Modified not to occur crash when the traceError, which is a required parameter, is missing at the server response 
	* (Android) Modified not to occur exceptions when Firebase setting is missing 
	* (Unity) Added the gamebase://dismiss scheme handling for a web login
	* (Unity) Modified infrequent failure in the display of webview for a release build 	

### 2.6.3 (January 14, 2020)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v2.6.3/GamebaseSDK-Unity.zip)

#### Feature Updates
* [SDK] 2.6.3
	* (Unity) Updated Standalone Webview: Updated CefWebview 	
	* (Unity) Added .dll file missing from an error occured after login 
		* ToastCommon.dll, vcruntime140.dll

#### Bug Fixes
* [SDK] 2.6.3
	* (Unity) Fixed error that occur when Login(CredentialInfo) API is called
	
### 2.6.2 (December 24, 2019)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v2.6.2/GamebaseSDK-Unity.zip)

#### More Features
* Conpon > Publish: Added the feature of keyword coupons

#### Feature Updates
* [SDK] 2.6.2
	* (Common) TOAST SDK Updates: Android(0.19.4), iOS(0.20.1), Unity(0.18.0)
	* (iOS) Naver SDK Updates (4.1.0)

### 2.6.1 (November 20, 2019)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v2.6.1/GamebaseSDK-Unity.zip)

#### Bug Fixes
* [SDK] 2.6.1
  * (Unity) Added the iOS Plugin file (toast_sdk_wrap.m) to Package in order to prevent errors for an iOS build  
  * (Unity) Fixed the error of UnityEditor in which the store code comes as empty on a platform other than Standalone, resulting in failed initialization  
  * (Unity) Fixed the error of NullReferenceException due to errors from processing zone type within Initialize API 

### November 13, 2019

#### Bug Fixes
* GamebaseSettingTool
  * Fixed the error in which files are not properly updated, with the version updated to Gamebase v2.6.0


### 2.6.0 (November 12, 2019)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v2.6.0/GamebaseSDK-Unity.zip)

```
To upgrade to Gamebase SDK 2.6.0 from a lower-than-2.6.0 version,  
make sure to apply changes as described in the Upgrade Guide.  
Find Upgrade Guide at: Game > Gamebase > Upgrade Guide
```

#### More Features 
* Added the payment feature for Google subscription  
  * [SDK] 2.6.0 Android
* [SDK] 2.6.0
  * (Common) Added TOAST Logger to send data to Log & Crash for analysis 
  * (iOS) Added authentication for Sign In with Apple 
  * (Android) Since Gamebase Android SDK is deployed by Bintray, it only takes a gradle setting to enable Gamebase. 

#### Feature Updates 
* [SDK] 2.6.0
  * (Unity) Fixed the error in the logic of updating LaunchingStatus for a login 
  * (Unity) Fixed the error of endless repetition of log delivery from the client, if delivery of debug logs is set on the Gamebase console

### October 15, 2019
#### Feature Updates 
* Sample App
	* Updated Gamebase SDK (v2.4.0)
	* Applied Smart Downloader (v1.5.8) and Leaderboard 
	* More Features: Downloading game resources, integrating Leaderboard and TAA indicators, transferring devices, and forced mapping 
	* Updates: Added ServerPush listeners and detection of observer maintenance  
	* Renewed games 
		
### 2.5.0 (August 27, 2019)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v2.5.0/GamebaseSDK-Unity.zip)

#### More Features 
* [SDK] 2.5.0
	* Provides API which opens CS URL entered on a console via webview 
	
### August 2, 2019 
#### Bug Fixes 
* [SDK] Setting Tool 1.4.3
	* Fixed the build error by moving down the script file below the editor folder  
	* Fixed failed operations when Multilanguage is provided with the entire path of the language file on MAC OS. 

### 2.4.4 (July 23, 2019)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v2.4.4/GamebaseSDK-Unity.zip)

#### Feature Updates
* [SDK] 2.4.4
	* (Common) Format changed for member error code
	* (Unity) Key added for GamebaseServerPushType (TRANSFER_KICKOUT)
* Setting Tool
	* Change of Folder Structure: Must reinstall after previous SettingTool is completely deleted  
	* More languages are supported 
	
### 2.4.3 (July 11, 2019)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v2.4.3/GamebaseSDK-Unity.zip)

#### Bug Fixes 
* [SDK] 2.4.3
	* (Unity) Fixed failed operations of AddMappingForcibly API, for the builds in iOS or Android 
	* (Unity) Fixed the json parsing error at iOSPlugin when RequestRetryTransaction API is called 

### June 27,2019

#### Bug Fixes
* [SDK] Setting Tool 1.4.1
	* Fixed the error in uploading existing setting data when GamebaseSettingTool was executed

### 2.4.2 (June 25, 2019)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v2.4.2/GamebaseSDK-Unity.zip)

#### Features Updates/Changes
* [SDK] 2.4.2
	* (Common) Add TOAST Launching information in the JSON string format to LaunchingInfo

#### Bug Fixes
* [SDK] 2.4.2
	* (Common) Fixed Bugs in Analytics: Modified to initialize indicators data that are saved before logout, withdrawal, or account transfer. 

### 2.4.0 (May 28, 2019)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v2.4.0/GamebaseSDK-Unity.zip)

#### Feature Updates 
* Purchase for HANGAME mix Available for Japan 
    * [SDK] 2.4.0
      * (Unity) Added external purchase for Standalone Japan  
      * (Unity)  Added HANGAME authentication for Standalone Japan 

#### Feature Updates/Changes
* [SDK] 2.4.0
  * (Common) Chanage of Classes Relevant to Indicators 
        * LevelUpData Class: Changed userLevel and levelUpTime as required parameters; the other fields are deleted [See Details: [Android](http://docs.toast.com/zh/Game/Gamebase/zh/aos-etc/#game-user-data-settings) / [iOS](http://docs.toast.com/zh/Game/Gamebase/zh/ios-etc/#game-user-data-settings) / [Unity](http://docs.toast.com/zh/Game/Gamebase/zh/unity-etc/#game-user-data-settings) / [JavaScript](http://docs.toast.com/zh/Game/Gamebase/zh/js-etc/#game-user-data-settings)]
            * GameUserData Class: Added the classId (game user's profession) field [See Details: [Android](http://docs.toast.com/zh/Game/Gamebase/zh/aos-etc/#level-up-trace) / [iOS](http://docs.toast.com/zh/Game/Gamebase/zh/ios-etc/#level-up-trace) / [Unity](http://docs.toast.com/zh/Game/Gamebase/zh/unity-etc/#level-up-trace) / [JavaScript](http://docs.toast.com/zh/Game/Gamebase/zh/js-etc/#level-up-trace)]

    * (Android) Naver SDK Version Updated (v4.2.5): Bug of Naver SDK fixed (fixed the issue, in which authentication process was stopped due to forced closure of activities when the app was restarted via app icon while login to Naver was underway)  
    * (Unity) StandaloneWebview supports 32bit Build (SDK volume upgraded from 53.6MB to 99.2MB)

### 2.3.0 (2019.04.23)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v2.3.0/GamebaseSDK-Unity.zip)

```
Gamebase를 사용하면 50여개의 중국스토어 연동이 가능합니다.
중국출시에 관심 있으신 경우에는 고객센터로 연락주세요.
```

#### 기능 추가
* [SDK] 2.3.0
	* (Android/Unity)중국스토어 인증/결제 추가

#### 기능 개선/변경
* [SDK] 2.3.0
	* (공통)Launching Status Code 추가: "심사중(204)", "테스트중(203)"

### 2.2.2 (2019.04.11)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v2.2.2/GamebaseSDK-Unity.zip)

#### 기능 개선/변경
* [SDK] 2.2.2
	* (Unity)SDK 로그 개선

#### 버그수정
* [SDK] 2.2.2
	* (Unity)AddMappingForcibly API를 호출하면 크래쉬가 발생하여 수정

### 2.2.1 (2019.04.02)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v2.2.1/GamebaseSDK-Unity.zip)
#### 버그수정
* [SDK] 2.2.1
	* (Unity) Unity Editor에서 Android 플랫폼을 선택하고 플레이를 하면 initialize시 서버에서 에러가 발생하는 이슈 수정

### 2.2.0 (2019.03.26)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v2.2.0/GamebaseSDK-Unity.zip)
#### 기능 추가
* TransferAccount 기능 추가: guest 사용자가 매핑없이 최대 2개의 키를 이용하여 새로운 기기로 이전할 수 있는 기능
    * (SDK공통)추가된 API 
        * TransferAccountInfo 발급 API (issueTransferAccount)
        * 발급된 TransferAccountInfo를 사용하여 계정 이전을 요청하는 API (transferAccountWithIdPLogin)
        * 발급된 TransferAccountInfo를 확인하는 API (queryTransferAccount)
        * 이미 발급된 TransferAccountInfo 갱신하는 API (renewTransferAccount)        
* 강제매핑 기능 추가: 이미 다른 계정에 연동 되어있는 IdP계정을 매핑할 수 있는 기능
    * (SDK공통)추가된 API 
        * 강제매핑하는 API (addMappingForcibly)

#### 기능 개선/변경
* [SDK] 2.2.0
	* (Android)IAP SDK 버전을 최신버전인 v1.5.3 버전으로 업데이트
	* (iOS)LINE SDK의 App 로그인 기능이 비활성화
		* LINE SDK v4의 버그로 인해 iOS 12에서 앱 로그인이 실패 하는 이슈가 있어 Gamebase Line Adatper에서 Web 로그인만 지원하도록 변경
	* (Unity)GamebaseMainActivity의 Package Name이 변경
		* com.toast.gamebase.activity.GamebaseMainActivity -> com.toast.android.gamebase.activity.GamebaseMainActivity

### 2.1.0 (2019.02.26)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v2.2.0/GamebaseSDK-Unity.zip)
#### 기능 개선/변경
* [SDK] 2.1.0
	* (공통)TransferKey API 삭제
		* issueTransferKey : TransferKey 발급
		* requestTransfer : TransferKey 검증

### 2.0.0 (2019.01.29)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v2.0.0/GamebaseSDK-Unity.zip)
```
Gamebase 2.0의 개선된 전체 지표를 활용하기 위해서는 SDK 업데이트가 필요합니다.
```

#### 기능 추가
* [SDK] 2.0.0
	* (공통)Custom 지표를 위한 API 추가 (구매 성공의 경우 SDK내부에서 자동 전송)
		* setGameUserData : 게임 로그인 이후 유저 레벨 정보 전송
		* traceLevelUpData : 레벨업 추적을 위하여 게임 유저의 레벨업이 되었을 때 호출

### 1.14.2 (2018.11.15)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v2.2.1/GamebaseSDK-Unity.zip)
#### 기능 개선/변경
* [SDK] 1.14.2
	* (Android)점검시, 데이터구조에서 점검 시작/종료 시간을 의미하는 epoch time의 타입을 기존 String에서 long으로 타입 변경 : 기존 Gamebase Unity와 연동 후 점검 호출 시 타입불일치로 콜백이 내려오지 않는 현상으로 인한 수정
	* (iOS)Provider Profile 획득 메서드 호출 시, 반환하는 TCGBAuthProviderProfile 객체의 description 메서드의 JSON 문자열 구조 변경으로 인하여 Gamebase iOS SDK 1.14.0와 Unity Plugin 1.14.0 적용시 crash가 발생될 수 있는 구조 수정

#### 버그수정
* [SDK] 1.14.2
	* (Unity)ShowWebView API 호출시 파라메타에 Callback을 넣지 않으면 crash가 발생되는 부분 수정
	* (Unity)iOS SDK의 Deleted API를 호출하는 코드가 있어 컴파일시 오류가 발생 되는 버그 수정

### 1.14.0 (2018.10.23)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v1.14.0/GamebaseSDK-Unity.zip)

#### 기능 추가
* [SDK] 1.14.0
    * (공통)Gamebase Webview에서 파일첨부 기능 추가 : Android의 API 19, Kitcat 에서는 정상 동작하지 않습니다.
    
#### 기능 개선/변경
* [SDK] 1.14.0
    * (공통)이용정지/점검에 대해 사용자가 콘솔에 작성한 메시지들을 URL 인코딩하여 전송하고 클라이언트에서 디코딩하여 처리하도록 수정
    * (Unity)GamebaseSDKSetting 오브젝트가 있는 씬으로 돌아갈 경우 오브젝트가 중복으로 생기지 않도록 개선
    * Remove API : Webview, Network, Launching
        * ShowWebBrowser(string url)
        * ShowWebView(GamebaseRequest.Webview.GamebaseWebViewConfiguration configuration)
        * ShowToast(string message, int duration)
        * AddUpdateStatusListener(GamebaseCallback.DataDelegate<GamebaseResponse.Launching.LaunchingStatus> callback) 
        * RemoveUpdateStatusListener(GamebaseCallback.DataDelegate<GamebaseResponse.Launching.LaunchingStatus> callback)
        * AddOnChangedStatusListener(GamebaseCallback.DataDelegate<GamebaseNetworkType> callback)
        * RemoveOnChangedStatusListener(GamebaseCallback.DataDelegate<GamebaseNetworkType> callback)
    * Deprecated  API 
        * GetLanguageCode()
* [SDK] Setting Tool        
    * 팝업 창 및 UI 개선
    
### 1.13.0 (2018.09.13)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v1.13.0/GamebaseSDK-Unity.zip)

#### 기능 개선/변경
* [SDK] 1.13.0
    * (공통)IAP SDK 최신버전 적용 (android:1.5.1, iOS:1.6.0)
    * (Unity)로그에서 보여주는 json 데이터를 알아보기 쉽도록 출력 포맷 개선
    
#### 버그수정
* [SDK] 1.13.0
    * (Unity)Unity 2017.2 이상 버전에서 Editor Play Mode 종료 시 websocke close 처리에서 발생하던 오류 수정
        
### 1.12.1 (2018.08.09)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v1.12.1/GamebaseSDK-Unity.zip)

#### 기능 개선/변경
* [SDK] 1.12.1
    * (공통)IAP SDK 최신버전 적용 (1.5.0)
    * (공통)Gamebase 점검페이지에서 점검시간을 단말기 설정 국가시간에 맞추어 노출하도록 개선
    * (공통)점검페이지를 외부 페이지로 사용할 때 Console에 입력한 점검 정보를 사용할 수 있도록 기능 추가
    * (공통)IdP 매핑된 사용자의 Guest 매핑시도시 에러 발생(TCGB_ERROR_AUTH_ADD_MAPPING_CANNOT_ADD_GUEST_IDP)
    * (공통)인증 API 중복 호출시 에러 발생(AUTH_ALREADY_IN_PROGRESS_ERROR)
    * (Android)TencentPush SDK 업데이트 (3.2.3)
    * (Android)Onestore v17(API v5) 지원 : Gamebase에서는 v16(스토어코드=TS)은 제공하지 않습니다.
    * (iOS)에러코드 추가 : Gamecenter 로그인 거부(TCGB_ERROR_IOS_GAMECENTER_DENIED)
* [SDK] Setting Tool
    * 폴더명 변경 : TOAST -> Toast
    * 에러발생시 팝업 창 알림 추가 : File Download 실패, File Extract 실패, XML 파싱 실패
    
### 1.12.0 (2018.07.24)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v1.12.0/GamebaseSDK-Unity.zip)

#### 기능 개선/변경
* [SDK] Setting Tool
    * Setting Tool 최신 버전이 있을 경우 업데이트 알림 기능 추가 
    * 내부 null Exception 수정
    
#### 버그수정
* [SDK] 1.12.0
    * (Unity)IssueTransferKey API 호출시 exception 발생하던 버그 수정
    * (Unity)Unity Google Adapter 제거 : 기존에 GoogleAdapter 사용중인 개발사는 아래 업데이트 가이드 참고
    
**Unity Google Adapter 업데이트 가이드**

* Unity SDK 1.6.0이상 1.11.0 이상 버전을 사용하는 경우 1.12.0 버전으로 업데이트 하기 전에 아래 내용을 필히 숙지하셔야 합니다.(1.6.0 미만 버전 사용중인 경우에는 GoogleAdapter를 미사용하기 때문에 영향이 없습니다.)
    1. Setting Tool 설정
        * GoogleAdapter가 제거됨에 따라 더이상 Unity 탭에서 Google 항목이 노출되지 않는다.
        * Google 인증을 사용할 경우에는 각 플랫폼 탭에서 Google 항목을 활성화한다.
            * Android > Authentication > Google 선택해서 설정
            * iOS > Authentication > Google 선택해서 설정
    2. Gamebase Login API (변경 없음)
        * Gamebase.Login(GamebaseAuthProvider.GOOGLE, callback);
    3. GPGS 기능을 사용하는 경우
        * GPGS SDK for Unity 유지
        * GPGS 관련 로직은 앱에서 별도로 관리
    4. GPGS 기능을 사용하지 않는 경우
        * GPGS SDK for Unity 삭제 

### 1.11.0 (2018.06.26)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v1.11.0/GamebaseSDK-Unity.zip)

#### 기능 추가
* iOS Google IdP 추가 : iOS
* Twitter IdP 추가 : Android, iOS
* Line IdP 추가 : Android만 제공. iOS는 2018년 7월 제공 예정입니다.
    
#### 기능 개선/변경
* [SDK] 1.11.0
    * (공통)LocalizedString 일본어 번역 추가
    * (공통)인증 API 호출시 초기화, 로그인을 하지 않은 경우 명확히 에러 코드를 구분하도록 내부 로직을 개선
    * (Android)'android.permission.READ_PHONE_STATE' 권한 제거
    * (Android)GamebaseConfiguration.Builder의 필수 설정값인 setAppId, setAppVersion을 생성자에서 입력할 수 있도록 변경
    * (Android)GamebaseConfiguration.Builder 의 setServerApiVerseion API를 제거
    * (Android)getAuthBanInfo() API, class AuthBanInfo 이름을 변경 : getBanInfo(), class BanInfo
    * Naver ID Login SDK 업데이트 : iOS(4.0.10)
* Sample App 
    * ServerPush 기능 및 Observer 기능 추가
    * Gamebase SDK 업데이트 : Android(1.9.0), iOS(1.9.0), Unity(1.10.1)    
    
### 1.10.1 (2018.06.11)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v1.10.1/GamebaseSDK-Unity.zip)

#### 버그수정
* [SDK] 1.10.1
    * (Unity)Unity Adapter가 없는 경우 AddMapping API 호출 시 내부적으로 로그인으로 처리하던 버그 수정

### 1.10.0 (2018.06.07)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v1.10.0/GamebaseSDK-Unity.zip)

#### 기능 추가
* [SDK] 1.10.0
    * (Unity)StandaloneWebviewAdapter: html source rendering 지원    

#### 기능 개선/변경
* [SDK] 1.10.0
    * (Unity)Unity Adapter의 interface가 수정
        * v1.10.0 이상 사용 시에는 UnityAdapter 버전 업그레이드가 필요(GamebaseUnitySDK_FacebookAdapter_v1.5.0, GamebaseUnitySDK_StandaloneWebviewAdapter_v1.7.0)
    * (Unity)Login API 호출 시 Unity Adapter가 없는 경우 네이티브(Android/iOS)의 로그인 API를 호출하도록 로직 변경 : facebook, Google
    * (Unity)각 Adapter 폴더 구조 및 이름 오타 수정
        * 경로: Assets/Gamebase/Scripts/Adapter => Assets/Gamebase/Adapter
        * 오타: Adapater => Adapter    
    
### 1.9.0 (2018.05.18)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v1.9.0/GamebaseSDK-Unity.zip)

#### 기능 개선/변경
* [SDK] 1.9.0
    * Unity SDK(1.9.0) Google Adapter 신규버전(1.6.2)으로 교체하여 재배포
        * 5/3 배포된 Unity SDK(1.9.0)에 적용된 Google Adapter를 최신버전으로 교체(1.6.1->1.6.2)
    
### 1.9.0 (2018.05.03)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v1.9.0/GamebaseSDK-Unity.zip)

#### 기능 추가
* Transfer 기능 추가
    * guest 사용자가 매핑없이 새로운 기기로 이전할 수 있는 기능
    * (SDK공통)추가된 API 
        * Transfer Key 발급 API (IssueTransferKey)
        * 발급된 TransferKey를 사용하여 계정 이전을 요청하는 API (RequestTransfer)
* 이용정지 등록시 사용자의 리더보드(랭킹) 데이터를 삭제할 수 있는 옵션 추가(TOAST Leaderboard를 사용하는 경우에 한함)
    * 이용정지 등록 메뉴를 이용하거나 App Guard 연동 페이지에서 사용 가능

### 1.8.1 (2018.04.09)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v1.8.1/GamebaseSDK-Unity.zip)
#### 버그 수정
* [SDK] 1.8.1
    * (Unity)UnityAndroid 플랫폼에서 아래 기능 사용 시 모듈 초기화가 되지 않아 NullReferenceException이 발생하여 수정
        * Launching, Purchase, Push, Util, Webview

### 1.8.0 (2018.04.05)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v1.8.0/GamebaseSDK-Unity.zip)

#### 기능 추가
* Kick out 기능 추가
    * 현재 게임 중인 전체 사용자의 연결을 끊는 기능(점검시 게임에서 전체 사용자의 연결을 끊고 싶을 때 사용할 수 있음)
    * (SDK 공통)kick out 이벤트를 받을 수 있는 API 추가
* 점검 웹페이지를 사용자가 Console에서 입력한 HTML 페이지로 사용할 수 있도록 기능을 개선
    * 이전에는 Gamebase에서 제공하는 웹페이지나 외부 웹페이지 연결만 가능했음
    * 웹서버가 없는 경우에도 점검페이지를 사용자가 원하는 형태로 만들 수 있음
* Observer 기능 개발 및 API 추가
    * (SDK 공통) 점검 등 앱 상태/네트워크 상태/유저 상태(이용정지) 변경사항에 대한 Listener를 Observer 등록을 통하여 일괄 처리할 수 있도록 API 추가

#### 기능 개선/변경
* [SDK] 1.8.0
    * (공통)Observer 기능 추가에 따라 다음 API Deprecated : LaunchingStatus Listener, Network Listener(기존 사용자는 계속 사용 가능)
    * (iOS)페이코 간편로그인 3rd SDK v1.2.2 적용 : 로그인 성공 시 토큰 만료 정보(expires_in) 제공, iPhoneX 로그인 UI 개선
    * (iOS)iPhoneX 지원을 위하여, Webview 사용 인터페이스 수정

#### 버그 수정
* 국가코드(contry code)가 10자 이상인 경우 동접 데이터가 저장되지 않는 현상 수정
* [SDK] 1.8.0
    * (Setting Tool)Unity Facebook Adapter를 체크하면 에러가 나는 버그 수정

### 1.7.1 (2018.03.13)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v1.7.1/GamebaseSDK-Unity.zip)

#### 버그 수정
* [SDK] 1.7.1
    * (Unity)Inspector에서 설정된 SetDebugMode 값이 반영 안 되던 버그 수정
    * (Unity)Standalone, WebGL: Display Language에서 사용되는 리소스 파일 누락 부분 수정
    * (Unity)Google Adapter 1.6.2 배포: Google Adapter 1.6.1에서 AuthCode가 Empty로 반환되어 인증 실패하는 버그 수정

### 1.7.0 (2018.02.22)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v1.7.0/GamebaseSDK-Unity.zip)
#### 기능 추가
* [SDK] 1.7.0
    * Naver IdP 인증 추가
    * Display Language 설정 추가: 단말기 언어와 별도로 게임내에서 게임유저의 노출 언어를 설정할 수 있도록 Display 언어를 추가하였습니다.

### 1.6.0 (2018.01.25)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v1.6.0/GamebaseSDK-Unity.zip)

#### 기능 추가
* [SDK] 1.6.0
    * (Unity)Standalone WinSDK 추가
        * 64비트 지원
        * 인증 지원 : facebook, google, payco

### 1.5.0 (2017.12.21)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v1.5.0/GamebaseSDK-Unity.zip)

#### 기능 추가
* [SDK] 1.5.0
    * WebView가 닫힐 때 발생하는 Close Callback 추가
    * WebView에서 사용하는 Custom Scheme의 Event를 받을 수 있는 기능 추가
    * Unity Setting Tool 신규 배포

#### 버그 수정
* [SDK] 1.5.0
    * (Unity)UnityEditor에서 Guest로그인이 되지 않는 현상 수정
    * (Unity)TOAST Console에 Facebook 인증 정보를 등록하지 않고 Gamebase.Login("facebook") API를 호출할 경우, KeyNotFoundException이 발생하여 방어코드 추가

### 1.4.0 (2017.11.23)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v1.4.0/GamebaseSDK-Unity.zip)

#### 기능 추가
* [SDK] 1.4.0 업데이트
    * (Unity)Gamebase Facebook Adapter가 추가 : Android, iOS, WebGL, Standalone Platform 및 UnityEditor 지원

### 1.3.0 (2017.10.26)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v1.3.0/GamebaseSDK-Unity.zip)

#### 기능 추가
* [SDK] 1.3.0 업데이트
    * Credential을 이용한 AddMapping API추가

#### 기능 개선/변경
* [SDK] 1.3.0 업데이트
    * (Unity)CredentialInfo를 사용하는 Login API호출 시 iOSPlugin에서 Json 파싱이 안되던 버그를 수정

### 1.2.0 (2017.09.21)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v1.2.0/GamebaseSDK-Unity.zip)

#### 기능 추가
* 이용정지(사용자처벌) 기능 추가
* [SDK] 1.2.0 업데이트
    * 이용정지 사용자 팝업 창 노출

### 1.1.5 (2017.07.20)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v1.1.5/GamebaseSDK-Unity.zip)

#### 기능 개선/변경
* Gamebase 상품 이용 중지시 관련 데이터 삭제를 위한 일 배치 기능 추가
* [SDK] 1.1.5 업데이트
    * 시스템 팝업 창 API 추가 (showAlertWithTitle)
    * 국가코드를 대문자로 반환하도록 변경 (Android)
    * TCPush SDK 1.4.1 로 업데이트
    * IAP SDK 1.3.3.20170627 로 업데이트

### 1.1.4 (2017.05.25)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v1.1.4/GamebaseSDK-Unity.zip)

#### 기능 개선/변경
* Gamebase 상품 이용 중지시 관련 데이터 삭제를 위한 일 배치 기능 추가
* [SDK] 1.1.4 업데이트
    * 런타임 중 결제 Store를 변경할 수 있는 API 제공
    * (Android)TCPushSdk v1.4 적용, Tencent Push 기능 제공

### 1.1.2 (2017.04.04)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v1.1.2/GamebaseSDK-Unity.zip)

#### 기능 개선/변경
* [SDK] 1.1.2 업데이트
    * 게임 론칭시 점검, 긴급공지 팝업 창 개선
    * Unity Plugin 디버그로그 추가 및 익셉션 상세처리

### 1.1.0 (2017.03.21)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v1.1.0/GamebaseSDK-Unity.zip)

#### 기능 개선/변경
* [SDK] 1.1.0 업데이트
    * 외부 AccessToken을 받아서 idPLogin을 해주는 인터페이스를 추가
    * [UI 기능 추가](./aos-ui) : Custom Webview, AlertDialog

### 1.0.0 (2017.03.09)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v1.0.0/GamebaseSDK-Unity.zip)

#### 신규 상품 출시
* 게임에서 공통적으로 필요한 기능들을 제공하여 손쉽고 효율적으로 게임 개발이 가능하도록 돕는 서비스입니다.
    * 다양한 인증 지원 : Guest , 3rd Party(Google , Facebook, GameCenter 등) 인증
    * 로그아웃 및 회원탈퇴 기능을 제공
    * 하나의 User가 여러 개의 외부 IDP를 동시에 사용할 수 있도록 mapping기능을 제공
    * 게임운영을 위한 게임 앱 상태관리, 점검, 긴급공지 등의 기능을 웹콘솔로 제공
    * 실시간 운영지표 확인 가능한 웹콘솔 화면 제공
    * TOAST Cloud상품 연동 : PUSH, IAP
