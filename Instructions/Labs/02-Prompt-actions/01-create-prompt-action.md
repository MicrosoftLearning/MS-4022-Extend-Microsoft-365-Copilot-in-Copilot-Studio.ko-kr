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
1. **+ 새 도구**를 선택합니다.
1. 새 도구 팝업 창에서 **프롬프트**를 선택합니다. 프롬프트 작성기 UI로 이동됩니다. 이 창 내에서 Copilot을 사용할 수 있지만 이 연습에 대한 프롬프트를 수동으로 정의하겠습니다.
1. 창 위쪽의 텍스트 상자에서 자동 생성된 이름을 선택하고 **마케팅 피치 프롬프트**라는 이름으로 바꿉니다.
1. **지침** 텍스트 상자에 `Create a marketing pitch for a product based on a `을(를) 입력합니다.
1. 입력한 문장 끝에 커서를 놓고 **콘텐츠 추가**를 선택합니다 .
1. **텍스트**를 선택합니다.
1. **이름** 필드에 `Draft`을 입력합니다.
1.  **샘플 데이터** 필드에 `The Mighty Mechanical Pencil is new, exciting, and useful. It's not only the first of its kind pencil, but it's fun to use.` 입력 후 **닫기**를 선택합니다.

    ![Copilot Studio의 프롬프트 작성기 UI에서 입력 변수가 "Draft"라는 이름으로 구성되는 것을 보여 주는 스크린샷](../Media/prompt-content-sample-data.png)

## 프롬프트 테스트 및 개선

1. 지침 상자 위에 있는 **테스트**를 선택하여 사용자가 제공한 샘플 데이터로 프롬프트를 테스트합니다.
1. **모델 응답** 섹션에서 테스트 실행의 출력을 봅니다.

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
    ![구체화된 프롬프트를 테스트한 후의 사용자 지정 프롬프트 UI 스크린샷](../Media/test-prompt-refined.png)
1. **저장**을 선택하여 보고서를 저장합니다.

## (선택 사항) 에이전트에 프롬프트 작업 추가

이전 랩을 완료하고 선언적 에이전트를 만든 경우, 이 작업을 에이전트에 추가하고 해당 작업을 참조하도록 에이전트의 지침을 업데이트할 수 있습니다.

### 프롬프트 도구 추가

1. Copilot Studio의 사이드바에서 **에이전트**를 선택합니다.
1. **Microsoft 365 Copilot**을 선택합니다.
1. **에이전트**에서 작업을 추가할 **Product Support** 에이전트를 선택합니다.
1. 페이지의 **도구** 섹션에서 **도구 추가**를 선택합니다.
1. **프롬프트** 필터를 선택합니다.
1. **마케팅 피치 프롬프트** 도구를 선택합니다.
    ![마케팅 피치 프롬프트 도구가 나열된 도구 추가 창의 스크린샷](../Media/add-marketing-pitch-tool.png)
1. **추가 및 구성**을 선택하고 도구가 추가될 때까지 기다립니다. 이제 도구가 Product Support 에이전트의 **도구**에 나열됩니다.
    ![마케팅 피치 프롬프트 도구를 나열하는 제품 지원 에이전트의 도구 섹션 스크린샷](../Media/agent-updated-tools.png)

### 에이전트의 지침 및 시작 프롬프트 업데이트

프롬프트 사용을 안내하기 위해 에이전트의 지침을 업데이트합니다.

1. **지침** 텍스트 상자에서 기존 지침 텍스트에 다음을 추가한 후 변경 내용을 **저장**합니다. `Use the Marketing Pitch Prompt tool to craft pitches for products that follow Contoso guidelines based on users' draft ideas.` 
1. **제안된 프롬프트** 섹션에서 Eagle Air 제안 프롬프트를 다음 제안된 프롬프트로 바꾼 후 변경 내용을 **저장**합니다. `Marketing Pitch` : `Create a marketing pitch following Contoso guidelines based on the following draft:`

연습을 완료하고 에이전트에 대한 프롬프트 도구를 만들었습니다.
