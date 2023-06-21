# 템플릿 관리

{% hint style="info" %}
💡 템플릿은 **리뷰 항목**과 **질문** 양식을 의미합니다.&#x20;

&#x20;   템플릿을 미리 만들어 두면 리뷰를 진행할 때마다 불러올 수 있습니다.
{% endhint %}

## 템플릿 만들기 <a href="#make-review-template" id="make-review-template"></a>

`어드민` > `템플릿 관리` 에서 새로운 템플릿을 만들어 보세요.

![](<../../.gitbook/assets/Untitled (13) (3).png>)

{% hint style="info" %}
💡 **’Lemonbase 제공’ 템플릿**에는 다양한 목적의 양식이 마련되어 있어요.&#x20;

여기에서 질문과 가이드를 참고하시면 템플릿을 만드는 데에도 도움될 거예요.
{% endhint %}

<details>

<summary>리뷰 총점을 위한 템플릿 만들기</summary>

리뷰 총점을 확인하기 위한 템플릿과 필수 설정에 대해 알려드릴게요.

**✔️조건 사항**

1. 리뷰 총점은 \[셀프 리뷰]와 \[하향 리뷰]에서만 사용이 가능합니다.
2. 해당 리뷰에서 \[일반 리뷰 템플릿]과 **\[업적 평가 템플릿]** 모두를 사용해주셔야 합니다.
3. 각 템플릿에 \[가중치 + 등급형 질문 + 등급 별 환산 점수를 모두설정해야지 리뷰 총점 기능을 사용하실 수 있습니다.

💡 질문 템플릿 종류 및 생성하는 법이 궁금하다면 [이 문서](https://www.notion.so/812f3fb1fef64432b511957685d7b52a)를 확인해 주세요!

#### 일반 리뷰 템플릿

1. 일반 리뷰 템플릿 생성시, `질문에 가중치 옵션 설정`을 클릭합니다.

<img src="../../.gitbook/assets/Untitled (17) (3).png" alt="" data-size="original">

2. 질문을 생성하실 때, 질문 답변 방식 중 1개 이상의 \[등급] 질문이 필요합니다. 따라서, `등급 / 1개 선택 / 복수 선택` 버튼을 클릭해주세요.

<img src="../../.gitbook/assets/Untitled (18) (3).png" alt="" data-size="original">

3. `등급`을 선택하고, `환산 점수`를 필수적으로 작성해주셔야 합니다.

<img src="../../.gitbook/assets/Untitled (19) (4).png" alt="" data-size="original">

4. 질문 설정을 완료하면, 해당 페이지 하단의 가중치를 설정해주세요

<img src="../../.gitbook/assets/Untitled (20) (2).png" alt="" data-size="original">

⚠️ **가중치의 합은 100%가 되어야 합니다.**&#x20;

단, 주관식으로만 이뤄진 질문의 경우 가중치 값에 포함되지 않습니다.

<img src="../../.gitbook/assets/Untitled (21) (3).png" alt="" data-size="original">

#### **업적 평가 템플릿**

1. 업적 평가 템플릿 생성시 답변 유형 중 `등급`을 선택하고, `환산 점수`를 필수적으로 작성해주셔야 합니다.

<img src="../../.gitbook/assets/Untitled (22) (3).png" alt="" data-size="original">

2. 템플릿 생성 하단에 `가중치` 설정을 켜야 리뷰 총점 기능을 이용하실 수 있습니다.

<img src="../../.gitbook/assets/Untitled (23) (3).png" alt="" data-size="original">

</details>



## 템플릿 유형 선택하기 <a href="#make-review-template-select-format" id="make-review-template-select-format"></a>

진행하고자 하는 리뷰의 성격에 맞게 세 가지 템플릿 유형을 선택해서 만들 수 있어요.

*   **일반 리뷰 템플릿**

    기본적인 주관식/객관식 문항들을 만들 때 선택해 주세요.

    핵심가치 및 역량 평가할 때 선택해 주세요.
*   **업적 평가 템플릿**

    직접 본인의 성과(업적)를 작성하고 그에 대해 평가할 때 선택해 주세요.
*   **등급 템플릿**

    리뷰 내용을 종합하여 최종 등급을 매길 때 선택해 주세요.

    캘리브레이션 기능을 이용하고자 한다면, 이 템플릿이 모든 하향 리뷰에 적용되어야 합니다.

![](<../../.gitbook/assets/Untitled (14).png>)

### 일반 리뷰 템플릿 <a href="#make-review-template-select-format-general" id="make-review-template-select-format-general"></a>

#### 기본 정보

* 가중치 ON: 항목별 가중치를 설정할 수 있습니다. (가중치 적용 및 점수 합산 가능)
* 가중치 OFF: 항목별 가중치를 설정하지 않습니다.

<figure><img src="../../.gitbook/assets/image (82).png" alt=""><figcaption><p>위와 같이 항목별 가중치 설정이 가능합니다. 질문 작성을 모두 마친 후 하단에서 설정 가능합니다.</p></figcaption></figure>

#### 작성 가이드

직원들에게 리뷰 작성 가이드를 주고 싶다면 입력해 주세요. 각 회사의 리뷰 제도 공지 혹은 작성 가이드 등을 안내할 수 있습니다. 이 내용은 어드민과 리뷰 작성자만 확인할 수 있습니다.

<figure><img src="../../.gitbook/assets/image (32).png" alt=""><figcaption></figcaption></figure>

#### 질문

질문 내용을 적어주세요. 작성 가이드에는 답변 작성 시 유의할 점을 적어주세요.

<figure><img src="../../.gitbook/assets/image (169).png" alt=""><figcaption></figcaption></figure>

#### 답변

`객관식 답변`을 원한다면 **등급 / 1개 선택 / 복수 선택**을 사용하고,

`주관식 답변`을 원한다면 **코멘트**를 사용하세요!

_객관식과 주관식 형식 두 가지를 동시에 사용할 수도 있어요_ 🙂



*   등급: 등급별 환산 점수 설정이 가능합니다.\


    <figure><img src="../../.gitbook/assets/image (33).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (24).png" alt="" width="563"><figcaption><p>리뷰 작성 화면</p></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (172).png" alt="" width="563"><figcaption><p>등급’을 선택하면, 리뷰 결과지에 항목별 평균값이 계산됩니다. (여러 명이 리뷰를 작성한 경우에만 해당)</p></figcaption></figure>

* **1개 선택**\
  등급이 아닌 선택 유형의 질문 시 유용합니다. (ex. 리뷰 대상자가 가장 잘 지키고 있는 핵심 가치)\

* **복수 선택**\
  여러 개의 답변을 선택할 수 있습니다.



#### 리뷰 대상자에게 답변 비공개

이 옵션이 적용된 질문과 답변은 **리뷰 대상자에게는 보이지 않고,** 리뷰 대상자의 리더, 차상위 리더, 어드민에게만 공개됩니다.

* **특정 항목을 리뷰 대상자에게 공유하고 싶지 않은 경우**에만 체크해 주세요. (전체 비공개인 경우 체크X)
* 리뷰 내용 자체를 공유하고 싶지 않다면 이 옵션에 체크하지 말고, **리뷰 생성 시 공유 옵션을 선택**하세요.

<figure><img src="../../.gitbook/assets/image (23).png" alt=""><figcaption></figcaption></figure>

### 업적 평가 템플릿 <a href="#make-review-template-select-format-performance" id="make-review-template-select-format-performance"></a>

#### 질문과 가이드

{% hint style="info" %}
**업적 평가 템플릿은 아래 두 가지 경우에만 적용 가능합니다. (1) 셀프 리뷰 (2) 셀프+하향 리뷰**

* `셀프 리뷰`에서는 본인의 성과를 적어 그에 대해 평가하고
* `하향 리뷰`에서는 그 성과와 평가 내용을 보면서 평가를 합니다. 즉, 업적 평가에서는 셀프 평가 내용이 기재 되어야만 하향 평가가 가능합니다.

\
구성원 입장에서 어떻게 작성하는지 궁금하다면 아래 문서에서 확인해 주세요!

[성과 리뷰(평가)하기](https://www.notion.so/ad2b0dc679ba40b38576fa95e6cd2be3?pvs=21)
{% endhint %}

위 내용을 고려하여 질문과 가이드를 입력해 주세요.

가이드를 통해 각 회사의 리뷰 제도 공지 혹은 작성 방법 등을 안내할 수 있습니다. 이 내용은 어드민과 리뷰 작성자만 확인할 수 있습니다.

<figure><img src="../../.gitbook/assets/image (21).png" alt=""><figcaption></figcaption></figure>

#### 답변 유형

답변 유형은 등급/서술형 두 가지 중 선택할 수 있습니다.

<figure><img src="../../.gitbook/assets/image (26).png" alt=""><figcaption></figcaption></figure>

#### 가중치와 코멘트

* 가중치: 셀프 리뷰에서 성과 작성 시, 가중치를 설정할 수 있어요. 가중치의 합은 100%입니다.
* 코멘트: 성과에 대한 등급 평가에 코멘트 작성 여부를 선택할 수 있습니다.

<figure><img src="../../.gitbook/assets/image (70).png" alt=""><figcaption></figcaption></figure>

### 등급 템플릿 <a href="#make-review-template-select-format-rating" id="make-review-template-select-format-rating"></a>

#### 질문과 가이드

작성자에게 보여지는 질문을 적고, 가이드를 통해 각 회사의 리뷰 제도 공지 혹은 작성 방법 등을 안내할 수 있습니다. 이 내용은 어드민과 리뷰 작성자만 확인할 수 있습니다.

<figure><img src="../../.gitbook/assets/image (36).png" alt=""><figcaption></figcaption></figure>

#### 답변 유형

답변 유형은 `등급/서술형` 두 가지 중 선택할 수 있습니다.

평가 내용을 종합하여 최종 등급을 매길 때 사용해 주세요.

<figure><img src="../../.gitbook/assets/image (69).png" alt=""><figcaption></figcaption></figure>
