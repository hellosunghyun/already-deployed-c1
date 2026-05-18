# 배포했는데요? 1기 — 수업 자료 저장소

이 저장소는 **배포했는데요? 1기** 전체 수업 자료를 Markdown 문서로 관리하기 위한 저장소입니다.
PPT나 Slidev 없이, Markdown 뷰어에서 발표자료를 넘기고 워크북을 따라 실습하는 방식으로 운영합니다.

1회차만 담는 저장소가 아니라, 여러 회차를 같은 형식으로 누적하는 자료 저장소입니다.

## 과정 목표

참가자는 AI 코딩 에이전트와 함께 [Astro](https://astro.build/) 기반 개인 홈페이지를 만들고, [GitHub Pages](https://pages.github.com/)에 배포하며, 점진적으로 운영 가능한 개인 홈페이지 구조를 갖춥니다.

최종적으로 아래 흐름을 경험하는 것이 목표입니다.

```text
AI에게 목표와 맥락 전달
→ 계획 확인
→ 구현
→ 브라우저와 로그로 검증
→ commit
→ GitHub push
→ GitHub Pages 배포
→ 다음 개선점 기록
```

## 자료 Depth

이 저장소는 자료를 아래 depth로 나눕니다.

```text
Depth 0. 과정 전체
  README.md
  resources/

Depth 1. 회차
  sessions/01/
  sessions/02/

Depth 2. 회차별 자료 유형
  presentation/
  workbook/
  templates/
  example-homepage/  # 있는 회차만

Depth 3. 실제 진행 파일
  presentation/slides/*.md
  workbook/*.md
  templates/*.md
```

루트 README는 전체 과정의 지도 역할만 합니다.
각 회차의 자세한 발표자료 목록과 워크북 단계는 해당 회차의 `README.md`에서 확인합니다.

## 회차별 인덱스

| 회차 | 상태 | 주제 | 핵심 결과물 | 자료 |
|---|---|---|---|---|
| 1회차 | 작성됨 | AI 에이전트와 함께 첫 배포 루프 만들기 | Astro 첫 버전, GitHub 저장소, GitHub Pages URL | [sessions/01](./sessions/01/) |
| 2회차 | 작성됨 | 홈페이지를 읽히는 구조로 나누기 | Home / About / Projects / Posts, Layout, Navigation | [sessions/02](./sessions/02/) |
| 3회차 | 예정 | AI에게 디자인 수정과 요구사항을 정확히 전달하기 | 스크린샷 기반 수정, 브라우저 요소/영역 선택 요청, 모바일 확인, 디자인 개선 | 준비 예정 |
| 4회차 | 예정 | Notion을 콘텐츠 관리 도구처럼 연결하기 | Notion DB, Integration, Notion 기반 Posts | 준비 예정 |
| 5회차 | 예정 | 운영 가능한 개인 홈페이지로 마무리하기 | README, 배포 체크리스트, 선택 도메인, 최종 제출 | 준비 예정 |

## 회차 폴더 구조

각 회차는 가능한 한 같은 구조를 사용합니다.

```text
sessions/XX/
├── README.md
├── presentation/
│   ├── README.md
│   └── slides/
├── workbook/
│   ├── README.md
│   └── 단계별 실습 문서
├── templates/
└── example-homepage/
```

### `presentation/`

진행자가 앞부분에서 짧게 설명할 Markdown 슬라이드입니다.
목표는 긴 강의가 아니라, 워크북에서 헷갈릴 개념을 미리 풀어주는 것입니다.

### `workbook/`

참가자가 직접 따라가는 실습 문서입니다.
각 단계는 가능한 한 아래 구조를 따릅니다.

- 목표
- 왜 하는가
- 쉬운 설명
- AI에게 보낼 프롬프트
- 체크박스
- Ready Gate
- 힌트
- 퀴즈
- 커밋 가이드

### `templates/`

참가자가 복사해서 채울 수 있는 템플릿입니다.
회차에 따라 `AGENTS.md`, `CLAUDE.md`, 프로젝트 카드 데이터, 글 목록 데이터 등이 들어갑니다.

### `example-homepage/`

해당 회차를 끝까지 완료하지 못한 참가자가 기준 상태로 사용할 수 있는 예제입니다.
예제는 원본을 직접 수정하기보다, 개인 작업 폴더로 복사하거나 sparse checkout 해서 사용하는 것을 권장합니다.

## 현재 포함된 자료

### 1회차

- [1회차 자료](./sessions/01/)
- [1회차 발표자료](./sessions/01/presentation/README.md)
- [1회차 워크북](./sessions/01/workbook/README.md)
- [1회차 완료 예제](./sessions/01/example-homepage/)
- 목표: `github.io` 링크까지 이어지는 첫 배포 루프 만들기

### 2회차

- [2회차 자료](./sessions/02/)
- [2회차 발표자료](./sessions/02/presentation/README.md)
- [2회차 워크북](./sessions/02/workbook/README.md)
- [2회차 템플릿](./sessions/02/templates/)
- 목표: Home / About / Projects / Posts 구조와 공통 Layout 만들기

## 진행 방식

각 회차는 아래 흐름을 기본으로 합니다.

```text
0~5분: 오늘 결과물과 성공 기준
5~25분: 필요한 개념 설명
25~30분: Codex 기준 데모
30분 이후: 워크북 Sprint 실습
마지막 10분: 결과 기록 / 막힌 지점 / 숙제 안내
```

현장 상황에 따라 설명 시간이 늘어날 수 있지만, 핵심은 참가자가 워크북을 보고 스스로 이어갈 수 있게 하는 것입니다.

## 공통 원칙

- 설명은 [Codex](https://chatgpt.com/codex) 기준으로 하되, [Claude Code](https://docs.claude.com/en/docs/claude-code), [Antigravity](https://codelabs.developers.google.com/getting-started-google-antigravity) 사용자가 따라올 수 있게 프롬프트를 일반화합니다.
- AI에게 바로 실행시키지 않고 먼저 계획을 받습니다.
- 새 라이브러리, secret, 삭제 명령은 조심스럽게 다룹니다.
- 결과는 브라우저, 로그, `npm run build`, GitHub Actions, GitHub Pages URL로 확인합니다.
- 변경사항은 작은 단위로 commit합니다.

## 참고 링크

- [참고 링크 모음](./resources/references.md)

## 과정의 핵심 문장

> AI에게 코딩을 맡기는 것은 책임을 넘기는 것이 아닙니다.  
> 반복 작업을 위임하고, 검증 책임을 더 명확히 갖는 것입니다.
