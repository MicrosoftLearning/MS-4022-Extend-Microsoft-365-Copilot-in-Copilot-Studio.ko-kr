---
title: 연습 지침
permalink: index.html
layout: home
---

# 연습

이 페이지에는 Microsoft 기술 과정 **MS-4022: Copilot Studio에서 Microsoft 365 Copilot 확장**과 관련된 연습이 나열되어 있습니다.

관련 학습 경로: [Copilot Studio에서 Microsoft 365 Copilot 확장](https://learn.microsoft.com/training/paths/extend-microsoft-365-copilot-studio/).

**참고**: 이 연습을 완료하려면 다음 사항이 필요합니다.

- [Copilot Studio에 액세스할 수 있는](https://learn.microsoft.com/microsoft-copilot-studio/requirements-licensing-subscriptions) 회사 또는 학교 계정. Microsoft 365 조직의 구성에 따라 Copilot Studio에 대한 액세스 권한이 아직 없는 경우 [체험판 계정 만들기](https://learn.microsoft.com/microsoft-copilot-studio/sign-up-individual)가 가능할 수도 있습니다.
- Microsoft 365 Copilot 라이선스
- 원하는 콘텐츠 소스에 연결하는 데 필요한 자격 증명(커넥터, API 등)

{% assign labs = site.pages | where_exp:"page", "page.url contains '/Instructions/Labs'" %} {% assign labs = labs | sort: "lab.title" %} {% for activity in labs  %}
- [{{ activity.lab.title }}]({{ site.github.url }}{{ activity.url }}) {% endfor %}

