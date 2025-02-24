## Game > Gamebase > Upgrade Guide

## 2.35.0

### Android

#### Naver IdP

* 이제 Naver 로그아웃시 토큰을 삭제하지 않습니다.
    * 재로그인 할 때 정보 제공 동의 창이 뜨지 않습니다.
    * 웹로그인시에는 계정이 변경되지 않습니다.
    * 이전 동작을 유지하기 위해서는 Gamebase Console의 AdditionalInfo에 다음과 같이 설정하세요.

```
{"logout_and_delete_token":true}
```

## 2.34.0

### Android

#### Changed/Deprecated APIs

* 由于在Gamebase控制台中注册Kickout时可以设置是否显示kickout弹窗，因此以下字段已被deprecated。
    * **UIPopupConfiguration.enableKickoutPopup**

### iOS

#### Changed/Deprecated APIs

* 由于在Gamebase控制台中注册Kickout时可以设置是否显示kickout弹窗，因此以下API已被deprecated。
    * **[TCGBConfiguration enableKickoutPopup:]**
    * **[TCGBConfiguration isEnableKickoutPopup]**

### Unity

* 目前不支持GamebaseConfiguration的enableKickoutPopup属性。

## 2.33.0

### iOS

* 更改了与TCGB_ERROR_UNKNOWN_ERROR进行映射的错误代码。
    * TCGB_ERROR_UNKNOWN_ERROR的错误代码从999更改为9999。
    * 添加了映射到999错误代码的TCGB_ERROR_SOCKET_UNKNOWN_ERROR错误。
    
### Unity

* 更改了与GamebaseErrorCode.UNKNOWN_ERROR进行映射的错误代码。
    * GamebaseErrorCode.UNKNOWN_ERROR的错误代码从999更改为9999。
    * 添加了映射到999错误代码的GamebaseErrorCode.SOCKET_UNKNOWN_ERROR错误。

### Unreal

* 更改了与GamebaseErrorCode.UNKNOWN_ERROR进行映射的错误代码。
    * GamebaseErrorCode::UNKNOWN_ERROR的错误代码从999更改为9999。
    * 添加了映射到999错误代码的GamebaseErrorCode::SOCKET_UNKNOWN_ERROR错误。  

## 2.32.0

### Android

* 由于Gamebase Access Token过期无法恢复而发生的GamebaseEventHandler事件category，在**GamebaseEventCategory.OBSERVER_HEARTBEAT**中已更改为**GamebaseEventCategory.LOGGED_OUT**。
    * 请更改登录条件，即当**GamebaseEventCategory.OBSERVER_HEARTBEAT**事件中的GamebaseEventObserverData.code值为**GamebaseError.AUTH_TOKEN_LOGIN_INVALID_TOKEN_INFO(3102)**时登录的条件，更改为在**GamebaseEventCategory.LOGGED_OUT**事件中登录。

## 2.29.0 
 
### Unity
 
* 已发布Setting Tool 2.0.0。  
    * 因文件结构已被更改，需要删除以前的Setting Tool后重新进行设置。 
    * 使用Setting Tool 1.5.0以下的用户需要删除以下Directory中的所有与Gamebase有关的库。
        * **Assets/Plugins/Android**  
        * **Assets/Plugins/iOS** 
    * 关于更改的信息和使用方法，请参考如下指南。
        * [Game > Gamebase > Unity SDK使用指南 > 开始 > Specification of Setting Tool](./unity-started/#specification-of-setting-tool)

## 2.27.0

### iOS

#### ImageNotice

* 已修改在Unity中未能显示图片通知的问题。
    * 如果使用低于Gamebase iOS SDK 2.27.0的版本，有可能在Unity中看不到图片通知。 
    * 如果要使用图片通知，请使用Gamebase iOS SDK 2.27.0以上版本。 
 
## 2.26.0

### Unity

* 使用相关版本时，请直接删除”Assets/Gamebase/Toast/IAP/Plugins”后使用。
    * 如果应用了Gamebase Unity SDK 2.27.0或更高版本，则无需删除。 

### Unreal

* 在Gamebase中multidex设置已被删除。如果要设置，请参考以下指南。
    * [Game > Gamebase > Unreal SDK使用指南 > 开始 > Installation > Android Settings > 应用multidex](./unreal-started/#android-settings)


## 2.25.0

### Android

#### Changed Minimum Support Version

* 支持的最低Android Gradle Plugin(AGP)版本从2.3.0已升级至3.2.0。
    * 但将targetSdkVersion设置为30以上时，若要支持Android 11终端机，则需AGP 3.3.3以上版本。
        * 请参考以下文件。
        * [Game > Gamebase > Android SDK使用指南 > 开始 > Setting > Android 11](./aos-started/#android-11)
* 如果需要低版本的AGP支持，请联系[客户服务](https://toast.com/support/inquiry)。

#### AndroidX

* Android Support Library的依赖已被更改为AndroidX，请将该修改项目应用于Gradle中。

* 为不支持AndroidX的库，请在gradle.properties文件中添加以下迁移声明。

```groovy
# >>> [AndroidX]
android.useAndroidX=true
android.enableJetifier=true
```

* 为最新AndroidX版本，请在build.gradle文件中添加Java 8打包设置。 

```groovy
android {
    compileOptions {
        // >>> [AndroidX]
        sourceCompatibility JavaVersion.VERSION_1_8
        targetCompatibility JavaVersion.VERSION_1_8
    }
}
```

#### Under AGP 3.4.0

* Android Gradle Plugin版本低于3.4.0时将出现打包失败，因此需要在gradle.properties文件中添加如下声明。

```groovy
# gradle.properties
# >>> Fix for AGP under 3.4.0
android.enableD8.desugaring=true
android.enableIncrementalDesugaring=false
```

#### Line IdP

* 使用Line IdP时，因在Line SDK内存在**&lt;queries&gt;**标签，根据AGP版本可能会打包失败。 
    * 请参考以下指南，请升级为可进行”queries”标签打包的AGP版本。 
    * [Game > Gamebase > Android SDK使用指南 > 开始 > Setting > Android 11](./aos-started/#android-11)
* 使用Line IdP时，由于在Line SDK内已被声明为**android:allowBackup="false"**，应用程序打包时有可能在Manifest merger中出现fail。如果打包失败，请按照以下示例，在application标签中添加**tools:replace="android:allowBackup"**声明。
```xml 
<application
      tools:replace="android:allowBackup"
      ... >
```

### iOS

* 进行修改后，当出现Sign In with Apple的ASAuthorizationErrorUnknown错误时返回TCGB_ERROR_AUTH_EXTERNAL_LIBRARY_ERROR (3009)错误。 

### Unity

* 使用相关版本时，请直接删除”Assets/Gamebase/Toast/IAP/Plugins”后使用。
    * 如果应用了Gamebase Unity SDK 2.27.0或更高版本，则无需删除。 

#### Changed Minimum Support Version

* 支持的最低Unity版本从2017.4.16已升级至2018.4.0。
* 如果需要低版本的Unity支持，请联系[客户服务](https://toast.com/support/inquiry)。

#### AndroidX Build

* 在Gamebase Android SDK中应用AndroidX时，为了Android打包需要添加以下声明。 
* 低于2019.3

```groovy
// mainTemplate.gradle
([rootProject] + (rootProject.subprojects as List)).each {
    ext {
        it.setProperty("android.useAndroidX", true)
        it.setProperty("android.enableJetifier", true)
    }
}
```

* 2019.3以上

```groovy
// gradleTemplate.properties
android.useAndroidX=true
android.enableJetifier=true
```

#### Under AGP 3.4.0
 
* 当Unity Editor版本为2018.4.3以下或2019.1.6以下时，由于AGP版本低(3.2.0)将出现打包失败，因此需要添加如下声明。 

```groovy
// mainTemplate.gradle
([rootProject] + (rootProject.subprojects as List)).each {
    ext {
        // >>> Fix for AGP under 3.4.0
        it.setProperty("android.enableD8.desugaring", true)
        it.setProperty("android.enableIncrementalDesugaring", false)
    }
}
```

### Unreal

#### AndroidX Build

* 在Gamebase Android SDK中应用AndroidX时，为了Android打包在UPL中添加以下声明。

```xml
<gradleProperties>    
  <insert>      
    android.useAndroidX=true      
    android.enableJetifier=true    
  </insert>  
</gradleProperties>
```

## 2.21.2

### iOS

* 如果在Gamebase iOS SDK 2.21.1中启用bitcode并进行**archive build**，则将出现错误。
    * 使用bitcode时，请使用已解决上述问题的Gamebase iOS SDK 2.21.2。

## 2.21.0

### Android  

* 若由于向jCenter发布的Gamebase Android SDK 2.21.0打包出现错误，在声明**mavenCentral()**之前声明了**jcenter()**，将使所有Gamebase API崩溃。 
    * 请使用未出现错误的Gamebase Android SDK 2.21.1或声明**jcenter（）之前先声明**mavenCentral（）**。
* Maven Repository
    * 因jCenter停止向一般用户提供服务([https://jfrog.com/blog/into-the-sunset-bintray-jcenter-gocenter-and-chartcenter/](https://jfrog.com/blog/into-the-sunset-bintray-jcenter-gocenter-and-chartcenter/) )，无法再上载新版本。(对jCenter的访问也将于2022年2月1日结束。)
    * 从Gamebase Android SDK 2.21.0以上版本开始只在**mavenCentral()**发布，而不在**jcenter()**发布，因此需要在gradle repository中添加mavenCentral。

```groovy
repositories {
    // >>> For Gamebase SDK
    mavenCentral()
    ...
}
```

#### Line IdP

* 使用Line IdP时，当Line SDK被更新时，若不在Gradle中设置**JavaVersion.VERSION_1_8**，则将导致打包失败(请参考以下示例)。

```groovy
android {
    compileOptions {
        // >>> [Line IdP]
        sourceCompatibility JavaVersion.VERSION_1_8
        targetCompatibility JavaVersion.VERSION_1_8 
    }
}
```

### iOS

* 如果在Gamebase iOS SDK 2.21.0上使用bitcode，则将出现错误。 
    * 如果要使用bitcode，请使用Gamebase iOS SDK 2.21.1。

## 2.20.2
 
### iOS

#### Facebook IdP

* Facebook SDK已在Gamebase iOS SDK 2.20.2中更新至9.1.0。
    * 需要对Facebook SDK进行额外的设置，请在info.plist中添加以下值。如果不进行设置，则将导致崩溃。
        * FacebookAutoLogAppEventsEnabled
        * FacebookAdvertiserIDCollectionEnabled
* 关于详细信息，请参考[Facebook iOS SDK指南](https://developers.facebook.com/docs/app-events/getting-started-app-events-ios)。

## 2.19.0

### Android

#### Weibo IdP

* 若在Gamebase Android SDK 2.19.0中交替使用Weibo IdP登录和其他IdP登录，则将发生崩溃。
    * 如果需要用Weibo IdP，请使用已解决上述问题的Gamebase Android SDK 2.19.1。

## 2.18.2

### Android

#### Removed APIs

* 已经从Gamebase Android SDK 2.6.0中删除被deprecated的函数。
    * **GamebaseConfiguration.Builder.setFCMSenderId()**
    * **GamebaseConfiguration.Builder.setTencentAccessKey()**
    * **GamebaseConfiguration.Builder.setTencentAccessId()**

## 2.18.0

### Android

#### Purchase Google

* 如果在Gamebase Android SDK 2.18.0中调用Google道具支付，则将发生崩溃。 
    * 如果需要用Weibo IdP，请使用已解决上述问题的Gamebase Android SDK 2.18.1。

## 2.17.0

### Android

* 若在Gamebase Android SDK 2.17.0中调用Gamebase.ImageNotice.showImageNotices API，则将发生崩溃。
    * 请使用已解决2.17.0崩溃或在OS 5.0~6.0中Custom Scheme Event不正常启动等问题的Gamebase Android SDK 2.17.4。
 
## 2.15.1

### iOS

* 当使用gamebase SDK中定义的**gamebaseeventcategory**类型而不使用nsstring时，要将此类型更改为**tcgbgamebaseeventcategory**。

## 2.15.0

### Android

#### Purchase Google

* 使用**gamebase-adapter-purchase-google**时，若要将Gamebase SDK 2.15.0以下版本升级到2.15.0以上版本，则必须将**以前版本的Game Client Version设置为“必须更新”**。 
	* 当Google Billing Client模块儿被更新，使不同的Billing Client版本应用于多个终端机的情况下，如果购买道具时出现错误，进行“支付在处理”时将出现问题。

## 2.6.0

### Unity

#### Android Limitation

* 由于Android Support Library版本升至28.0.0，Unity 5、Unity 2017.1、Unity 2017.2中Android创建失败。
	* 若使用Unity 2017.3以下版本Editor，请安装Unity 2017.3以上版本，复制“Editor/Data/PlaybackEngines/AndroidPlayer/Tools/gradle/lib”文件夹，覆盖在与您使用的Unity Editor的相同的路径，并按如下示例修改mainTemplate.gradle文件。

```groovy
// GENERATED BY UNITY. REMOVE THIS COMMENT TO PREVENT OVERWRITING WHEN EXPORTING AGAIN
buildscript {
	repositories {
		jcenter()
        // >>> For download Gradle Android Plugin
        maven {
            url 'https://maven.google.com'
        }
	}

	dependencies {
		//classpath 'com.android.tools.build:gradle:2.1.0'
        // >>> Update Gradle Android Plugin version
        classpath 'com.android.tools.build:gradle:2.3.0'
	}
}
```

#### Firebase推送

* 使用Firebase Cloud Messaging时，将从Firebase Console中下载的google-services.json文件转换为xml资源，并添加到项目中才能成功收到推送。
    * 使用Gamebase 2.5.0以前的旧版本时，没有xml资源的情况下也可收到推送，但使用Gamebase 2.6.0以上版本时必须要有xml资源才能收到。
* 请参考以下实施指南。
    * [\[Game > Gamebase > Android SDK使用指南 > push > Settings > Firebase\]](./aos-push/#firebase)

#### Standalone

* Removed Japan Purchase
	* 日本支付已FadeOut。
	* 若使用GamebaseUnitySDK_IAPAdapter，请直接删除如下文件夹。
        * Asset/Toast/Common
        * Asset/Toast/Core
        * Asset/Toast/IAP
        * Asset/Toast/Standalone

### Android

#### Limitation

* minSdkVersion由15(IceCreamSandwichMR1, 4.0.3)更改为16(JellyBean, 4.1)。
	* OS 4.1以下的终端机中无法保证正常运行，因此项目的minSdkVersion为15时，请更改为16。

#### Removed APIs

* 清除的函数如下。请更改为替代函数。
    * **Gamebase.getAuthBanInfo()**已清除。请更改为**Gamebase.getBanInfo()**。
    * **Gamebase.getLanguageCode()**已清除。请更改为**Gamebase.getDeviceLanguageCode()**。
    * **new GamebaseConfiguration.Builder(void)**已清除。请更改为**GamebaseConfiguration.newBuilder()**。
    * **new GamebaseConfiguration.Builder.setAppId()**已清除。请更改为**GamebaseConfiguration.newBuilder()**。
    * **new GamebaseConfiguration.Builder.setAppVersion()**已清除。请更改为**GamebaseConfiguration.newBuilder()**。

#### Changed/Deprecated APIs

* Gamebase.activeApp()为自动调用，因此可不再调用。
* 作为Gamebase.initialize()的因素需要的GamebaseConfiguration的创建方法已更改。
    * 取代**new GamebaseConfiguration.Builder(String, String)**，调用**GamebaseConfiguration.newBuilder()**。
* 请勿再调用LaunchingStatus.isPlayable()。
	* 请参考[\[Game > Gamebase > Android SDK使用指南 > 初始化 > Launching Information\]](./aos-initialization/#launching-information)文件，按照Launching Status Code直接决定是否可以玩游戏。
* Purchase
    * Store Code无法更改，因此应从**GamebaseConfiguration.newBuilder()**传输Store Code。
        * Gamebase.Purchase.getStoreCode() / Gamebase.Purchase.setStoreCode()将清除。请勿再使用。
    * Gamebase.Purchase.requestRetryTransaction()现在不调用也无妨。
* Push
    * 自Gamebase Android SDK 2.6.0以上起，发送推送信息时，应通过Gamebase控制台的**推送**选项卡的菜单发送。
        * 若低于Gamebase Android SDK 2.6.0，应从Gamebase控制台的**推送（旧）**选项卡发送推送。
    * GamebaseConfiguration.Builder.setFCMSenderId()现在不调用也无妨。
    * 调用GamebaseConfiguration.Builder.setTencentAccessKey()、 GamebaseConfiguration.Builder.setTencentAccessId()时，应清除API调用，并在build.gradle中如下声明。

```groovy
android {
    defaultConfig {
        ...
        // >>> For Tencent Push Notification
        manifestPlaceholders = [
            XG_ACCESS_ID : "1234567890",
            XG_ACCESS_KEY : "ABCDEFGHIJKL",
        ]
    }
}
```

## 2.4.4

### Unity

* Setting Tool已升级。
    * 文件夹结构更改，应将之前版本的SettingTool完全删除后重新安装。

## 2.2.2

### Unity

* GamebaseUnitySDKSettings类的**storeCodeAOS**变量名更改为**storeCodeAndroid**。
    * 若存在参考**storeCodeAOS**定义Store Code的代码或Prefab，则变量参考失败，因此请更改为**storeCodeAndroid**变量。

## 2.2.0

### Unity

* GamebaseMainActivity的Package Name已更改。
    * AndroidManifest.xml的MainActivity声明若未如下更改，则会发生崩溃。
    * **com.toast.gamebase.activity.GamebaseMainActivity** -> **com.toast.android.gamebase.activity.GamebaseMainActivity**

```xml
<manifest>
    ...
    <application>
    ...
        <activity android:name="com.toast.android.gamebase.activity.GamebaseMainActivity"
            android:launchMode="singleTask"
            android:configChanges="keyboard|keyboardHidden|screenLayout|screenSize|orientation"
            android:label="@string/app_name">
            <intent-filter>
                <action android:name="android.intent.action.MAIN" />
                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>
        </activity>
    ...
    </application>
    ...
</manifest>
```

## 2.1.0

### Common

#### Removed APIs

* 未使用的TransferKey功能已清除。
	* 若需要Guest账号迁移功能，请使用自Gamebase SDK 2.2.1起添加的[\[Game > Gamebase > Unity SDK使用指南 > 验证 > TransferAccount\]](./unity-authentication/#transferaccount)功能。
