## Game > Gamebase > User Guide for Unreal SDK > Getting Started 

This document describes the environment and initial setting to enable Unreal Gamebase SDK.

## Environments

> [Note] 
>
> Support Versions for Unreal 
>
> * UE 4.22 ~ UE 4.26
> * To get support for a lower version of Unreal, please contact [Customer Center](https://toast.com/support/inquiry).

#### Supported Platforms

* iOS
* Android
* Editor
    * Supports partial features only. 

When unsupported Gamebase API is called on a selected platform, errors like below are returned as callback; if a callback is not available, warning logs show as output.  

* GamebaseErrorCode::NOT_SUPPORTED
* GamebaseErrorCode::NOT_SUPPORTED_IOS
* GamebaseErrorCode::NOT_SUPPORTED_ANDROID
* GamebaseErrorCode::NOT_SUPPORTED_UE4_STANDALONE
* GamebaseErrorCode::NOT_SUPPORTED_UE4_EDITOR

Platforms supported by each API can be categorized by the following icon: 

**API**

Supported Platforms
<span style="color:#1D76DB; font-size: 10pt">■</span> UNREAL_IOS
<span style="color:#0E8A16; font-size: 10pt">■</span> UNREAL_ANDROID
<span style="color:#B60205; font-size: 10pt">■</span> UNREAL_EDITOR

## Installation

1. Download Unreal Gamebase SDK and create a folder named `Plugins` in the project path and add the downloaded SDK.  
2. From the Unreal editor, display the `Settings > Plugins` window, and find and enable `Project > Gamebase > Gamebase Plugin`.

* [Download Gamebase Unreal SDK](/Download/#game-gamebase)

### Android Settings

1. Select **Edit > Project Settings** from the editor menu.
2. In the Project Settings window, under Plugin category, select **Gamebase**.

![Unreal Project Settings - Android](https://static.toastoven.net/prod_gamebase/UnrealDevelopersGuide/unreal-developers-guide-started-android-setttings-2.19.0.png)

* Android - Authentication
    * Activate the IdP to use.
    * To use Hangame IdP, please contact our Customer Center.
* Android - Push
    * Activate the Push to use.
* Android - Purchase
    * Select the store to use.
    * ONE Store
        * Select View Option - Full payment screen (Full) or Payment popup window (Popup).


#### An issue where Google Play authentication and payment does not complete

Processing the authentication and payment for the Google Play service requires Distribution settings.
To find out more, see the following document. 

* [Signing Projects for Release](https://docs.unrealengine.com/en-US/Platforms/Mobile/Android/DistributionSigning/index.html)

#### Enable AndroidX

* From Gamebase Android SDK 2.25.0, AndroidX has been introduced. Therefore, you must add the following setting to the [UPL (Unreal Plugin Language)](https://docs.unrealengine.com/4.27/en-US/SharingAndReleasing/Mobile/UnrealPluginLanguage/) file.

```xml
<gradleProperties>    
  <insert>
    android.useAndroidX=true      
    android.enableJetifier=true    
  </insert>  
</gradleProperties>
```

#### Enable multidex

* From Gamebase Unreal SDK 2.26.0, the multidex-related setting within Gamebase has been removed. Therefore, you must add the following setting to the [UPL (Unreal Plugin Language)](https://docs.unrealengine.com/4.27/en-US/SharingAndReleasing/Mobile/UnrealPluginLanguage/) file.

```xml
<buildGradleAdditions>
  <insert>
  android {
    defaultConfig {
      multiDexEnabled true
    }
  }
  </insert>
</buildGradleAdditions>

<androidManifestUpdates>
    <addAttribute tag="application" name="android:name" value="androidx.multidex.MultiDexApplication"/>
</androidManifestUpdates>
```

### iOS Settings

To use the Gamebase SDK for Unreal, `UE4 Github source code` has to be used, and the Github account must be linked after joining the Epic games in order to expose the UnrealEngine repository.
See below for relevant guides.  

* [Downloading Unreal Engine Source Code](https://docs.unrealengine.com/5.0/en-US/downloading-unreal-engine-source-code/)
* [Getting up and running](https://github.com/EpicGames/UnrealEngine#getting-up-and-running)

>`!Important`
> If you ignore this process, the following guide link does not properly work and the Gamebase SDK for Unreal will become unavailable.

#### Sign in with Apple

To enable Sign in with Apple, com.apple.developer.applesignin must be added to entitlement.  

* [Sign in with Apple Entitlement](https://developer.apple.com/documentation/bundleresources/entitlements/com_apple_developer_applesignin)

If login to Gamebase AppleId is attempted without a key value added, error shall occur like below:   

```
Authorization failed: Error Domain=AKAuthenticationError Code=-7026 "(null)"
```

Since UE4(4.24.3) does not support the feature, below codes must be added above line 196 of the following file.  [Engine/Source/Programs/UnrealBuildTool/Platform/IOS/IOSExports.cs](https://github.com/EpicGames/UnrealEngine/blob/release/Engine/Source/Programs/UnrealBuildTool/Platform/IOS/IOSExports.cs).

```cs
// AS-IS
if (bRemoteNotificationsSupported)
{
    Text.AppendLine("\t<key>aps-environment</key>");
    Text.AppendLine(string.Format("\t<string>{0}</string>", bForDistribution ? "production" : "development"));
}

// TO-BE
if (bRemoteNotificationsSupported)
{
    Text.AppendLine("\t<key>aps-environment</key>");
    Text.AppendLine(string.Format("\t<string>{0}</string>", bForDistribution ? "production" : "development"));
    Text.AppendLine("\t<key>com.apple.developer.applesignin</key>");
    Text.AppendLine("\t<array>");
    Text.AppendLine("\t\t<string>Default</string>");
    Text.AppendLine("\t</array>");
}
```

#### Remote Notification

1. To enable Gamebase Remote Notification, go to **Project Settings > Platforms > iOS** and activate **Enable Remote Notifications Support**. (available only on Github sources)
2. To receive the Foreground push notification, the code shown below must be removed from the [Engine/Source/Runtime/ApplicationCore/Private/IOS/IOSAppDelegate.cpp](https://github.com/EpicGames/UnrealEngine/blob/4.24/Engine/Source/Runtime/ApplicationCore/Private/IOS/IOSAppDelegate.cpp) file, or

        - (void)userNotificationCenter:(UNUserNotificationCenter *)center
            willPresentNotification:(UNNotification *)notification
                withCompletionHandler:(void (^)(UNNotificationPresentationOptions options))completionHandler
        {
            // Received notification while app is in the foreground
            HandleReceivedNotification(notification);
        
            completionHandler(UNNotificationPresentationOptionNone);
        }

    modify it as follows:
        
            // AS-IS
            completionHandler(UNNotificationPresentationOptionNone);
            
            // TO-BE
            completionHandler(UNNotificationPresentationOptionAlert);

#### Rich Push Notification

Cannot use the Rich Push Notification function due to the following issues:

* Unreal does not provide any methods for adding the [Notification Service Extension](https://developer.apple.com/documentation/usernotifications/unnotificationserviceextension?language=objc) to the project.
    * [Create NHN Cloud Push Notification Service Extension](https://docs.toast.com/en/TOAST/en/toast-sdk/push-ios/#notification-service-extension)

#### Error in Unreal Builds due to Warning Messages of iOS SDK

If a warning message from iOS SDK is converted as error for Unreal build, leading into failure in the buildup, handle the clang compile option code of the following file as footnotes: [Engine/Source/Programs/UnrealBuildTool/Platform/IOS/IOSToolChain.cs](https://github.com/EpicGames/UnrealEngine/blob/4.24/Engine/Source/Programs/UnrealBuildTool/Platform/IOS/IOSToolChain.cs)

```cs
// Result += " -Wall -Werror";
```

#### PLCrashReporter

There is an issue where the device using the architecture cannot get the memory address because the PLCrashReporter used by UE4 does not support the `arm64e` architecture.

Game developers using the crash analysis of the NHN Cloud Log & Crash Search must refer to the following guide to modify the UE4 internal PLCrashReporter:

1. Unzip the GamebaseSDK-Unreal/Source/Gamebase/ThirdParty/IOS/GamebaseSDK-iOS/externals/plcrashreporter.zip file.
2. Replace the file and header file of the UE4 internal PLCrashReporter with the unzipped file.
    * Engine/Source/ThirdParty/PLCrashReporter/plcrashreporter-master-xxxxxxx

## API Deprecate Governance

APIs that are no longer supported by Gamebase are to be deprecated. 
Once deprecated, APIs might be deleted without previous notice if they fulfill the following conditions: 

* Updated more than 5 times for a minor version 
    * Gamebase Version Format - XX.YY.ZZ
        * XX : Major
        * YY : Minor
        * ZZ : Hotfix

* At least 5-month old 
