## Step 4: 사용자 정의 에이전트 생성

이제 지침, 프롬프트 및 템플릿이 함께 작동하므로 사용자 정의를 한 단계 더 진행하고 싶습니다. 새로운 과제를 구상할 때, 구현보다는 아이디어 창출에만 초점을 맞춘 특화된 채팅 경험을 원합니다.

### 📖 이론: 사용자 정의 에이전트

사용자 정의 에이전트(`*.agent.md`)는 Copilot의 작동 방식을 근본적으로 변경하여 특정 도구와 응답 형식을 가진 특화된 대화 경험을 만들며, 심지어 독특한 개성도 있을 수 있습니다! Copilot Chat 인터페이스의 드롭다운 목록에서 선택됩니다.

Visual Studio Code는 `.github/agents/` 디렉토리에서 `*.agent.md` 파일을 검색합니다.

> [!TIP]
> 사용자 정의 에이전트에 대해 자세히 알아보세요:
>
> - [VS Code Docs: 사용자 정의 에이전트](https://code.visualstudio.com/docs/copilot/customization/custom-agents)
> - [GitHub Docs: 사용자 정의 에이전트 구성](https://docs.github.com/en/copilot/reference/custom-agents-configuration)


### ⌨️ 활동: 과제 아이디어 창출 사용자 정의 에이전트 생성

이제 과제 아이디어 브레인스토밍을 위한 특화된 사용자 정의 에이전트를 생성해봅시다.

1. 다음과 같은 새 파일을 생성합니다:

   ```text
   .github/agents/assignment-brainstorming.agent.md
   ```

1. 초점이 있는 브레인스토밍 경험을 생성하기 위해 다음 내용을 추가합니다:

   ```markdown
   ---
   name: assignment-brainstorming
   description: 과제 아이디어 창출 어시스턴트
   tools: ["search", "web"]
   ---

   # 💡 과제 아이디어 창출 어시스턴트

   **브레인스토밍 모드 활성화됨** 🚀

   저는 Mergington 고등학교의 과제 아이디어 창출 도우미입니다! 기존 커리큘럼을 분석하고 학생들이 이미 배운 내용을 바탕으로 구축하는 창의적인 다음 과제를 제안합니다.

   ## 응답 스타일

   모든 응답은 다음 형식을 따릅니다:

   🔍 빠른 스캔: [기존 과제의 간단한 분석]
   💡 아이디어 폭발: [3~5가지 빠른 제안]
   🎯 다음 질문: [더 도움이 되기 위해 알아야 할 사항]

   ## 규칙

   - ⚡ 응답은 짧게
   - 🎯 항상 구체적인 질문으로 끝내기
   - 💡 개념에 집중, 세부사항 아님
   - 🚫 과제 명세서 작성 금지
   - 📊 기존 커리큘럼 격차를 바탕으로 아이디어 도출
   ```

### ⌨️ 활동: 브레인스토밍 사용자 정의 에이전트 테스트

1. VS Code에서 Copilot Chat을 엽니다.

1. 에이전트 드롭다운 목록에서 사용자 정의 에이전트를 선택합니다.

   <img width="379" height="218" alt="copilot agent: 과제 아이디어 창출 에이전트가 선택됨" src="https://github.com/user-attachments/assets/4effffa7-b8ef-4830-8050-9c777f9f0189" />

1. 교사가 물어볼 수 있는 질문으로 사용자 정의 에이전트를 테스트합니다. 다른 응답 형식에 주목하세요!

   > ![Static Badge](https://img.shields.io/badge/-Prompt-text?style=social&logo=github%20copilot)
   >
   > ```prompt
   > 현재 커리큘럼에서 빠진 과제 주제가 뭐야?
   > ```

   > ![Static Badge](https://img.shields.io/badge/-Prompt-text?style=social&logo=github%20copilot)
   >
   > ```prompt
   > 내 학생들을 위한 고급 Python 과제 3개를 제안해줘.
   > ```

   > ![Static Badge](https://img.shields.io/badge/-Prompt-text?style=social&logo=github%20copilot)
   >
   > ```prompt
   > 데이터 분석 과제 이후에 좋을만한 과제가 뭐야?
   > ```

1. 후속 질문을 시도하여 사용자 정의 에이전트가 대화 전체에서 성격을 어떻게 유지하는지 확인해봅시다.

1. 새로운 사용자 정의 에이전트 파일에 대한 변경사항을 커밋하고 푸시합니다: `.github/agents/assignment-brainstorming.agent.md`

1. Mona가 최종 검토를 위해 당신을 기다립니다!

<details>
<summary>문제가 있으신가요? 🤷</summary><br/>

- 사용자 정의 에이전트 파일이 `.github/agents/` 디렉토리에 있고 `.agent.md` 확장자인지 확인하세요.
- 사용자 정의 에이전트는 `@` 멘션이 아닌 드롭다운 목록에서 선택됩니다.
- 사용자 정의 에이전트가 드롭다운에 나타나지 않으면 VS Code를 다시 시작하거나 윈도우를 다시 로드하세요.
