# 자주 묻는 질문

## 엑셀 없이 구성원 여러 명을 한꺼번에 등록할 수 있나요? <a href="#bulk-upload-employee" id="bulk-upload-employee"></a>

Microsoft 엑셀 프로그램이 설치되어 있지 않다면, **구글 스프레드시트(Spreadsheet)**를 이용하세요!

1. [이 링크](https://docs.google.com/spreadsheets/d/1mG069G4AkPuLohTHB8bwX0okE9JjGmFUTS4Wj9VwYIg/edit?usp=sharing)를 눌러주세요.
2. \[파일 - 사본만들기]로 업로드 양식을 복사해주세요.
3. 양식에 맞춰 내용을 채워주세요. 행, 열이 변경되면 오류가 생기니 주의해주세요.
4. **\[파일 - 다운로드 - Microsoft Excel (.xlsx)]** 클릭해 다운로드 해주세요.
5. 이렇게 저장된 파일을 레몬베이스 [#undefined-1](management.md#undefined-1 "mention") 기능을 통해 업로드해주세요.

{% hint style="info" %}
💡 구글 로그인을 해야 사용할 수 있습니다.
{% endhint %}

![](<../../.gitbook/assets/레몬베이스 구성원 업로드 양식 스프레드시트.png>)

<table data-header-hidden data-full-width="false"><thead><tr><th></th><th data-hidden></th><th data-hidden></th></tr></thead><tbody><tr><td></td><td></td><td></td></tr></tbody></table>

## 구성원 엑셀 업로드가 안돼요 <a href="#error-bulk-upload-employee" id="error-bulk-upload-employee"></a>

구성원 엑셀 업로드에 실패하는 경우는 크게 다음과 같습니다.

* 평가권자로 지정한 사람이 구성원으로 등록되지 않은 경우
* 평가권자로 지정한 사람이 비활성화 되어 있는 경우
* 평가권자로 지정한 사람의 이메일 주소에 오타가 있는 경우

💡 평가권자로 지정한 사람이 구성원으로 등록되어 있지 않아 오류가 발생하는 경우가 가장 많습니다.

아래 방법을 똑같이 따라해 주세요!

1. \[ **=VLOOKUP(U4,E:E,1,FALSE)** ]를 복사하세요.
2. **비어있는 열의 4행**에 복사한 함수를 붙여넣기 하세요.
3.  아래 방향으로 드래그하여 셀을 선택하고 `Ctrl(Command)+D`를 눌러 함수를 일괄 적용해 주세요!

    ![](<../../.gitbook/assets/Untitled (4).gif>)

    평가권자의 이메일에 등록한 [zzz@lemonbase.com](mailto:zzz@lemonbase.com) 주소가 구성원의 이메일에 등록되어 있지 않은 경우
4. \#N/A 값 행의 평가권자의 이메일(U열)이 구성원의 메일(E열)에 등록되어 있는지, 오타는 없는지 확인해 주세요.



## 구성원 프로필 이미지 업로드가 안돼요 <a href="#error-upload-profile-image" id="error-upload-profile-image"></a>

Window 업데이트가 이루어지지 않거나 특정 백신을 사용하는 경우, 인증서 업데이트가 안 되는 경우가 있는데요. 이 때 구성원의 프로필 이미지 업로드가 안 되는 현상이 발생합니다.

구성원 프로필 이미지 업로드가 안 된다면, 먼저 아래 방법에 따라 인증서가 유효한지 확인해 주세요!

#### 인증서 유효 여부 확인하기

1.  아래 링크로 접속하여 주소창의 `자물쇠` 아이콘을 클릭해 주세요.

    (아래 링크로 접속했을 때 `Not Found` 가 뜨면 잘 접속하신 겁니다!)\


    [https://cdn.filestackcontent.com/](https://cdn.filestackcontent.com/)

    ![](<../../.gitbook/assets/Untitled (70).png>)
2.  아래 이미지의 네모 박스 영역을 클릭한 뒤 `인증서가 유효함` 으로 뜨는지 확인해 주세요.

    ![](<../../.gitbook/assets/Untitled (1) (2).png>)

    ![](<../../.gitbook/assets/Untitled (2) (1).png>)

위 이미지처럼 `인증서가 유효함`으로 뜨지 않는 경우, 아래 방법에 따라 진행해 주세요.

혹 `인증서가 유효함` 으로 뜨는데, 구성원 프로필 업로드가 안 되는 상황이시라면 [채팅](http://lemonbase.channel.io)을 통해 알려주세요.

#### 인증서가 유효하지 않을 경우 해결 방법

두 가지 인증서 설치 방법을 알려드릴게요. 차근차근 따라와 주세요!

#### 첫 번째 인증서 설치하기

1.  아래 사이트에 접속한 뒤, ISRG Root X1의 `der` 을 눌러 파일을 다운로드 받아주세요.

    [Chain of Trust](https://letsencrypt.org/certificates/)

    ![](<../../.gitbook/assets/Untitled (3) (4).png>)
2.  다운로드 파일에서 마우스 오른쪽 클릭 후 `인증서 설치`를 눌러주세요.

    ![](<../../.gitbook/assets/Untitled (4) (5).png>)
3.  `로컬 컴퓨터` 클릭 후 `다음` 버튼을 클릭해 주세요.

    ![](<../../.gitbook/assets/Untitled (5) (5).png>)
4.  `모든 인증서를 다음 저장소에 저장` > `찾아보기` > `신뢰할 수 있는 루트 인증 기관` > `확인` > `마침` 버튼을 눌러주세요.

    ![](<../../.gitbook/assets/Untitled (6) (1).png>)

![](<../../.gitbook/assets/Untitled (7) (2).png>)

5. 잠시 후 설치 관련 경고 문구 `보안 경고 : CA(인증 기관)로부터 다음을 위한 인증서를 설치하려고 합니다` 가 나오면 `예`를 눌러서 설치한 뒤 `가져오기를 완료했습니다` 메시지가 뜰 때까지 기다려 주세요.

#### 두 번째 인증서 설치하기

1.  아래 사이트에 접속한 뒤 `루트 인증서 자동 설치 exe 다운로드` 해주세요.

    [한국정보인증 SSL 기술지원](https://tech.signgate.com/demotest/SSL/index.html)

    ![](<../../.gitbook/assets/Untitled (8) (2).png>)

첫 번째 인증서와 두 번째 인증서 설치가 완료 되었다면 컴퓨터를 재부팅한 뒤 구성원 프로필 이미지 업로드가 되는지 확인해 주세요! 🙂

위와 같이 진행했는데, 구성원 프로필 업로드가 안 된다면 [채팅](https://lemonbase.channel.io/)으로 알려주세요.

문제 파악 후 해결에 도움을 드리겠습니다.





## 평가권자는 어떤 권한을 갖나요? <a href="#appraisal-leader-authority" id="appraisal-leader-authority"></a>

#### **리뷰**

평가권자는 팀원에 대해 아래와 같은 리뷰 권한이 생깁니다.

![](<../../.gitbook/assets/리뷰 권한.png>)

####

## 조직 리더는 어떤 권한을 갖나요? <a href="#organization-leader-authority" id="organization-leader-authority"></a>

레몬베이스 **목표** 기능을 사용하신다면, **조직 리더**를 꼭 지정해 주세요. (참고:[#undefined-2](organizations.md#undefined-2 "mention"))

#### 조직 리더로 지정되면, 아래의 목표 관리 권한을 갖습니다.

‘내 팀원 목표’ 메뉴를 확인할 수 있습니다.

![](<../../.gitbook/assets/내 팀원 목표.png>)

#### 조직 목표, 팀원이 담당하는 목표의 추가/수정/삭제/체크인에 대한 알림을 받을 수 있습니다.

![](<../../.gitbook/assets/목표 수정에 대한 알림.png>)

#### 어드민이 조직 리더에게 목표 수정/삭제/이동/체크인에 대한 권한을 줄 수 있습니다.

![](<../../.gitbook/assets/조직 리더 권한.png>)

구성원 관리 페이지에서 조직 리더를 업로드하고, 목표 기능을 사용해 주세요!
