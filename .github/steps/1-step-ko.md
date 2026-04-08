## Step 1: Copilot 지침 설정

당신은 Mergington 고등학교의 선생님으로 학생들을 위한 숙제와 코딩 연습 문제를 만듭니다. 이러한 과제를 공유하기 위한 정적 웹사이트를 유지하고 있으며, AI 보조자들이 일관된 코드 품질과 프로젝트 구조를 보장하도록 일반적인 기준을 설정하고 싶습니다.

Copilot 지침이 도움이 될 수 있다고 들었습니다!

<details>
<summary>웹사이트 스크린샷 📸</summary><br/>

첫 번째 활동에서 이 웹사이트를 실행할 것입니다!

<img width="600" alt="homework 웹사이트 스크린샷" src="https://github.com/user-attachments/assets/2383b6e9-64d5-4907-94b3-b67153efb008" />

</details>

### 📖 이론: 저장소 사용자 지정 지침이란?

저장소 사용자 지정 지침은 Copilot에 저장소별 특정 지침 및 선호도를 제공하여 프로젝트 컨텍스트 및 표준을 이해하는 데 도움을 줍니다. `.github/copilot-instructions.md` 파일을 생성하면 Copilot의 제안이 항상 프로젝트 규칙과 코딩 표준을 따르도록 할 수 있습니다.

완전한 지침 세트는 저장소의 Copilot Chat에 제출하는 모든 요청에 자동으로 추가됩니다.

> [!TIP]
> 지침을 간단하고 프로젝트의 "방법"에 초점을 맞추세요. 여기에는 목적, 폴더 구조, 코딩 표준, 주요 도구, 예상 형식 등이 포함될 수 있습니다.

자세한 내용은 [GitHub Docs: 저장소 사용자 지정 지침](https://docs.github.com/en/copilot/how-tos/custom-instructions/adding-repository-custom-instructions-for-github-copilot) 페이지를 참조하세요.

### ⌨️ 활동: 교육용 웹사이트 프로젝트 탐색

사용자 지정 지침으로 작업하기 위해 먼저 개발 환경을 설정하고 프로젝트 구조를 탐색해봅시다.

1. 아래 버튼을 마우스 오른쪽 버튼으로 클릭하여 새 탭에서 **Codespace 생성** 페이지를 엽니다. 기본 설정을 사용합니다.

   [![GitHub Codespaces에서 열기](https://github.com/codespaces/badge.svg)](https://codespaces.new/{{full_repo_name}}?quickstart=1)

1. **저장소** 필드가 원본이 아닌 복사본인지 확인한 다음 녹색 **Codespace 생성** 버튼을 클릭합니다.

   - ✅ 복사본: `/{{full_repo_name}}`
   - ❌ 원본: `/skills/customize-your-github-copilot-experience`

1. 브라우저에서 Visual Studio Code가 로드되고 모든 확장 프로그램이 설치될 때까지 잠시 기다립니다.

   - **Live Preview** 확장 프로그램이 활성화되었는지 확인합니다.
   - **Python** 확장 프로그램이 활성화되었는지 확인합니다.

1. `index.html`을 마우스 오른쪽 버튼으로 클릭하고 **프리뷰 표시**를 선택하여 작동하는 웹사이트를 봅니다.

   > ❕ **중요**: 프리뷰 탭을 열어두어 라이브 업데이트를 확인합니다. 이 연습 과정 전체에서 편집을 수행할 것입니다.

1. 프로젝트 구조를 탐색합니다:

   - `assets/` 폴더를 탐색하여 웹사이트 자산(CSS, JavaScript, 이미지)을 봅니다.
   - `assignments/` 폴더를 살펴보고 기존 과제 형식을 이해합니다.
   - 루트 디렉토리의 `index.html`을 검토하여 주요 웹사이트 구조를 확인합니다.
   - 루트 디렉토리의 `config.json`을 검토하여 과제가 어떻게 설정되어 있는지 확인합니다.

### ⌨️ 활동: 저장소 Copilot 지침 생성

프로젝트를 탐색했으므로 이제 Copilot이 교육 웹사이트 프로젝트를 이해하도록 도와주는 사용자 지정 지침을 생성해봅시다.

1. VS Code에서 다음과 같은 새 파일을 생성합니다:

   ```text
   .github/copilot-instructions.md
   ``` 

   > ❕ **중요:** 파일 이름이 올바른지 확인하세요. Copilot이 인식하려면 이 특정 파일 이름이 필요합니다.

1. 다음 내용을 추가하여 Copilot이 프로젝트의 목적, 구조 및 요구사항을 이해하도록 합니다:

   ```markdown
   # 프로젝트 설명

   이 프로젝트는 학생들과 숙제 및 코딩 연습 문제를 공유하기 위한 교육용 웹사이트입니다. 학생들은 포털에서 직접 과제를 검색, 확인 및 다운로드할 수 있습니다.

   ## 프로젝트 구조

   - [`assignments/`](../assignments/) 각 숙제 과제는 일관된 구조의 자체 하위 폴더에 저장됩니다.
   - [`templates/`](../templates/) 새 콘텐츠용 재사용 가능한 템플릿
   - [`assets/`](../assets/) CSS, JavaScript, 이미지 및 설정 파일을 포함한 웹사이트 자산 포함
   - [`index.html`](../index.html) 과제를 검색하고 보기 위한 정적 포털로 사용되는 주요 웹사이트 페이지. 콘텐츠는 [`config.json`](../config.json) 파일을 통해 구성 가능하여 과제 목록 및 세부 정보를 동적으로 생성합니다.

   ## 프로젝트 지침

   - 모든 페이지에서 일관된 스타일 유지
   - 파일 및 폴더 이름은 설명적이고 체계적으로 유지

   ## 교육 표준

   이 프로젝트의 콘텐츠를 생성할 때:

   - **학습 중심**: 모든 콘텐츠는 명확한 학습 목표와 적절한 난이도 수준으로 설계되어야 합니다.
   - **학생 친화적**: 학생들을 동기 부여하는 명확하고 격려적인 언어를 사용합니다.
   ```

1. Copilot에 프로젝트에 대해 묻거나 테스트해봅시다:

   > ![Static Badge](https://img.shields.io/badge/-Prompt-text?style=social&logo=github%20copilot)
   >
   > ```prompt
   > 이 프로젝트를 간단히 설명해줘
   > ```
