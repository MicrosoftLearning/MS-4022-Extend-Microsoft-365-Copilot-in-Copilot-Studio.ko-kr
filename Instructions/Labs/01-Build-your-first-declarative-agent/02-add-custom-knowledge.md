---
lab:
  title: '1.2: 사용자 지정 지식 추가'
---

# 사용자 지정 지식 추가

이 연습에서는 사용자 지정 지침 및 기반 데이터를 사용하여 이전 연습에서 만든 선언적 에이전트를 업데이트합니다. 

이 연습을 완료하는 데 약 **20**분 정도 소요됩니다.

## 시작하기 전에

이 연습을 시작하기 전에 선언적 에이전트가 기반 데이터로 사용할 제품 관련 문서를 Microsoft 365에 업로드해야 합니다. 연습을 준비하기 위해 아래 단계를 완료합니다.

> [!NOTE]
> 새 SharePoint Online 사이트에 문서를 업로드하는 경우 문서를 인덱싱하고 Copilot에서 사용할 수 있게 되기까지 지연이 발생합니다. 에이전트를 즉시 테스트하려면 **기존** 사이트에 문서를 업로드합니다. 문서가 인덱싱되어 에이전트가 지연 없이 사용할 수 있습니다. 새 SharePoint Online 사이트를 사용하는 경우 문서를 인덱싱하여 Copilot에서 사용할 수 있게 되기까지 더 오래 걸릴 수 있습니다.
>
> **아래 지침은 문서를 새 사이트에 업로드하는 과정을 안내합니다**. 기존 사이트를 사용하려면 **샘플 데이터 업로드**라는 레이블이 지정된 섹션에서 시작하고, **Products** 라이브러리 대신 기존 라이브러리를 사용합니다.

### 샘플 데이터 다운로드

1. 웹 브라우저에서 이 과정의 [GitHub 리포지토리](https://github.com/MicrosoftLearning/MS-4022-Extend-Microsoft-365-Copilot-in-Copilot-Studio/blob/master/Allfiles/Products.zip)로 이동합니다.
1. **download raw file** 단추를 선택하여 **Products.zip**을 다운로드합니다. 

    ![GitHub의 download raw file 단추를 강조 표시한 Microsoft Edge의 스크린샷.](../Media/download-raw-file.png)

1. 다운로드한 폴더를 **열고** **모두 추출**을 선택하여 내용물을 나중에 액세스할 수 있는 컴퓨터에 `Products`(이)라는 새로 만든 폴더로 추출합니다.

### SharePoint 사이트 만들기

1. 웹 브라우저에서 [https://m365.cloud.microsoft](https://m365.cloud.microsoft/chat)(으)로 이동 후 이 랩에서 사용 중인 Microsoft 365 계정으로 **로그인**합니다. 
1. 왼쪽 메뉴에서 **앱**(그리드 아이콘)을 선택한 다음, "모든 앱"을 선택하여 Microsoft 365 앱의 메뉴를 엽니다.
    ![Copilot Chat의 M365 앱 단추 스크린샷](../Media/apps-icon.png)
1. 앱 카탈로그에서 **SharePoint**를 선택합니다.
1. 왼쪽 메뉴에서 **사이트 만들기**를 선택합니다.
1. 사이트 유형으로 **팀 사이트**를 선택합니다.
1. **템플릿 선택** 페이지에서 **표준 팀**을 선택합니다.
1. **미리 보기** 페이지에서 **템플릿 사용**을 선택합니다.
1. **사이트 이름 지정** 페이지에서 `Product support` 입력 후 **다음**을 선택합니다.
1. 다음 구성 페이지에서 **개인 정보 설정**을 **공개**로 변경합니다.
1. **사이트 만들기**를 선택합니다. 사이트를 만들고 **마침** 단추가 활성화될 때까지 시간이 조금 걸릴 수 있습니다.
1. **마침**을 선택합니다. 브라우저에서 새 SharePoint 사이트로 이동합니다.

### 문서 라이브러리 만들기

1. **Product Support** SharePoint 사이트에서 페이지 맨 위에 있는 **새로 만들기** 단추를 선택하고 **문서 라이브러리**를 선택합니다.
1. **새 문서 라이브러리 만들기** 페이지에서 **빈 라이브러리**를 선택합니다.
1. **이름** 필드에 `Products` 입력 후 **만들기**를 선택합니다. 새 문서 라이브러리로 이동했습니다.

### 예제 데이터 업로드

1. **제품** 라이브러리에서 **업로드** 단추를 선택한 다음, **파일**을 선택합니다.
1. 컴퓨터에서 지난 단계 때 다운로드한 샘플 파일을 저장한 폴더로 이동합니다.
1. 로컬 Products 폴더의 파일을 **모두 선택**한 다음 **열기**를 선택하여 SharePoint에 업로드합니다.
1. 업로드가 완료될 때까지 기다립니다. 이제 파일이 SharePoint의 **Products** 라이브러리에 표시됩니다.

### SharePoint URL 복사

다음으로 에이전트의 지식을 구성할 때 사용할 사이트로 연결되는 직접 URL을 복사합니다.

1. SharePoint의 **Products** 라이브러리 페이지에서 오른쪽 위에 있는 **설정** 아이콘을 선택하고 **라이브러리 설정**을 선택한 다음 **기타 라이브러리 설정**을 선택합니다.
1. **웹 주소** 속성을 찾습니다. **SharePoint 사이트 URL**은 웹 주소에서 `https://DOMAIN.sharepoint.com/sites/SITE_NAME/LIBRARY_NAME` 형식으로 되어 있는 부분입니다. URL은 도메인이 Microsoft 365 테넌트 도메인인 `https://DOMAIN.sharepoint.com/sites/ProductSupport/Products` 형식이어야 합니다.
1. SharePoint 사이트 URL을 **복사** 하고 향후 랩 단계에서 사용할 수 있도록 저장합니다. "/Products" 이후에 오는 URL의 일부를 포함하지 마세요.

## 사용자 지정 지식을 사용하여 에이전트 구성

SharePoint URL을 에이전트에 기반 지식 원본으로 추가합니다.

### SharePoint URL 추가

1. 웹 브라우저에서 [Microsoft Copilot Studio](https://copilotstudio.microsoft.com/)(`https://copilotstudio.microsoft.com`)로 이동합니다.
1. **에이전트**를 선택합니다.
1. **Microsoft 365용 Copilot**을 선택합니다.
1. **Product Support** 에이전트를 선택합니다.
1. 에이전트 개요 페이지의 **기술 자료** 섹션에서 **기술 자료 추가**를 선택합니다.
1. 열리는 마법사의 **지식 추가** 페이지에서 **SharePoint**를 선택합니다.
1. 텍스트 상자에 **Products** SharePoint 라이브러리의 URL을 붙여넣고 **추가**를 선택합니다. `https://DOMAIN.sharepoint.com/sites/ProductSupport/Products` 형식이어야 합니다.

1. **에이전트에 추가**를 선택한 다음, 지식 원본이 에이전트에 추가될 때까지 기다립니다. 1분 정도 걸릴 수 있습니다.
1. **Products** 라이브러리가 에이전트 개요 정보의 **지식** 섹션 아래에 표시됩니다.
    ![에이전트에 추가된 제품 라이브러리를 보여 주는 제품 지원 에이전트의 지식 섹션 스크린샷](../Media/agent-knowledge-products.png)

    > **참고**: Copilot Studio 에이전트는 사용자를 대신하여 문서에 액세스합니다. 에이전트는 최종 사용자가 액세스할 수 있는 문서에서만 답변과 콘텐츠를 가져올 수 있습니다.

### 사용자 지정 지침 업데이트

다음으로 에이전트의 지침을 업데이트하여 에이전트가 지식 원본을 어떻게 사용해야 하는지 설명합니다.

1. Copilot Studio에서 에이전트 개요 페이지의 **세부 정보** 섹션 내 **편집**을 선택합니다.
1. **지침** 텍스트 상자의 내용을 다음으로 바꿉니다. `You are an agent tasked with answering questions about Contoso Electronics products. Start every response by enthusiastically thanking the user for their question or comment, then respond to their question or comment. You will use documents from the Products folder in SharePoint as your source of information. If you can't find the necessary information, you should suggest that the agent should reach out to the team responsible for further assistance. Your responses should be concise and always include a cited source.` 
1. **세부 정보** 섹션에서 **저장**을 선택합니다.

## Copilot Studio에서 에이전트 테스트

마지막으로, 에이전트가 사용자 지정 지식 원본을 사용할 수 있는지 테스트합니다.

1. Copilot Studio의 에이전트 개요 페이지에 있는 **에이전트 테스트** 창에서 **새 테스트 세션 시작** 단추를 선택하여 테스트 창을 새로 고칩니다.
1. 테스트 대화의 텍스트 상자에 `Tell me about Eagle Air` 입력 후 메시지를 보냅니다.
1. 응답을 기다. 응답에 Eagle Air 드론에 대한 정보가 포함되어 있습니다. 응답에는 SharePoint에 저장된 Eagle Air 문서에 대한 인용 및 참조가 포함됩니다.

몇 가지 프롬프트를 더 시도해 보겠습니다.

1. 메시지 상자에 `Recommend a product suitable for a farmer` 입력 후 메시지를 보냅니다.
1. 응답을 기다. 응답에는 Eagle Air에 대한 정보와 Eagle Air가 권장되는 이유에 대한 몇 가지 추가 컨텍스트가 포함되어 있습니다. 응답에는 OneDrive에 저장된 Eagle Air 문서에 대한 인용 및 참조가 포함됩니다.
1. 메시지 상자에 `Explain why the Eagle Air is more suitable than Contoso Quad` 입력 후 메시지를 보냅니다.
1. 응답을 기다. 응답은 Eagle Air가 농민이 사용하기에 Contoso Quad보다 더 적합한 이유를 자세히 설명합니다.

마지막으로 에이전트가 대답할 수 없는 질문을 하여 대체 응답을 테스트해 보겠습니다.

1. 메시지 상자에 `When was Mark8 released?` 입력 후 메시지를 보냅니다.
1. 응답을 기다. 응답에서는 지침에 정의된 대로 에이전트가 추가 지원을 담당하는 팀에 문의해야 한다고 추천합니다.
    ![테스트 창의 에이전트 응답 스크린샷](../Media/test-agent-knowledge.png)
