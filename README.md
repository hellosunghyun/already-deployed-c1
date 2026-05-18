# 배포했는데요? 1기 — 1회차 자료 저장소

이 저장소는 **1회차 수업을 Markdown 문서만으로 진행하기 위한 자료 묶음**입니다.
PPT나 Slidev 없이, Markdown 뷰어에서 문서를 넘겨가며 설명하고 실습합니다.

## 오늘의 목표

**[Astro](https://astro.build/) 개인 홈페이지 첫 버전을 만들고, [GitHub Pages](https://pages.github.com/)로 배포해 `github.io` 링크 하나를 갖습니다.**

오늘의 진짜 목표는 단순히 홈페이지를 만드는 것이 아닙니다.

- [Codex](https://chatgpt.com/codex) 같은 코딩 에이전트에게 일을 맡기는 법
- 목표와 맥락을 충분히 주는 법
- 실행 전에 계획을 확인하는 법
- 결과를 브라우저와 로그로 검증하는 법
- [Git](https://git-scm.com/)과 [GitHub](https://github.com/)를 이용해 안전하게 작업을 저장하는 법

을 함께 익히는 것입니다.

## 자료 구조

### 발표자료

발표자료는 슬라이드별 Markdown 파일로 나누었습니다.

- [발표자료 인덱스](./sessions/01/presentation/README.md)
- [Slide 01. 표지](./sessions/01/presentation/slides/01-title.md)
- [Slide 02. 오늘의 성공 기준](./sessions/01/presentation/slides/02-success.md)
- [Slide 03. vibe coding 다시 정의하기](./sessions/01/presentation/slides/03-vibe-coding.md)
- [Slide 04. AI에게 맥락이 필요한 이유](./sessions/01/presentation/slides/04-context.md)
- [Slide 05. 좋은 요청의 9요소](./sessions/01/presentation/slides/05-good-request.md)
- [Slide 06. 코딩 에이전트 공통 루프](./sessions/01/presentation/slides/06-agent-loop.md)
- [Slide 07. 오늘 깊게 안 들어갈 것](./sessions/01/presentation/slides/07-scope.md)
- [Slide 08. 웹사이트와 정적 사이트](./sessions/01/presentation/slides/08-website-static.md)
- [Slide 09. 왜 Astro인가](./sessions/01/presentation/slides/09-why-astro.md)
- [Slide 10. 왜 GitHub가 필요한가](./sessions/01/presentation/slides/10-why-github.md)
- [Slide 11. Git과 commit을 왜 써야 하나](./sessions/01/presentation/slides/11-git-commit.md)
- [Slide 12. GitHub Pages란](./sessions/01/presentation/slides/12-github-pages.md)
- [Slide 13. 오늘 만들 흐름](./sessions/01/presentation/slides/13-flow.md)
- [Slide 14. Codex 데모 흐름](./sessions/01/presentation/slides/14-codex-demo.md)
- [Slide 15. 다른 도구 사용자는 어떻게 따라오나](./sessions/01/presentation/slides/15-other-tools.md)
- [Slide 16. 다음 세션에는 무엇이 달라지나](./sessions/01/presentation/slides/16-next-sessions.md)
- [Slide 17. Notion은 왜 나중에 쓰나](./sessions/01/presentation/slides/17-why-notion-later.md)
- [Slide 18. 워크북 사용법](./sessions/01/presentation/slides/18-workbook.md)

### 워크북

워크북은 단계별로 작게 나누었습니다. 각 파일은 **다음 단계로 넘어가기 전 확인할 Ready Gate**, **힌트**, **퀴즈**, **한국어 프롬프트**를 포함합니다.

- [워크북 인덱스](./sessions/01/workbook/README.md)
- [00. 워크북 사용법](./sessions/01/workbook/00-how-to-use.md)
- [01. 시작 전 체크](./sessions/01/workbook/01-start-check.md)
- [02. AI 에이전트 사용 원칙](./sessions/01/workbook/02-ai-agent-principles.md)
- [03. Codex에서 프로젝트 폴더 열기](./sessions/01/workbook/03-open-folder-in-codex.md)
- [04. 환경 확인과 설치](./sessions/01/workbook/04-environment-check-install.md)
- [05. AGENTS.md / CLAUDE.md 만들기](./sessions/01/workbook/05-agent-instruction-file.md)
- [06. Astro 프로젝트 만들기](./sessions/01/workbook/06-create-astro-project.md)
- [07. localhost에서 확인하기](./sessions/01/workbook/07-run-local-preview.md)
- [08. Home 페이지 초안 만들기](./sessions/01/workbook/08-homepage-draft.md)
- [09. Git 기초와 자주 commit하기](./sessions/01/workbook/09-git-basics-commit.md)
- [10. GitHub 저장소 만들기](./sessions/01/workbook/10-create-github-repo.md)
- [11. GitHub에 코드 올리기](./sessions/01/workbook/11-push-to-github.md)
- [12. GitHub Pages 배포하기](./sessions/01/workbook/12-deploy-github-pages.md)
- [13. 결과 기록과 다음 숙제](./sessions/01/workbook/13-record-result-homework.md)

### 1회차 완료 예제

워크북을 끝까지 진행하지 못한 참가자는 아래 예제를 기준 상태로 사용할 수 있습니다.

- [1회차 완료 예제 코드베이스](./sessions/01/example-homepage)
- [예제 실행 방법](./sessions/01/example-homepage/README.md)

실행:

```bash
cd sessions/01/example-homepage
npm install
npm run dev
```

### 템플릿

- [AGENTS.md 템플릿](./sessions/01/templates/AGENTS.md)
- [CLAUDE.md 템플릿](./sessions/01/templates/CLAUDE.md)
- [GitHub Pages 배포 workflow 예시](./sessions/01/templates/deploy.yml)

### 참고 링크

- [참고 링크 모음](./resources/references.md)

## 진행 방식

1. 앞부분은 [발표자료](./sessions/01/presentation/README.md)를 보며 설명합니다.
2. 이후 참가자는 [워크북](./sessions/01/workbook/README.md)을 따라 각자 진행합니다.
3. 진행자는 중간중간 전체 체크만 합니다.
4. 막히면 먼저 해당 단계의 **힌트**를 봅니다.
5. 그래도 안 되면 AI에게 질문하거나 도움을 요청합니다.

## 오늘의 핵심 문장

> AI에게 코딩을 맡기는 것은 책임을 넘기는 것이 아닙니다.  
> 반복 작업을 위임하고, 검증 책임을 더 명확히 갖는 것입니다.
