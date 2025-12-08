---
lab:
  title: '3.1: 커넥터 도구 만들기'
---

# 커넥터 도구 만들기

이 연습에서는 Copilot Studio에서 선언적 에이전트를 위한 커넥터 도구를 구성합니다. "SharePoint - 목록 폴더" 커넥터를 사용하여 제품 지원 파일이 포함된 Products 폴더에서 파일 목록을 검색합니다.

이 연습을 완료하는 데 약 **15**분 정도 소요됩니다.

## 시작하기 전에

이 연습에서는 기존 에이전트에 커넥터 도구를 추가하는 데 중점을 둡니다. 이 연습에서는 다음을 가정합니다.

1. Copilot Studio에서 **Product Support** 선언적 에이전트를 이미 만들었습니다. 선언적 에이전트를 만들기 위한 지침이 필요한 경우 [선언적 에이전트 만들기](../01-Build-your-first-declarative-agent/01-create-declarative-agent.md)를 참조하세요.
1. **Product Support**라는 이름의 SharePoint 사이트가 있고, 이 사이트에는 샘플 제품 관련 데이터가 있는 파일이 들어 있는 **Products**라는 문서 라이브러리가 있습니다. 지침은 [사용자 지정 지식 추가](../01-Build-your-first-declarative-agent/02-add-custom-knowledge.md) 연습 내에 있는 **시작하기 전에**라는 섹션을 참조하세요.

## 미리 빌드된 커넥터에서 SharePoint 커넥터 도구 만들기

SharePoint List 폴더의 미리 빌드된 커넥터를 사용하여 커넥터 도구를 만들고 에이전트에 추가합니다.

1. 웹 브라우저에서 [Copilot Studio](https://www.copilotstudio.microsoft.com)(`https://www.copilotstudio.microsoft.com`)로 이동합니다.
1. 사이드바에서 **에이전트**를 선택합니다.
1. **Microsoft 365 Copilot**을 선택합니다.
1. **에이전트**에서 **Product Support**를 선택합니다.
1. **도구**에서 **도구 추가**를 선택합니다.
1. **도구 추가** 창에서 **커넥터** 단추를 선택하여 커넥터 도구를 필터링한 다음, **검색** 창에 `SharePoint`을(를) 입력하고 **검색**을 선택합니다. 관련 커넥터가 창에 표시될 때까지 기다립니다.
1. **목록 폴더** SharePoint 커넥터 작업을 찾아 선택합니다.
    ![목록 폴더 커넥터를 강조 표시하는 도구 추가 창의 스크린샷](../Media/add-tool-list-folder.png)
1. 모달 창에 SharePoint 커넥터에 대한 연결이 표시됩니다. 연결이 활성화되면 커넥터 옆에 녹색 확인 표시가 표시됩니다. **...** 를 선택하면 연결에 대한 세부 정보를 확인할 수 있습니다. 상태가 `Not connected`이면 **연결되지 않음** 옆의 드롭다운을 선택하고 **새 연결 만들기**를 선택합니다.
    ![새 연결 만들기 단추를 강조 표시하는 도구 추가 창의 스크린샷](../Media/create-new-connection.png)
1. **SharePoint에 연결** 페이지에서 **직접 연결(클라우드 서비스)** 을 선택한 다음, **만들기**를 선택합니다.
1. 다시 로그인하라는 메시지가 표시됩니다. 연습에 사용 중인 M365 계정을 사용하여 로그인합니다.
1. **도구 추가** 페이지에서 연결이 설정된 후 **추가 및 구성**을 선택하여 에이전트에 도구를 추가합니다.
1. **목록 폴더 - 커넥터** 도구가 에이전트의 **도구** 섹션에 나열되어 있는지 확인합니다.
    ![커넥터 도구가 추가된 후 제품 지원 에이전트의 도구 섹션 스크린샷](../Media/connector-tool-added.png)

## 에이전트에 대한 커넥터 도구 구성

에이전트에 대한 커넥터 도구의 속성을 구성합니다.

1. **제품 지원** 에이전트 페이지의 **도구** 아래에서 이전 섹션에서 추가한 **목록 폴더 - 커넥터** 도구를 선택합니다.
1. **이름** 텍스트 상자에 `List product support files`을 입력합니다.
1. **설명** 텍스트 상자에 `List product support files available in the Products folder`을(를) 입력합니다.
1. **추가 세부 정보** 옆에 있는 토글을 선택하여 추가 속성을 표시합니다.
1. **추가 세부 정보** 섹션의**설명** 텍스트 상자에 '제품 지원 SharePoint 사이트에 액세스하려면 로그인하세요.'를 입력합니다.
1. **입력** 섹션에서 **사이트 주소** 입력을 찾습니다. **값** 텍스트 상자에 **Product Support** SharePoint 사이트의 URL을 `https://DOMAIN.sharepoint.com/sites/ProductSupport` 형식으로 입력한 다음 **완료**를 선택합니다.
1. 다음으로, **파일 식별자** 입력을 찾습니다. 드롭다운에서 **채우기 방법** 필드를 **사용자 지정 값**으로 설정합니다.
1. **파일 식별자**에 대한 **값** 텍스트 상자에 `Products`을(를) 입력합니다.
1. 페이지 맨 위에 있는 **저장**을 선택하여 변경 내용을 저장합니다.
   
## 에이전트의 지침 수정

커넥터 작업을 사용하는 방법에 대한 안내를 제공하는 에이전트의 지침도 업데이트해 보겠습니다.

1. Copilot Studio의 **제품 지원**에이전트 **세부 정보** 섹션에서 **편집**을 선택합니다.
1. **지침** 텍스트 상자에서 기존 명령 텍스트에 다음을 추가합니다. `When asked about available support resources, use the SharePoint connector to list the files in the Products folder and let the user know the SharePoint Connector was used.` 
1. **저장**을 선택합니다.

## 도구로 에이전트 테스트

1. 에이전트 세부 정보 페이지의 오른쪽에 있는 **에이전트 테스트** 창을 펼칩니다.
1. 테스트 창에서 **새 테스트 세션 시작** 단추를 선택하여 에이전트의 최신 변경 내용을 로드합니다.
1. 메시지 상자에 `What product support files are available?` 입력 후 메시지를 보냅니다.
1. 에이전트가 지시에 따라 사용된 커넥터에 대한 주석으로 응답하고 Products 폴더에서 사용할 수 있는 파일을 나열합니다.
    ![목록 폴더 커넥터를 테스트하는 동안 테스트 창 결과의 스크린샷](../Media/test-agent-connector.png)

커넥터 도구가 에이전트 내에서 예상대로 작동하는지 확인하여 이 연습을 완료했습니다.
