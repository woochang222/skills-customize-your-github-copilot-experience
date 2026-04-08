## Step 2: 파일별 지침

일반적인 프로젝트 지침이 준비되어 있으니, 이제 과제와 관련된 더 구체적인 형식 지정 규칙이 필요하다는 것을 깨달았습니다. 저장소 전체 지침은 일반적인 코딩 표준에는 좋지만 모든 채팅 메시지에 포함될 자세한 과제 구조 요구사항으로 지침을 복잡하게 만들고 싶지 않습니다.

모든 과제가 동일한 패턴과 구조를 따르도록 하여 학생들이 일관된 경험을 하도록 하고 싶지만, 이러한 규칙은 과제 파일로 작업할 때만 적용되어야 합니다.

### 📖 이론: 사용자 지정 지침 파일

지침 파일(`*.instructions.md`)은 프로젝트의 특정 파일이나 디렉토리에 대해 Copilot에 목표가 있는 지침을 제공합니다.

모든 곳에 적용되는 저장소 전체 지침과 달리, 이 파일들은 [frontmatter](https://jekyllrb.com/docs/front-matter/)의 `applyTo` 필드를 사용하여 [glob 구문](https://code.visualstudio.com/docs/editor/glob-patterns)으로 특정 파일을 대상으로 합니다. 이는 해당 패턴과 일치하는 파일 작업 시 지침을 자동으로 적용합니다. 또는 Copilot Chat의 **컨텍스트 추가** 버튼을 사용하여 수동으로 지침을 첨부할 수 있습니다.

Visual Studio Code는 기본적으로 `.github/instructions/` 디렉토리에서 `*.instructions.md` 파일을 검색합니다.

> [!TIP]
> 지침은 작업 **방법**에 초점을 맞추어야 합니다 - 코드베이스의 해당 부분에서 사용되는 지침, 표준 및 규칙을 설명합니다.

자세한 내용은 [VS Code Docs: 사용자 지정 지침](https://code.visualstudio.com/docs/copilot/copilot-customization#_custom-instructions) 페이지를 참조하세요.

### ⌨️ 활동: 과제별 지침 생성

이제 과제 파일에만 적용되는 목표가 있는 지침을 생성하여 일관된 구조와 형식을 보장해봅시다.

1. 먼저 기존 과제 템플릿을 살펴봅시다. `templates/assignment-template.md`를 열어 모든 과제가 따라야 할 구조를 확인합니다.

1. 다음과 같은 새 파일을 생성합니다:

   ```text
   .github/instructions/assignments.instructions.md
   ```


1. 다음 내용을 추가하여 과제 형식 지정 표준을 정의합니다. 또한 `assignments` 디렉토리의 Markdown(`.md`) 파일로 모든 채팅 요청에 자동으로 적용됩니다.

   ```markdown
   ---
   applyTo: "assignments/**/*.md"
   ---

   # 과제 Markdown 구조 지침

   모든 과제 마크다운 파일은 다음 지침을 따라야 합니다:

   ## 1. 템플릿 사용

   - 과제 마크다운 파일은 [`templates/assignment-template.md`](../../templates/assignment-template.md)의 구조를 따라야 합니다.
   - 과제는 `README.md` 파일로 생성되어야 합니다.
   - 템플릿의 필수 섹션을 제거하거나 건너뛰지 마세요.

   ## 2. 섹션 지침

   섹션 제목은 템플릿의 구조를 반영해야 하며, 정확한 아이콘 사용을 포함합니다.

   - **제목**: `[Assignment Title]`을 짧고 설명적인 이름으로 바꿉니다 (예: `Python 기초`, `반복문과 조건문`, `함수와 모듈`).
   - **목표**: 학생이 배울 내용이나 달성할 내용을 요약하는 1~2 문장을 작성합니다. 주요 기술이나 개념에 초점을 맞춥니다.
   - **작업**: 각 작업:
      - 구체적이고 행동 지향적인 작업 이름 사용
      - 설명에서 학생이 무엇을 해야 하는지 명확하게 명시합니다.
      - 요구사항에서 글머리 기호를 사용하여 예상되는 결과나 기능을 나열합니다. 구체적이고 측정 가능합니다.
      - 도움이 되는 경우 코드 블록에 예제 입력/출력을 제공합니다.

   명시적으로 지정되지 않는 한 추가 섹션을 포함하지 마세요.
   ```

### ⌨️ 활동: 과제 지침 테스트

1. VS Code에서 파일 `assignments/games-in-python/README.md`를 엽니다. 이 과제는 설정한 모든 규칙과 일치하지 않습니다.

1. 이 과제 파일의 현재 구조를 검토해봅시다. 앞서 시험해본 템플릿 구조와 어떻게 다른지 참고합니다. **Site Preview** 탭에서 현재 어떻게 보이는지도 확인할 수 있습니다.

1. 과제 파일이 열린 상태에서 `Agent` 모드의 Copilot에 과제 구조를 업데이트하도록 요청합니다:

   > ![Static Badge](https://img.shields.io/badge/-Prompt-text?style=social&logo=github%20copilot)
   >
   > ```prompt
   > 이 과제 파일을 프로젝트 표준 및 템플릿 구조에 맞게 업데이트해줘
   > ```

1. Copilot이 일반적인 프로젝트 지침과 과제 특정 지침 파일을 어떻게 참조하는지 보세요.

   <img width="492" height="376" alt="Copilot 채팅에서 참조된 파일을 보여주는 스크린샷" src="https://github.com/user-attachments/assets/dbf26be3-5940-4619-af4e-0a4380f16494" />

1. 제안된 변경사항을 원본 파일 구조와 비교하여 Copilot이 지침을 어떻게 적용했는지 확인합니다. 제안된 변경사항을 적용하고 업데이트된 과제가 **Site Preview**에서 어떻게 보이는지 확인합니다.

1. 두 파일 모두 `main` 브랜치에 커밋하고 GitHub에 변경사항을 푸시합니다.

   - `.github/instructions/assignments.instructions.md`
   - `assignments/games-in-python/README.md`

1. Mona가 다음 단계를 준비할 때까지 기다립니다!

<details>
<summary>문제가 있으신가요? 🤷</summary><br/>

- 두 파일 모두 `main` 브랜치에 커밋했는지 확인하세요:
  - `.github/instructions/assignments.instructions.md`
  - `assignments/games-in-python/README.md`

</details>
