---
lab:
  title: '2.1: 프롬프트 작업 만들기'
---

# 프롬프트 작업 만들기

이 연습에서는 프롬프트 작업을 만들고, Copilot Studio에서 프롬프트를 테스트하고, Copilot 에이전트 내에서 프롬프트를 테스트합니다. 사용자가 아이디어를 특정 형식과 지침에 따라 구성된 마케팅 피치로 구성하는 데 도움이 되는 프롬프트 작업을 만들어 보겠습니다.

이 연습을 완료하는 데 약 **15**분 정도 소요됩니다.

## Copilot Studio에서 사용자 지정 프롬프트 만들기

1. 웹 브라우저에서 [Copilot Studio](https://copilotstudio.microsoft.com)(`https://copilotstudio.microsoft.com`)로 이동하여 Copilot Studio를 엽니다.
1. 왼쪽 탐색 영역에서 **도구**를 선택합니다.
1. **새로 만들기**를 선택한 다음 **프롬프트**를 선택합니다. 프롬프트 작성기 UI로 이동하게 됩니다.
1. **지침** 텍스트 상자에 `Create a marketing pitch for a product based on a `을(를) 입력합니다.
1. 입력한 문장 끝에 커서를 놓고 **콘텐츠 추가**를 선택합니다 .
1. **텍스트**를 선택합니다.
1. **이름** 필드에 `draft`을 입력합니다.
1.  **샘플 데이터** 필드에 `The Mighty Mechanical Pencil is new, exciting, and useful. It's not only the first of its kind pencil, but it's fun to use.` 입력 후 **닫기**를 선택합니다.

    ![Copilot Studio의 프롬프트 작성기 UI에서 입력 변수가 "draft"라는 이름으로 구성되는 것을 보여 주는 스크린샷.](../Media/prompt-action-input.png)

## 프롬프트 테스트 및 개선

1. 지침 상자 위에 있는 **테스트**를 선택하여 사용자가 제공한 샘플 데이터로 프롬프트를 테스트합니다.
1. 테스트 실행의 출력을 봅니다.

보다 구조화되고 일관된 출력을 만들도록 프롬프트를 다듬어 보겠습니다.

1. **지침** 텍스트 상자에서 기존 지침에 다음을 추가하여 프롬프트를 수정합니다.

    ```The pitch should follow the following Contoso guidelines:
       - Start with a brief hook
       - Describe unique value proposition
       - End with a call-to-action
       - Use an exciting and influential tone
    ```

1. **테스트**를 다시 선택하여 프롬프트를 다시 테스트합니다.
1. 응답이 어떻게 다른지 확인합니다.
1. **저장**을 선택합니다.

## 프롬프트 구성 및 게시

프롬프트를 저장하면 **에이전트에서 사용하도록 구성** 창이 나타납니다.

1. **이름** 필드에 `Create a Contoso Marketing Pitch`을(를) 입력합니다.
1. **에이전트에 이 도구를 사용해야 하는 시기를 알려주기 위한 설명** 필드에 `Create a marketing pitch that follows Contoso guidelines`을(를) 입력한 후 **다음**을 선택합니다. **프롬프트 만들기** 페이지로 이동하게 됩니다.
1. **추가**를 선택합니다.

## (선택 사항) 에이전트에 프롬프트 작업 추가

이전 랩을 완료하고 선언적 에이전트를 만든 경우, 이 작업을 에이전트에 추가하고 해당 작업을 참조하도록 에이전트의 지침을 업데이트할 수 있습니다.

### 프롬프트 도구 추가

1. Copilot Studio의 사이드바에서 **에이전트**를 선택합니다.
1. **Microsoft 365 Copilot**을 선택합니다.
1. **에이전트**에서 작업을 추가할 **Product Support** 에이전트를 선택합니다.
1. 페이지의 **도구** 섹션에서 **도구 추가**를 선택합니다.
1. **프롬프트** 필터를 선택합니다.
1. **Contoso 마케팅 피치 만들기** 프롬프트를 선택합니다.
1. **에이전트에 추가**를 선택합니다. 이제 도구가 Product Support 에이전트의 **도구**에 나열됩니다.

### 프롬프트 도구 구성

1. 에이전트 개요 페이지의 **도구** 섹션에서 `Contoso Marketing Pitch` 도구를 선택합니다. 도구의 속성 및 설정을 구성하는 페이지로 이동하게 됩니다.
1. 프롬프트 도구 내에서 위쪽 탐색 영역의 **입력**을 선택합니다.
1. **추가 입력**에서 **추가**를 선택합니다.
1. **초안** 변수를 선택합니다. 양식이 나타납니다.
1. **에이전트가 이 입력을 채우는 방법** 필드가 **동적으로 최고의 옵션 채우기(기본값)** 로 설정되어 있는지 확인합니다.
1. **표시 이름** 필드에서 `Initial draft`을 입력합니다.
1. **다음으로 식별** 필드가 **사용자의 전체 응답**으로 설정되어 있는지 확인합니다.
1. 창 오른쪽 위의 **저장**을 선택합니다.

### 에이전트의 지침 업데이트

프롬프트 사용을 안내하기 위해 에이전트의 지침을 업데이트합니다.

1. **지침** 텍스트 상자에서 기존 명령 텍스트에 다음을 추가합니다. `Use the Contoso Marketing Pitch action to help marketing stakeholders craft pitches for products based on their draft ideas.` 

## (선택 사항) Copilot Studio에서 프롬프트 도구 테스트

다음으로, Copilot Studio에서 프롬프트 도구로 에이전트를 테스트합니다.

1. Copilot Studio의 에이전트 개요 페이지에 있는 **에이전트 테스트** 창에서 **새로 고침** 단추를 선택하여 테스트 창을 새로 고치고 에이전트의 최신 변경 내용을 로드합니다.
1. 테스트 대화의 텍스트 상자에 `Create a Contoso marketing pitch based on the following draft: "Bouncy ball is the hottest product on the market for both youth and adults. It's durable and the largest of its kind."` 입력 후 메시지를 보냅니다.
1. 응답을 검토하여 에이전트가 사용자 지정 프롬프트의 지침에서 제공한 안내를 따르고 있음을 확인합니다.

연습을 완료하고 프롬프트 도구의 기능을 확인했습니다.
