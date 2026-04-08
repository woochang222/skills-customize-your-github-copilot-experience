# GitHub Copilot 커스터마이제이션 가이드

GitHub Copilot을 프로젝트에 맞게 설정하고 활용하는 방법을 배우는 종합 가이드입니다.

## 📚 학습 내용

### Step 1: Copilot 지침 설정
**목표**: 저장소 전체의 Copilot 행동 기준 설정

- `.github/copilot-instructions.md` 파일 생성
- 프로젝트 설명, 구조, 코딩 표준 정의
- 교육적 기준(학습 중심, 학생 친화적) 설정
- 모든 Copilot Chat 요청에 자동으로 적용

**핵심 내용**: 프로젝트 전역에 일관된 지침을 제공하여 Copilot의 생성 결과의 품질을 보장합니다.

---

### Step 2: 파일별 지침
**목표**: 특정 파일/디렉토리에만 적용되는 상세 지침 작성

- `.github/instructions/*.instructions.md` 파일 생성
- YAML frontmatter의 `applyTo` 필드로 glob 패턴 지정
- 과제 파일의 마크다운 구조 규칙 정의
- 특정 파일 작업 시에만 해당 지침 자동 적용

**핵심 내용**: 전역 지침을 복잡하게 하지 않으면서 특정 영역의 상세한 표준을 유지합니다.

**예시**: `assignments/**/*.md` 패턴으로 과제 파일의 형식과 구조 통일

---

### Step 3: 재사용 가능한 프롬프트
**목표**: 반복되는 작업을 자동화하는 프롬프트 템플릿 생성

- `.github/prompts/*.prompt.md` 파일 생성
- `/` 명령어로 Copilot Chat에서 쉽게 실행
- 여러 단계의 워크플로우를 하나의 프롬프트로 통합
- 마크다운 링크로 다른 파일/지침/프롬프트 참조

**핵심 내용**: 반복적인 작업(과제 생성, 설정 업데이트 등)을 자동화하여 생산성 향상

**예시**: `/new-assignment` 명령어로 과제 생성부터 설정 업데이트까지 자동 수행

---

### Step 4: 사용자 정의 에이전트
**목표**: 특정 목적에 최적화된 전문 Copilot 에이전트 생성

- `.github/agents/*.agent.md` 파일 생성
- 에이전트별 고유한 성격과 응답 형식 정의
- 도구(검색, 웹 등) 제한 및 설정
- Copilot Chat의 드롭다운에서 선택하여 사용

**핵심 내용**: 일반 Copilot과 달리 특정 역할에 집중한 전문화된 대화 경험 제공

**예시**: `assignment-brainstorming` 에이전트로 과제 아이디어 창출에만 집중

---

## 🗂️ 프로젝트 구조

```
.github/
├── copilot-instructions.md          # 저장소 전역 지침
├── instructions/
│   └── assignments.instructions.md  # 과제 파일 고유 지침
├── prompts/
│   └── new-assignment.prompt.md    # 과제 생성 프롬프트
└── agents/
    └── assignment-brainstorming.agent.md  # 아이디어 창출 에이전트

assignments/              # 학생 과제 모음
templates/               # 과제 템플릿
assets/                  # 웹사이트 리소스(CSS, JS, 이미지)
config.json             # 웹사이트 설정
index.html              # 메인 웹페이지
```

---

## 🎯 핵심 개념 정리

| 파일 타입 | 위치 | 용도 | 범위 |
|----------|------|------|------|
| **copilot-instructions.md** | `.github/` | 프로젝트 전역 기준 | 모든 요청 |
| **\*.instructions.md** | `.github/instructions/` | 파일별 상세 기준 | 패턴 매칭 |
| **\*.prompt.md** | `.github/prompts/` | 반복 작업 자동화 | 명령어(`/`) |
| **\*.agent.md** | `.github/agents/` | 전문화된 대화 경험 | 드롭다운 선택 |

---

## 💡 사용 팁

1. **지침 작성**: "어떤" 것이 아닌 "어떻게"에 초점을 맞추세요
2. **프롬프트 작성**: "무엇을" 해야 하는지 명확하게 정의하세요
3. **에이전트 생성**: 특정 역할에 최적화된 뉘앙스와 제약을 설정하세요
4. **자동화**: 반복되는 워크플로우는 프롬프트로 자동화하세요

---

## 📖 추가 학습 자료

- [GitHub Copilot 커스터마이제이션 문서](https://docs.github.com/en/copilot)
- [VS Code 커스텀 지침 가이드](https://code.visualstudio.com/docs/copilot/copilot-customization)
- [Model Context Protocol(MCP) 통합](https://github.com/skills/integrate-mcp-with-copilot)

