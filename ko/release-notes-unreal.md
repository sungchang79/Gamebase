## Game > Gamebase > 릴리스 노트 > Unreal

### 2.33.1 (2022. 02. 22.)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v2.33.1/GamebaseSDK-Unreal.zip)

#### 버그 수정
* iOS 빌드 시 발생하는 오류를 수정했습니다.

### 2.33.0 (2022.01.25)

[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v2.33.0/GamebaseSDK-Unreal.zip)

#### 기능 추가
* '결제 어뷰징 자동 해제' 기능이 추가되었습니다.
    * [Game > Gamebase > Unreal SDK 사용 가이드 > 인증 > GraceBan](./unreal-authentication/#graceban)
    * 결제 어뷰징 자동 해제 기능은 결제 어뷰징 자동 제재로 이용 정지가 되어야 할 사용자가 '이용 정지 유예 상태' 후 이용 정지가 되도록 합니다.
    * '이용 정지 유예 상태'일 경우, 설정한 기간 내에 이용 정지 해제 조건을 모두 만족하면 정상적으로 플레이할 수 있습니다.
    * 기간 내에 조건을 충족하지 못하면 이용이 정지됩니다.
* 결제 어뷰징 자동 해제 기능을 사용하는 게임은 로그인 후 항상 AuthToken.member.graceBanInfo API 값을 확인하고, null이 아닌 유효한 GraceBanInfo 객체를 리턴한다면 해당 유저에게 이용 정지 해제 조건, 기간 등을 안내해야 합니다.
    * 이용 정지 유예 상태인 유저의 게임 내 접근 제어는 게임에서 처리해야 합니다.
* 강제 매핑 시 IdP 로그인을 한 번 더 시도해야 하는 불편함을 개선한 새로운 강제 매핑 API가 추가되었습니다.
    * [Game > Gamebase > Unreal SDK 사용 가이드 > 인증 > Mapping > Add Mapping Forcibly](./unreal-authentication/#add-mapping-forcibly)
* Gamebase.AddMapping() 호출 후 AUTH_ADD_MAPPING_ALREADY_MAPPED_TO_OTHER_MEMBER(3302) 에러가 발생했을 때, 해당 계정으로 로그인을 할 수 있는 API가 추가되었습니다.
    * [Game > Gamebase > Unreal SDK 사용 가이드 > 인증 > Mapping > Change Login with ForcingMappingTicket](./unreal-authentication/#change-login-with-forcingmappingticket)
* GamebaseEventHandler의 GamebaseEventCategory에 **GamebaseEventCategory::ServerPushAppKickOutMessageReceived** 타입이 추가되었습니다.
    * 이 이벤트의 활용 방법은 다음 문서를 참고하시기 바랍니다.
    * [Game > Gamebase > Unreal SDK 사용 가이드 > ETC > Additional Features > Gamebase Event Handler > Server Push](./unreal-etc/#server-push)
* GamebaseEventHandler의 GamebaseEventCategory에 **GamebaseEventCategory::LoggedOut** 타입이 추가되었습니다.
    * Gamebase Access Token이 만료되어 로그인이 필요할 때 동작합니다.
    * [Game > Gamebase > Unreal SDK 사용 가이드 > ETC > Additional Features > Gamebase Event Handler > Logged Out](./unreal-etc/#logged-out)
* 공통 약관 창의 설정을 변경할 수 있는 신규 API가 추가되었습니다.
    * [Game > Gamebase > Unreal SDK 사용 가이드 > UI > Terms > showTermsView](./unreal-ui/#showtermsview)

#### 기능 개선/변경
* 오류 코드 추가 및 변경
    * GamebaseErrorCode::UNKNOWN_ERROR 에러에 매핑된 오류 코드를 999에서 9999로 변경하였습니다.
    * 오류 코드 999에 매핑한 GamebaseErrorCode::SOCKET_UNKNOWN_ERROR 에러를 새로 추가하였습니다.
    
#### 플랫폼별 변경 사항
* [Gamebase Android SDK 2.33.0](./release-notes-android/#2330-20220125)
* [Gamebase iOS SDK 2.33.0](./release-notes-ios/#2330-20220125)

### 2.26.1 (2021.11.23)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v2.26.1/GamebaseSDK-Unreal.zip)

#### 버그 수정
* GamebaseDisplayLanguageCode 핀란드어 오타 수정
    * Finish → Finnish

### 2.26.0 (2021.09.28)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v2.26.0/GamebaseSDK-Unreal.zip)

#### 기능 추가
* 공통 약관 기능 추가
    * 약관 WebView를 여는 API 추가
    * 약관 리스트 및 유저별 동의 여부를 조회하는 API 추가
    * 유저별 약관 동의 여부를 Gamebase 서버에 저장하는 API 추가

#### 기능 개선/변경
* 고객 센터 타입이 TOAST 조직 상품(Online Contact)인 경우 로그인을 하지 않아도 고객 센터가 표시되도록 변경
* 내부 론칭 URL 변경
* Gamebase에서 Android multidex 적용 제거

### 2.19.2 (2021.06.29)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v2.19.2/GamebaseSDK-Unreal.zip)

#### 버그 수정
* 이미지 공지 ShowImageNotices API 호출 시 onEventCallback을 등록하지 않는 경우 닫기 버튼을 눌렀을 때 크래시가 발생하는 문제 수정
* Android 설정 툴 - Enable Hangame, Enable Weibo가 정상 동작하지 않는 문제 수정

### 2.19.1 (2021.02.09)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v2.19.1/GamebaseSDK-Unreal.zip)

#### 버그 수정
* Unity 빌드 중 제외되는 파일이 생길 때 발생하는 컴파일 오류 수정

### 2.19.0 (2021.01.26)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v2.19.0/GamebaseSDK-Unreal.zip)

#### 기능 추가
* SDK 배포: 2.16.0 ~ 2.19.0 누적된 내역 반영
    * [Android 설정 툴](https://docs.toast.com/ko/Game/Gamebase/ko/unreal-started/#android-settings) 제공: Gamebase_Android_UPL.xml 파일을 수정하는 대신 설정 툴을 사용바랍니다.
    * 고객 센터 기능 추가    
    * 인증 추가: Hangame, Weibo
    * Galaxy 스토어 추가
    * 결제 아이템 정보에 지역화된 상품 정보 추가: localizedTitle, localizedDescription
    * Android 설정 툴 제공
    * Unreal 4.26 지원
    
### 2.15.0 (2020.10.27)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v2.15.0/GamebaseSDK-Unreal.zip)

#### 기능 추가
* Unreal SDK 기능 추가: SDK 2.15.0
    * 기존의 모든 이벤트 시스템을 통합하는 GamebaseEventHandler 추가
        * ServerPush, Observer 기능을 포함하고 있고, 프로모션 결제 이벤트 및 푸시 이벤트 확인 가능
    * API 추가
        * 상품 ID로 결제 요청하고 추가 정보(UserPayload)를 입력해 결제 완료 시 확인 가능한 결제 API 추가
        * 이미지 공지 표시: showImageNotices
        * Push 토큰 정보 확인: queryTokenInfo
    * 푸시 토큰 등록 시 NotificationOption 설정으로 앱이 포그라운드(foreground) 상태에서도 푸시 알림을 받을 수 있도록 기능 추가
    * WebViewConfiguration contentMode 설정 추가
    
#### 기능 개선/변경
* [SDK] 2.15.0
    * (Unreal) TOAST SDK 업데이트: Android(0.23.0), iOS(0.26.0), Unity(0.21.0)    

#### 버그 수정
* [SDK] 2.15.0    
    * (Unreal) 결제 모듈에 ProGuard 선언이 누락된 오류 수정

### 2.9.1 (2020.08.25)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v2.9.1/GamebaseSDK-Unreal.zip)

#### 기능 추가
* [SDK] 2.9.1
    * (Unreal) Unreal 4.22 ~ 4.25 지원
    * (Unreal) PLCrashReporter 이슈 지원: [가이드](http://docs.toast.com/ko/Game/Gamebase/ko/unreal-started/#ios-settings)

#### 기능 개선/변경
* [SDK] 2.9.1
    * (Unreal) iOS Plugin 내부 Gamebase SDK for iOS 버전 업데이트(2.9.1)
    * (Unreal) UObject 레퍼런싱 처리가 누락된 부분을 수정  
   
### 2.9.0 (2020.05.12)
[SDK Download](https://static.toastoven.net/toastcloud/sdk_download/gamebase/v2.9.0/GamebaseSDK-Unreal.zip)

#### 기능 추가
* [SDK] 2.9.0
    * (Unreal) SDK 신규 배포
