# SSO 설정하기

레몬베이스의 SSO 서비스는 SAML (Security Assertion Markup Language) 2.0 표준을 기반으로 합니다.

SSO (Single Sign-On)를 사용하면 구성원이 레몬베이스를 위한 별도의 사용자 ID와 패스워드를 유지할 필요가 없습니다. 또한, 사용 권한을 가진 애플리케이션에 대해 1회 사용자 인증을 하면 됩니다. 사용자가 세션을 실행하는 동안 애플리케이션을 전환하더라도 다시 인증할 필요가 없습니다.

보안 관점에서는 아래와 같은 장점이 있습니다.

* 시스템에 액세스할 수 있는 사람을 한 곳에서 쉽게 관리할 수 있습니다.
* Identity와 인증 데이터가 외부에 있어 데이터 침해에 대한 위험이 줄어듭니다.
* 더 나은 암호 정책을 사용할 수 있어 암호 관리 전략 및 교육의 필요성이 줄어듭니다.
* 더 빠르게 로그인할 수 있고 비밀번호 분실이 줄어들어 사용성이 개선됩니다.

## SSO 설정하기

**레몬베이스는 SAML 2.0 ID 제공 역할을 할 수 있는 외부 시스템과 연동할 수 있습니다.**

{% hint style="info" %}
작업자가 레몬베이스에 **‘연동 관리’ 어드민 권한**이 있어야 SSO 연동 작업이 수월합니다.
{% endhint %}

### 구글 워크스페이스 <a href="#sso-google-workspace" id="sso-google-workspace"></a>

Google Workspace와의 SAML SSO 연동을 통해 구성원은 새 비밀번호를 설정하지 않고도 Google 계정으로 레몬베이스에 로그인할 수 있습니다.

다음은 애플리케이션 생성 및 사용자 액세스 활성화에 대한 단계별 가이드입니다.

#### **1단계: 구글 워크스페이스 관리 콘솔에서 맞춤 SAML 앱을 만드세요**

1. [https://admin.google.com/에서](https://admin.google.com/%EC%97%90%EC%84%9C) [최고 관리자 권한](https://support.google.com/a/answer/2405986#super\_admin)으로 관리 콘솔에 로그인하세요.
2. **관리 콘솔 홈페이지 > 앱 > 웹 및 모바일 앱 > 앱 추가 > 맞춤 SAML 앱 추가**를 클릭하세요.
3. 앱 세부정보 페이지에서 사용자 지정 앱의 이름을 “Lemonbase”로 입력하세요.
4. ‘계속’을 클릭해서 다음 화면으로 진행하세요. (설명과 아이콘은 옵션)

#### **2단계: 레몬베이스에서 SSO를 설정하세요**

1. **레몬베이스 홈 > 어드민 탭 > 설정 - 연동 관리 > SSO 로그인 연동** 페이지로 이동하세요. ([설정 페이지](https://lemonbase.com/app/admin/integration/sso))
2. SSO URL, 엔티티 ID, 그리고 인증서를 **구글 워크스페이스**에서 각 각 복사해서 **레몬베이스 SSO 로그인 연동** 페이지 내에 있는 각 영역에 붙여 넣고 우측 상단의 저장을 클릭하세요.
   1. 구글 ‘SSO URL’ → 레몬베이스 ‘SSO URL (IDP URL)’
   2. 구글 ‘엔티티 ID’ → 레몬베이스 ‘엔티티 ID’
   3. 구글 ‘인증서’ → 레몬베이스 ‘인증서’\
      <img src="../../../.gitbook/assets/image (289).png" alt="" data-size="original">![](<../../../.gitbook/assets/image (130).png>)
3. 구글 워크스페이스에서 '계속'을 클릭하세요.

#### **3단계: 구글 워크스페이스에 SAML 설정을 마무리하세요**

1.  레몬베이스 SSO 로그인 연동 페이지에서 회신 URL (ACS URL)과 메타데이터 (엔티티 ID)를 각 각 복사해서 구글 워크스페이스의 ACS URL과 엔티티 ID 칸에 붙여 넣으세요.\


    <figure><img src="../../../.gitbook/assets/image (173).png" alt="" width="563"><figcaption></figcaption></figure>
2. ‘이름 ID 형식’ 드롭다운에서 **‘EMAIL’**을 선택하세요.
3. ‘이름 ID’ 드롭다운에서 ‘**Basic Information > Primary email’** 선택하고 하단에 계속 버튼을 클릭하세요.\
   ![](<../../../.gitbook/assets/image (292).png>)![](<../../../.gitbook/assets/image (245).png>)
4. ‘매핑 추가’를 클릭하고 Google 디렉터리 속성은 ‘Primary email’, 앱 속성에는 ‘Email’이라고 입력하세요.\
   ![](<../../../.gitbook/assets/image (254).png>)![](<../../../.gitbook/assets/image (133).png>)
5. 마침을 클릭하여 SAML 앱 설정을 완료하세요.
6.  마지막으로, 생성된 앱에서 사용자 액세스를 클릭하시고 ‘모든 사용자에 사용하도록 설정’을 선택하고 저장하세요.\


    <figure><img src="../../../.gitbook/assets/image (175).png" alt="" width="563"><figcaption></figcaption></figure>

#### **4단계: 레몬베이스에서 SSO를 활성화하세요**

1. ‘SAML SSO 활성화’만 먼저 설정하고 SSO 로그인이 잘 작동하는지 확인하세요.
2. SSO 로그인이 문제 없이 잘 작동하는 것을 확인하신 이후에 보안상의 이유로 모든 사용자가 SSO로만 로그인을 해야한다면 ‘모든 사용자 SAML SSO 강제 로그인’을 설정하세요. 설정이 잘 못 되었을 경우 어드민도 로그인을 할 수 없게되므로 IT 또는 보안팀과 작동에 문제 없는지 최종 확인 후 설정을 마무리하세요.

추가 설명이 필요한 경우 Google 웹사이트의 설명을 함께 참고해 주세요.

* [Google을 ID 공급자로 사용하여 SSO 설정](https://support.google.com/a/topic/7556794)
* [사용자 지정 앱으로 SAML 기반 SSO 설정](https://support.google.com/a/topic/7559288)
* [사용자 지정 SAML 애플리케이션 설정](https://support.google.com/a/answer/6087519)



### 원로그인 <a href="#sso-one-login" id="sso-one-login"></a>

레몬베이스와 원로그인 연동을 통해 사용자별 접근 권한 관리가 가능해집니다.

다음은 SSO 연동을 위한 애플리케이션 생성 및 사용자 접근 권한 부여에 대한 단계별 가이드입니다.

#### **1단계: 원로그인에서 SAML Custom Connector를 생성하세요**

1. [원로그인](https://app.onelogin.com/login)에 로그인하고 **administration** 메뉴로 이동하세요.
2.  Applications 탭에서 Applications 메뉴로 이동한 후 ‘**Add App**’을 클릭하세요.\


    <figure><img src="../../../.gitbook/assets/image (132).png" alt="" width="563"><figcaption></figcaption></figure>
3.  검색창에서 SAML Custom Connector (advanced)를 검색하고 클릭하세요.\


    <figure><img src="../../../.gitbook/assets/image (290).png" alt="" width="563"><figcaption></figcaption></figure>
4.  Configuration에서 Display Name은 Lemonbase로 설정하고 저장하세요.\


    <figure><img src="../../../.gitbook/assets/image (277).png" alt="" width="563"><figcaption></figcaption></figure>
5. 왼쪽에 새롭게 생긴 탭 중에 SSO 탭으로 이동한 뒤 새로운 브라우저 창을 열고 2단계를 진행하세요.



#### **2단계: 레몬베이스에서 SSO를 설정하세요**

1. `어드민 > 설정 > 연동 관리 > SSO 로그인 연동` 페이지에 접속하세요 ([설정 페이지](https://lemonbase.com/app/admin/integration/sso))
2.  원로그인 SSO 탭에서 아래와 같이 진행하세요.

    1.  SAML Signature Algorithm을 ‘**SHA-256**’으로 설정하고 우측 상단의 Save 버튼을 눌러 저장하세요.\


        <figure><img src="../../../.gitbook/assets/image (281).png" alt="" width="375"><figcaption></figcaption></figure>
    2. 다시 SSO 탭으로와서 ‘Issuer URL’을 복사하고 레몬베이스 SSO 로그인 연동 페이지 내에 ‘IDP 상세 정보 > 메타데이터 URL (Issuer ID)’ 영역에 붙여넣으세요.



#### **3단계: 원로그인에서 SAML 설정을 마무리하세요**

1.  원로그인에서 Configuration 탭으로 이동한 후 아래와 같이 설정하세요.\


    <figure><img src="../../../.gitbook/assets/image (248).png" alt="" width="563"><figcaption></figcaption></figure>

* **레몬베이스 SSO 로그인 연동** 페이지에서
  * 1\) **‘메타데이터 (엔티티 ID)’** 값을 복사한 후 **‘Audience (EntityID)’** 영역에 붙여넣으세요.
  * 2\) **‘회신 URL (ACS URL)’** 값을 복사한 후 **‘Recipient’, ‘ACS (Consumer) URL’** 두 영역에 붙여넣으세요.
  * 3\) **‘ACS (Consumer) URL Validator’** 영역에 아래 값을 붙여넣으세요.
    * `[-a-zA-Z0-9@:%.*\\+~#=]{2,256}\\.[a-z]{2,6}\\b([-a-zA-Z0-9@:%*\\+.~#?&//=]*)`
  * 4\) **‘로그아웃 URL (SLS URL)’** 값을 복사한 후 **‘Single Logout URL’** 영역에 붙여넣으세요.

2.  원로그인 Configuration 탭에서 하단으로 스크롤 후 SAML initiator를 **‘Service Provider’**로 설정해주세요.\


    <figure><img src="../../../.gitbook/assets/image (135).png" alt="" width="375"><figcaption></figcaption></figure>
3.  원로그인 Parameters 탭으로 이동해서 + 버튼을 클릭하여 아래와 같이 새로운 필드를 생성하세요.\


    <figure><img src="../../../.gitbook/assets/image (263).png" alt="" width="563"><figcaption></figcaption></figure>

* ‘Field name’에 ‘Email’이라고 입력 후 Flags에서 ‘Include in SAML assertion’을 체크하고 저장한 뒤, Value 드롭다운 메뉴에서 ‘Email’을 선택하고 저장하세요.\
  ![](<../../../.gitbook/assets/image (266).png>)![](<../../../.gitbook/assets/image (265).png>)**ㅍ**



#### **4단계: 원로그인에서 레몬베이스 앱(SAML Custom Connector) 을 접근할 수 있는 사용자를 지정하세요**

1.  Users 탭에서 Users 메뉴를 선택하세요.\


    <figure><img src="../../../.gitbook/assets/image (131).png" alt="" width="563"><figcaption></figcaption></figure>
2. 레몬베이스에 SSO를 통해 접속할 유저를 클릭하고 Applications 탭으로 이동하세요.
3.  우측에 ‘+’를 클릭하시고 Lemonbase 앱을 선택 후 Continue를 클릭하세요. **‘Allow the user to sign in’**이 체크되어 있는지 확인 후 저장하세요.\


    <figure><img src="../../../.gitbook/assets/image (275).png" alt="" width="563"><figcaption></figcaption></figure>



    <figure><img src="../../../.gitbook/assets/image (239).png" alt="" width="375"><figcaption></figcaption></figure>

#### 5**단계: 레몬베이스에서 SSO를 활성화하세요**

1. ‘SAML SSO 활성화’만 먼저 설정하고 SSO 로그인이 잘 작동하는지 확인하세요.
2. SSO 로그인이 작동하는 것을 확인한 이후 보안상의 이유로 모든 사용자가 SSO로만 로그인을 해야한다면 **‘모든 사용자 SAML SSO 강제 로그인’**을 설정하세요. 설정이 잘 못 되었을 경우 어드민도 로그인을 할 수 없게되므로 IT 또는 보안팀과 SSO 설정에 문제가 없는지 최종 확인 후 설정을 마무리하세요.



### 옥타 <a href="#sso-okta" id="sso-okta"></a>

레몬베이스와 옥타의 연동을 통해 사용자 관리 접근 권한 관리가 가능해집니다.

다음은 SSO 연동을 위한 애플리케이션 생성 및 사용자 접근 권한 부여에 대한 단계별 가이드입니다.

#### **1단계: 옥타에서 App Integration을 생성하세요**

1. [옥타](https://app.okta.com/)에 로그인하고 **관리자 메뉴**로 이동하세요.
2.  왼쪽 사이드 패널에서 **Applications > Applications** 메뉴로 이동한 후 ‘Create App Integration’ 버튼을 클릭하세요.

    <figure><img src="../../../.gitbook/assets/image (242).png" alt="" width="563"><figcaption></figcaption></figure>
3. Sign-in method로 ‘SAML 2.0’을 선택하고 ‘Continue’를 클릭하세요.
4. General Settings 탭에서 App name은 Lemonbase로 설정하고 다음으로 진행하세요.
5. 옥타에서 Configure SAML을 진행하기 앞서 **레몬베이스 홈 > 어드민 탭 > 설정 - 연동 관리 > SSO 로그인 연동** 페이지로 이동하세요. ([설정 페이지](https://lemonbase.com/app/admin/integration/sso))
6. 다음의 동작을 옥타 **‘Configure SAML 탭’**에서 진행하세요.
   1. 레몬베이스 SSO 로그인 연동 페이지에서 **‘회신 URL (ACS URL)’** 값을 복사한 후 **‘Single sign-on URL’** 영역에 붙여넣으세요. 하단에 **‘Use this for Recipient URL and Destination URL’**을 체크하세요.
   2. 레몬베이스 SSO 로그인 연동 페이지에서 **‘메타데이터 (엔티티 ID)’** 값을 복사한 후 **‘Audience URI (SP Entity ID)’** 영역에 붙여넣으세요.
   3.  **‘Attribute Statements’**에 아래와 같이 Name, Value 필드에 **‘Email’**이라고 입력하세요.\


       <figure><img src="../../../.gitbook/assets/image (293).png" alt="" width="563"><figcaption></figcaption></figure>
7. 하단으로 스크롤해서 **‘Next**’를 클릭하여 Feedback 탭으로 이동하세요.
8. ‘I'm an Okta customer adding an internal app’을 선택하고 **‘Finish’**를 클릭하여 앱 생성을 마무리하세요.
9.  새롭게 생긴 **‘Sign On’** 탭으로 이동한 뒤 새로운 브라우저 창을 열고 2단계를 진행하세요.\


    <figure><img src="../../../.gitbook/assets/image (286).png" alt="" width="563"><figcaption></figcaption></figure>

#### **2단계: 레몬베이스에서 SSO를 설정하세요**

1. **레몬베이스 홈 > 어드민 탭 > 설정 - 연동 관리 > SSO 로그인 연동** 페이지로 이동하세요 ([설정 페이지](https://lemonbase.com/app/admin/integration/sso))
2.  레몬베이스 SSO 설정에 필요한 값을 복사해오기 위해 옥타 Sign On 탭 하단으로 스크롤하세요. **‘SAML Signing Certificates’** 영역에서 **‘SHA-2 Type’** 우측에 **‘Actions’** 버튼을 클릭하고 **‘View IdP metadata’** 위에서 우클릭하고 링크 주소를 복사하세요.\


    <figure><img src="../../../.gitbook/assets/image (287).png" alt="" width="563"><figcaption></figcaption></figure>
3. 레몬베이스 내에 ‘메타데이터 URL (Issuer ID)’ 영역에 붙여넣고 저장하세요.



#### **3단계: 옥타에서 Lemonbase 앱(Okta Application) 을 접근할 수 있는 사용자를 추가하세요**

1.  Applications 메뉴에서 Lemonbase 앱 우측의 설정 아이콘을 클릭하고 ‘Assign to Users’를 클릭하세요.\


    <figure><img src="../../../.gitbook/assets/image (136).png" alt="" width="563"><figcaption></figcaption></figure>
2.  Lemonbase 앱을 접근할 사용자를 ‘Assign’ 하고 ‘Save and Go Back’을 클릭해서 저장하세요.\


    <figure><img src="../../../.gitbook/assets/image (294).png" alt="" width="563"><figcaption></figcaption></figure>

#### **4단계: 레몬베이스에서 SSO를 활성화하세요**

1. 레몬베이스 SSO 로그인 연동 페이지에서 ‘SAML SSO 활성화’만 먼저 설정하고 SSO 로그인이 잘 작동하는지 확인하세요.
2. 잘 작동하는 것을 확인한 이후 보안상의 이유로 모든 사용자가 SSO로만 로그인을 해야한다면 ‘모든 사용자 SAML SSO 강제 로그인’을 설정하세요. 잘 못 설정시 어드민도 로그인을 할 수 없게되므로 IT 또는 보안팀과 SSO 구성과 작동에 문제 없는지 최종 확인 후 설정을 마무리하세요.



#### 💡 **고급) 옥타에서 Single Logout URL 설정하기**

1. 레몬베이스 Certification 가져오기
   1.  레몬베이스 어드민 [SAML SSO 연동 페이지](https://lemonbase.com/app/admin/integration/saml)에서 제공되는 Metadata URL을 주소창이나 Postman으로 요청하여 XML 내용을 확인하세요.\


       <figure><img src="../../../.gitbook/assets/image (244).png" alt="" width="563"><figcaption></figcaption></figure>
   2.  tag 중 X509Certificate에 해당하는 값을 tag 제외하고 복사하세요.\


       <figure><img src="../../../.gitbook/assets/image (270).png" alt=""><figcaption></figcaption></figure>
   3. 텍스트 작성기 또는 노트패드를 열고 header → 복사한 내용 → footer tag를 차례로 붙인 후, `{인증서_이름}.crt` 로 저장하세요
      1. header
         * `-----BEGIN CERTIFICATE-----`
         * footer
           * `-----END CERTIFICATE-----`
         * 저장 전 모습
           * `-----BEGIN CERTIFICATE-----` \
             `b에서 복사한 값` \
             `-----END CERTIFICATE-----`   \

   4. 생성된 crt 파일을 아래와 같이 업로드\

2. Certification 업로드하기
   1.  SAML Settings 하단에 Show Advanced Settings를 클릭하세요.\


       <figure><img src="../../../.gitbook/assets/image (268).png" alt="" width="375"><figcaption></figcaption></figure>
   2.  위에서 만든 crt 파일을 Signature Certificate으로 등록하세요.\


       <figure><img src="../../../.gitbook/assets/image (256).png" alt="" width="375"><figcaption></figcaption></figure>
3. Enable Single Logout을 체크하고 Single Logout URL에는 레몬베이스 [SAML 연동 페이지](https://lemonbase.com/app/admin/integration/saml)에서 SAML 구성 정보 > 로그아웃 URL 을 복사해서 붙여넣으세요

### 애져(Azure) <a href="#sso-azure" id="sso-azure"></a>

Azure와의 SAML SSO 연동을 통해 구성원은 새 비밀번호를 설정하지 않고도 Azure 계정으로 레몬베이스에 로그인할 수 있습니다. 다음은 애플리케이션 생성 및 사용자 액세스 활성화에 대한 단계별 가이드입니다.

#### **1단계: Azure Active Directory에서 SAML Toolkit을 설정하세요**

1. [Azure 포탈](https://portal.azure.com/#home)에 SSO를 적용하고자 하는 회사 계정으로 로그인하세요.
2.  왼쪽 탐색 창을 클릭하고 **“Azure Active Directory”** 서비스를 선택하세요.\


    <figure><img src="../../../.gitbook/assets/image (257).png" alt="" width="563"><figcaption></figcaption></figure>
3. 엔터프라이즈 애플리케이션으로 이동한 다음, 검색 창에 “saml tool”을 입력하세요. 검색 결과로 나오는 “Azure AD SAML Toolkit”을 클릭하세요.\
   ![](<../../../.gitbook/assets/image (283).png>)![](<../../../.gitbook/assets/image (255).png>)\

4. 인식하기 쉽도록 이름을 설정하시고 “만들기”를 클릭해서 설정으로 넘어가세요. (1분 정도 소요됩니다.)
   1.  가이드에서는 default 상태 그대로 “Azure AD SAML Toolkit” 이름을 사용했습니다.\


       <figure><img src="../../../.gitbook/assets/image (134).png" alt="" width="563"><figcaption></figcaption></figure>
5. 개요 화면에서 “2. Single Sign On 설정”을 클릭하고 다음 화면에서 Single Sign-On 방법으로 “SAML”을 선택하세요.\
   ![](<../../../.gitbook/assets/image (276).png>) ![](<../../../.gitbook/assets/image (258).png>)

![](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/6bf45423-b444-4e0a-8244-38e0a6c42139/Untitled.png)

6. **“1) 기본 SAML 구성”** 섹션에서 편집을 클릭하고 **“레몬베이스 SAML 구성 정보”** ([연동 관리 > SAML SSO](https://lemonbase.com/app/admin/integration/saml))를 각 각 복사해서 Azure 내 **“기본 SAML 구성”**의 각 영역에 붙여 넣고 저장하세요.\


<figure><img src="../../../.gitbook/assets/image (240).png" alt="" width="563"><figcaption></figcaption></figure>

1. 레몬베이스 “메타데이터 (엔티티 ID)” → Azure “식별자(엔터티 ID)”
2. 레몬베이스 “회신 URL (ACS URL)” → Azure “회신 URL(Assertion Consumer Service URL)”
3. [https://lemonbase.com/](https://lemonbase.com/) → 레몬베이스의 홈페이지 주소를 Azure “로그온 URL”, “릴레이 상태” 입력 칸에 각 각 복사 붙여넣기 하세요.
4. 레몬베이스 “로그아웃 URL (SLS URL)” → Azure “로그아웃 URL(선택 사항)”



7. **“2) 특성 및 클레임”**에서 편집을 클릭하고 고유한 사용자 ID를 이메일 값으로 변경하세요.\
   레몬베이스 로그인 시 사용자의 이메일 값이 사용자 ID로 사용됩니다.\


<figure><img src="../../../.gitbook/assets/image (272).png" alt="" width="563"><figcaption></figcaption></figure>

* “고유한 사용자 Id”를 클릭하고 원본 특성 드롭다운 메뉴에서 “user.mail”을 선택하고 저장하세요.\
  ![](<../../../.gitbook/assets/image (122).png>)![](<../../../.gitbook/assets/image (247).png>)

#### **2단계: 레몬베이스에서 SSO를 설정하세요**

1.  Azure에서 하단으로 스크롤해서 **“3) SAML 인증서”** 영역을 찾고 **“앱 페더레이션 메타데이터 URL”**을 복사하세요.\


    <figure><img src="../../../.gitbook/assets/image (278).png" alt="" width="563"><figcaption></figcaption></figure>
2. [레몬베이스 SSO 로그인 연동](https://lemonbase.com/app/admin/integration/saml) 페이지 내 IDP 상세 정보 아래 “메타데이터 URL (Issuer ID)” 영역에 붙여넣기 하고 저장하세요.\
   ![](<../../../.gitbook/assets/image (262).png>)



#### 3**단계: Azure에서 레몬베이스에 로그인 할 수 있는 사용자 및 그룹을 할당하세요**

1.  개요 화면에서 **“1. 사용자 및 그룹 할당”**을 클릭하세요.\


    <figure><img src="../../../.gitbook/assets/image (284).png" alt="" width="563"><figcaption></figcaption></figure>
2. “사용자/그룹 추가”을 클릭 후 “선택된 항목 없음”을 클릭하고 사용자 및 그룹을 선택하고 할당하세요.\
   ![](<../../../.gitbook/assets/image (269).png>)![](<../../../.gitbook/assets/image (252).png>)\
   ![](<../../../.gitbook/assets/image (261).png>)![](<../../../.gitbook/assets/image (282).png>)



#### 4**단계: 레몬베이스에서 SSO를 활성화하세요**

1.  ‘SAML SSO 활성화’만 먼저 설정 및 저장한 후 SSO 로그인이 잘 작동하는지 확인하세요.\


    <figure><img src="../../../.gitbook/assets/image (249).png" alt="" width="563"><figcaption></figcaption></figure>
2. SSO 로그인이 문제 없이 잘 작동하는 것을 확인하신 이후에 보안상의 이유로 모든 사용자가 SSO로만 로그인을 해야한다면 ‘모든 사용자 SAML SSO 강제 로그인’을 설정하세요. 설정이 잘 못 되었을 경우 어드민도 로그인을 할 수 없게되므로 IT 또는 보안팀과 작동에 문제 없는지 최종 확인 후 설정을 마무리하세요.

추가 설명이 필요한 경우 마이크로소프트 웹사이트의 설명을 함께 참고하세요.

* [자습서: Azure AD SAML Toolkit과 Azure AD SSO 통합](https://learn.microsoft.com/ko-kr/azure/active-directory/saas-apps/saml-toolkit-tutorial)





## FAQ <a href="#sso-faq" id="sso-faq"></a>

**Q. 가이드에 따라서 SSO 설정을 완료했는데 SSO 로그인이 안돼요**

크게 네 가지 사항에 대해 확인이 필요합니다

1. 외부 시스템 (구글 워크스페이스, 원로그인, 옥타, Azure 등)에 해당 계정이 등록되어있고 액세스가 허용되었는지
2. 레몬베이스 내에 해당 계정이 생성되었는지, 비활성화 상태는 아닌지
3. 레몬베이스 내에 SSO가 활성화되었고 설정이 잘 되었는지 (내부 IT팀 또는 개발팀과 확인 필요)
4. 구성원에게 가입 초대 (구성원 관리) 메일을 보냈고 가입 메일을 통해 최초 SSO 로그인을 진행했는지\


**Q. SSO 설정 후에 아래와 같은 에러 메시지가 뜨고 있어요**

`{"error":{"message":"SAML 인증에 실패하였습니다. (사유: ['invalid_response'], 상세 사유: There is no AttributeStatement on the Response)"}}`

**Parameter 또는 속성 매핑** 설정이 잘 못 되었을 가능성이 높습니다. 가이드에서 해당 부분이 잘 설정되었는지 다시 한 번 확인해주세요\


**Q. 구글 계정으로 SSO 로그인을 하는데 다른 사람 계정으로 로그인이 되고 있어요**

Chrome을 사용하고 계신다면 우측 상단 프로필 영역에서 다른 사람 계정으로 로그인되어있는지 확인해주세요. 만약 그렇다면 [로그아웃](https://support.google.com/chrome/answer/9159867?hl=ko-GB\&co=GENIE.Platform%3DDesktop)한 후 다시 SSO 로그인을 시도하세요.\


**Q. SSO를 비활성화 하기 전에 주의해야할 사항이 있나요?**

SSO를 비활성화 하실 경우 구성원들은 이메일/패스워드로 로그인해야 합니다. 아직 비밀번호를 설정하지 않은 구성원은 새롭게 비밀번호 설정이 필요합니다. 비밀번호를 설정하기 위해서는 두 가지 방법이 있습니다.

1. 아직 SSO가 활성화되어 있는 경우, 구성원은 레몬베이스에 로그인 후 우측 상단 프로필에서 **프로필 > 프로필 관리 > 계정 설정**을 통해 비밀번호를 세팅할 수 있습니다.

![](<../../../.gitbook/assets/Untitled (12) (4).png>)

![](<../../../.gitbook/assets/Untitled (13) (2).png>)

2. 로그인하지 않은 상태에서도 구성원은 비밀번호를 설정할 수 있습니다. 레몬베이스 홈에서 [로그인 > 비밀번호 찾기](https://lemonbase.com/password-reset)를 진행하면 구성원의 메일 계정을 통해 비밀번호를 새롭게 설정 할 수 있습니다.

![](<../../../.gitbook/assets/Untitled (14) (2).png>)

**Q. SSO 로그인만 허용 시 가입 절차**

1. 초대 메일

![](<../../../.gitbook/assets/Untitled (15) (4).png>)

2. 가입 화면

![](<../../../.gitbook/assets/스크린샷 2023-04-10 오후 5.47.30.png>)

3. 계정 선택

![](<../../../.gitbook/assets/스크린샷 2023-04-10 오후 5.48.25.png>)

