---
lab:
  title: '1.3: 제안된 프롬프트 추가'
---

# 제안된 프롬프트 추가

이 연습에서는 6개의 적절한 제안된 프롬프트를 사용하여 이전 연습에서 만든 선언적 에이전트를 업데이트합니다.

이 연습을 완료하는 데 약 **10**분 정도 소요됩니다.

## 제안된 프롬프트 정의

Copilot Studio에서 다음 작업을 수행합니다.

1. **Product Support** 에이전트의 **개요** 페이지로 이동합니다.
1. 대화형 에이전트 만들기 마법사는 만드는 동안 에이전트에 대한 제안된 프롬프트를 생성했습니다. 에이전트의 기능에 따라 더 적절한 프롬프트로 바꾸겠습니다.
1. **제안된 프롬프트** 섹션에서 **편집** 아이콘을 선택합니다.
1. 기존 프롬프트를 다음으로 바꿉니다.

      `Eagle Air` : `Tell me about Eagle Air`

      `Return policy` : `What is the returns policy`              

      `Product information` : `Can you provide information on a specific product?` 

      `Product troubleshooting` : `I'm having trouble with a product. Can you help me troubleshoot the issue?` 

      `Repair information ` : `Can you provide information on how to get a product repaired?`
      
      `Contact support` : `How can I contact support for help?`

1. **저장**을 선택하여 변경 내용을 저장합니다. 

## 에이전트 다시 게시

업데이트한 에이전트를 Microsoft 365 Copilot에 게시해 보겠습니다.

1. 에이전트의 변경 내용이 성공적으로 저장되면 Copilot Studio에서 에이전트 개요 페이지의 오른쪽 위에 있는 **게시**를 선택합니다.
1. 열리는 모달 창에서 **게시**를 선택합니다.
1. 열리는 **가용성 옵션** 창의 **공유 링크** 제목 아래에서 **복사**를 선택합니다.
    ![가용성 옵션 창의 스크린샷](../Media/availability-options-share-link.png)
1. 웹 브라우저의 다른 탭에서 에이전트의 공유 링크 **붙여넣기** 후 **Enter** 키를 선택합니다. **Product Support** 에이전트를 설명하는 창이 나타납니다.
1. 에이전트 이름 아래의 **지금 업데이트**를 선택하여 Product Support 에이전트에 변경 내용을 게시합니다. 에이전트가 업데이트되는 동안 잠시 기다립니다.
1. 업데이트가 완료되면 모달 창을 닫습니다. 브라우저에서 Microsoft 365 Copilot으로 이동하지 않는 경우 왼쪽 메뉴 또는 Microsoft 365 포털의 **앱** 메뉴에서 **Copilot**을 선택합니다.

## Microsoft 365 Copilot에서 에이전트 테스트

1. **Microsoft 365 Copilot**의 사이드 패널의 에이전트 목록에서 **제품 지원**을 찾고 이를 선택하여 에이전트와 직접 채팅할 몰입형 환경을 입력합니다. Copilot Studio에서 정의한 제안된 프롬프트가 사용자 인터페이스에 표시됩니다.

    ![Microsoft Edge에서 Product Support 에이전트의 스타터 프롬프트를 보여 주는 Microsoft 365 Copilot 스크린샷.](../Media/product-support-starter-prompts.png)
1. 제안된 프롬프트를 **선택**하고, 메시지를 **전송**하고, 응답을 검토합니다.
