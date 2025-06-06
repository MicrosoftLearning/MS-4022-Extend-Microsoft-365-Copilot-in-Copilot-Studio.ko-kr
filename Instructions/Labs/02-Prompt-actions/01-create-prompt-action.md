---
lab:
  title: '2.1: 프롬프트 작업 만들기'
---

# 프롬프트 작업 만들기

이 연습에서는 프롬프트 작업을 만들고, Copilot Studio에서 프롬프트를 테스트하고, Copilot 에이전트 내에서 프롬프트를 테스트합니다. 사용자가 아이디어를 특정 형식과 지침에 따라 구성된 마케팅 피치로 구성하는 데 도움이 되는 프롬프트 작업을 만들어 보겠습니다.

이 연습을 완료하는 데 약 **15**분 정도 소요됩니다.

## Copilot Studio에서 프롬프트 작업 만들기

1. 웹 브라우저에서 [Copilot Studio](https://copilotstudio.microsoft.com)(`https://copilotstudio.microsoft.com`)로 이동하여 Copilot Studio를 엽니다.
1. 왼쪽 탐색 창에서 **라이브러리**를 선택합니다.
1. **새로 추가**를 선택한 다음 **프롬프트**를 선택합니다. **프롬프트 작업 추가** 마법사가 열립니다.
1. **작업 이름** 필드에 `Create a Contoso Marketing Pitch`을(를) 입력합니다.
1. **설명** 필드에 `Create a marketing pitch that follows Contoso guidelines` 입력 후 **다음**을 선택합니다. **프롬프트 만들기** 페이지로 이동하게 됩니다.
1. **지침** 텍스트 상자에 `Create a marketing pitch for a product based on a `을(를) 입력합니다.
1. 입력한 문장 끝에 커서를 놓고 **콘텐츠 추가**를 선택합니다 .
1. **텍스트**를 선택합니다.
1. **이름** 필드에 `draft`을 입력합니다.
1. **샘플 데이터** 필드에 `The Mighty Mechanical Pencil is new, exciting, and useful. It's not only the first of its kind pencil, but it's fun to use.` 입력 후 **닫기**를 선택합니다.

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

## 작업 구성 및 게시

1. **작업 매개 변수 선택** 페이지에서 `draft` 입력 변수에 대해 다음 **설명**을 제공합니다. `initial draft of the marketing pitch`.
1. `text` 출력 변수에 대해 다음 **설명**을 제공합니다. `Final marketing pitch that adheres to Contoso guidelines`.
1. **다음**을 선택합니다.
1. 세부 정보를 올바르게 입력했는지 확인하고 **게시**를 선택합니다.
1. 작업이 저장되고 게시되는 동안 잠시 기다립니다.
1. 이제 라이브러리에서 작업을 사용할 수 있습니다. **저장 후 닫기**를 선택합니다.

   > **참고**: 에이전트에서 **작업 추가** 페이지의 **추천** 또는 **라이브러리** 섹션에 새 프롬프트 작업이 표시되는 데 몇 분 이상 걸릴 수 있습니다.

## (선택 사항) 에이전트에 프롬프트 작업 추가

이전 랩을 완료하고 선언적 에이전트를 만든 경우, 이 작업을 에이전트에 추가하고 해당 작업을 참조하도록 에이전트의 지침을 업데이트할 수 있습니다.

### 작업 추가

1. **라이브러리**에서 작업을 추가할 선언적 에이전트를 선택합니다.
1. **세부 사항** 섹션에서 **편집**을 선택합니다.
1. **지침** 텍스트 상자에서 기존 명령 텍스트에 다음을 추가합니다. `Use the Contoso Marketing Pitch action to help marketing stakeholders craft pitches for products based on their draft ideas.` 
1. 에이전트 세부 정보 페이지의 **작업**에서 **작업 추가**를 선택합니다.
1. **작업 추가** 모달 창의 **추천** 또는 **라이브러리** 섹션에서 **Contoso Marketing Pitch**를 선택합니다.
1. 작업 페이지에서 **이름**이 `Create a Contoso Marketing Pitch`인지 확인합니다.
1. **설명**이 `Create a marketing pitch that follows the Contoso guidelines`인지 확인합니다.
1. **작업 추가**를 선택합니다. 어느 정도 시간이 걸릴 수 있습니다. 이 작업이 **작업**에서 에이전트가 사용할 수 있는 작업 목록에 추가됩니다.

### 작업 구성

1. 에이전트가 사용할 수 있는 작업 중 `Contoso Marketing Pitch` 작업을 선택합니다. 작업의 속성 및 설정을 구성하는 페이지로 이동하게 됩니다.
1. **작업 이름**이 `Create a new Contoso marketing pitch`(으)로 설정되어 있는지 확인합니다.
1. 작업 내에서 위쪽 탐색 영역의 **입력**을 선택합니다.
1. **추가 입력**에서 **추가**를 선택합니다.
1. **초안** 변수를 선택합니다. 양식이 나타납니다.
1. **에이전트가 이 입력을 채우는 방법** 필드가 **동적으로 최고의 옵션 채우기(기본값)** 로 설정되어 있는지 확인합니다.
1. **표시 이름** 필드에서 `Initial draft`을 입력합니다.
1. **다음으로 식별** 필드가 **사용자의 전체 응답**으로 설정되어 있는지 확인합니다.
1. 창 오른쪽 위의 **저장**을 선택합니다.

## (선택 사항) Copilot Studio에서 프롬프트 작업 테스트

다음으로, Copilot Studio에서 작업으로 에이전트를 테스트합니다.

1. Copilot Studio의 에이전트 개요 페이지에 있는 **에이전트 테스트** 창에서 **새로 고침** 단추를 선택하여 테스트 창을 새로 고치고 에이전트의 최신 변경 내용을 로드합니다.
1. 테스트 대화의 텍스트 상자에 `Create a Contoso marketing pitch based on the following draft: "Bouncy ball is the hottest product on the market for both youth and adults. It's durable and the largest of its kind."` 입력 후 메시지를 보냅니다.
1. 응답을 검토하여 에이전트가 사용자 지정 프롬프트 작업의 지침에서 제공한 안내를 따르고 있음을 확인합니다.

연습을 완료하고 프롬프트 작업의 기능을 확인했습니다.
