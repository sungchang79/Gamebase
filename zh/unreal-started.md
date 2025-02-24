## Game > Gamebase > Unreal SDK使用指南 > 开始

描述Gamebase Unreal SDK的使用环境和默认设置。

### Environments

> [参考] 
>
> Unreal支持的版本
>
> * UE 4.22 ~ UE 4.26
> * 如果需要比上述版本更低的Unreal版本，请联系[客户服务](https://toast.com/support/inquiry)。

#### Supported Platforms

* iOS
* Android
* Editor
    * 只支持一部分功能。

当调用所选的平台不支持的Gamebase API时，通过回调返还以下错误。若没有回调，则输出Warning日志。 

* GamebaseErrorCode::NOT_SUPPORTED
* GamebaseErrorCode::NOT_SUPPORTED_IOS
* GamebaseErrorCode::NOT_SUPPORTED_ANDROID
* GamebaseErrorCode::NOT_SUPPORTED_UE4_STANDALONE
* GamebaseErrorCode::NOT_SUPPORTED_UE4_EDITOR

每个API支持的平台按以下图标分类。 

**API**

Supported Platforms
<span style="color:#1D76DB; font-size: 10pt">■</span> UNREAL_IOS
<span style="color:#0E8A16; font-size: 10pt">■</span> UNREAL_ANDROID
<span style="color:#B60205; font-size: 10pt">■</span> UNREAL_EDITOR

## Installation

1. 下载Gamebase Unreal SDK后，在项目路径创建**Plugins**文件夹，并将下载的SDK添加在文件夹里。
2. 在Unreal编辑器中打开**Settings > Plugins**窗口后，启用**Project > Gamebase > Gamebase Plugin**中的Plugin。 

* [Download Gamebase Unreal SDK](/Download/#game-gamebase)

### Android Settings

1. 选择编辑器菜单**Edit > Project Settings**。
2. 在Project Settings窗选择Plugin类别中的**Gamebase**。

![Unreal Project Settings - Android](http://static.toastoven.net/prod_gamebase/UnrealDevelopersGuide/unreal-developers-guide-started-android-setttings-2.19.0.png)

* Android - Authentication
    * 启用要使用的IdP。
    * 关于使用Hangame IdP有提问时，请联系客服。
* Android - Push
    * 启用要使用的Push。
* Android - Purchase
    * 选择要使用的商店。
    * ONE Store
        * View Option - 在结算页面(Full)和结算弹窗(Popup)当中选择。 


#### Google Play认证和未完成付款

若想在Google Play服务进行认证和结算，则需设置Distribution。 
关于详细的内容，请参考以下文档。

* [Signing Projects for Release](https://docs.unrealengine.com/en-US/Platforms/Mobile/Android/DistributionSigning/index.html)

#### AndroidX适用

* 因为Android X将适用于Gamebase Android SDK 2.25.0版本，需要在[UPL(Unreal Plugin Language)](https://docs.unrealengine.com/4.27/en-US/SharingAndReleasing/Mobile/UnrealPluginLanguage/)文件中添加以下设置。
  
```xml
<gradleProperties>    
  <insert>
    android.useAndroidX=true      
    android.enableJetifier=true    
  </insert>  
</gradleProperties>
```

#### multidex适用	

* 因为将从Gamebase Unreal SDK 2.26.0版本开始删除与Gamebase内multidex有关的信息，需要在[UPL(Unreal Plugin Language)](https://docs.unrealengine.com/4.27/en-US/SharingAndReleasing/Mobile/UnrealPluginLanguage/)文件中添加以下设置。 

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

若要使用Gamebase SDK for Unreal，则需使用”UE4 Github源代码”。注册成为Epic games会员后连接Github账户才能显示UnrealEngine repository。
有关指南内容，请参考以下文档。

* [Downloading Unreal Engine Source Code](https://docs.unrealengine.com/5.0/en-US/downloading-unreal-engine-source-code/)
* [Getting up and running](https://github.com/EpicGames/UnrealEngine#getting-up-and-running)

>”!注意”
> 如果省略此程序，无法正常使用以下指南的链接或Gamebase SDK for Unreal。

#### Sign in with Apple

为了使用Sign in with Apple功能，需要在entitlement中添加com.apple.developer.applesignin key值。 

* [Sign in with Apple Entitlement](https://developer.apple.com/documentation/bundleresources/entitlements/com_apple_developer_applesignin)

若不添加key值的状态下进行Gamebsae AppleId登录，则将出现以下错误。 

```
Authorization failed: Error Domain=AKAuthenticationError Code=-7026 "(null)"
```

因UE4(4.24.3)不支持此功能，要在[Engine/Source/Programs/UnrealBuildTool/Platform/IOS/IOSExports.cs](https://github.com/EpicGames/UnrealEngine/blob/4.24/Engine/Source/Programs/UnrealBuildTool/Platform/IOS/IOSExports.cs)文件中修改以下代码。

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

1. 为了使用Gamebase Remote Notification功能，需要在**Project Settings > Platforms > iOS**设置中启用**Enable Remote Notifications Support**功能(只有在Github下载源码时才能使用)。
2. 为了接收Foreground推送通知，要在[Engine/Source/Runtime/ApplicationCore/Private/IOS/IOSAppDelegate.cpp](https://github.com/EpicGames/UnrealEngine/blob/4.24/Engine/Source/Runtime/ApplicationCore/Private/IOS/IOSAppDelegate.cpp)文件中删除以下代码，

        - (void)userNotificationCenter:(UNUserNotificationCenter *)center
            willPresentNotification:(UNNotification *)notification
                withCompletionHandler:(void (^)(UNNotificationPresentationOptions options))completionHandler
        {
            // Received notification while app is in the foreground
            HandleReceivedNotification(notification);
        
            completionHandler(UNNotificationPresentationOptionNone);
        }

    修改的方式如下。
        
            // AS-IS
            completionHandler(UNNotificationPresentationOptionNone);
            
            // TO-BE
            completionHandler(UNNotificationPresentationOptionAlert);

#### Rich Push Notification

因出现以下问题不能使用Rich Push Notification功能。

* Unreal不提供在项目中可添加[Notification Service Extension](https://developer.apple.com/documentation/usernotifications/unnotificationserviceextension?language=objc)的方法。
    * [创建NHN Cloud Push Notification Service Extension](https://docs.toast.com/en/TOAST/en/toast-sdk/push-ios/#notification-service-extension)

#### iOS SDK的Warning消息导致Unreal打包错误

若因iOS SDK上出现的Warning消息转为错误，导致Unreal打包失败的现象，则需对[Engine/Source/Programs/UnrealBuildTool/Platform/IOS/IOSToolChain.cs](https://github.com/EpicGames/UnrealEngine/blob/4.24/Engine/Source/Programs/UnrealBuildTool/Platform/IOS/IOSToolChain.cs)文件中的clang编译选项进行注释。 

```cs
// Result += " -Wall -Werror";
```

#### PLCrashReporter

因UE4中使用的PLCrashReporter不支持”arm64e”architecture，出现无法从使用该architecture的设备获取存储器地址值的问题。

在NHN Cloud Log & Crash Search中使用Crash分析的游戏开发公司应参考以下指南更改UE4内部PLCrashReporter。

1. 需要解压GamebaseSDK-Unreal/Source/Gamebase/ThirdParty/IOS/GamebaseSDK-iOS/externals/plcrashreporter.zip文件。
2. 将UE4内部PLCrashReporter的a文件和header文件换成解压缩的文件。
    * Engine/Source/ThirdParty/PLCrashReporter/plcrashreporter-master-xxxxxxx

## API Deprecate Governance

将对Gamebase不支持的API进行Deprecate处理。 
若Deprecated的API符合以下条件，可能在未通知的状态被删除掉。

* 更新5次以上的次要版本
    * Gamebase Version Format - XX.YY.ZZ
        * XX : Major
        * YY : Minor
        * ZZ : Hotfix

* 至少经过5个月