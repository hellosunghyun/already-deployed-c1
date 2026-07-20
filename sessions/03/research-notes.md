# 3회차 웹 리서치 노트

마지막 확인: 2026-07-20

이 문서는 3회차 자료에 직접 반영한 Codex Plan mode, Browser, `AGENTS.md`, DESIGN.md 레퍼런스의 근거와 수업 범위를 기록합니다. 제품 UI와 기능 제공 여부는 플랜·워크스페이스·롤아웃에 따라 달라질 수 있으므로, 수업에는 스크린샷 대체 경로를 함께 둡니다.

## Codex Plan mode

OpenAI Codex Best Practices는 복잡하거나 모호한 작업에서는 코딩 전에 계획을 세우라고 안내합니다. Plan mode는 Codex가 맥락을 모으고, 필요한 질문을 하고, 구현 전 더 강한 계획을 만들게 하는 용도이며 `/plan` 또는 `Shift`+`Tab`으로 전환할 수 있다고 설명합니다.

- 참고: [OpenAI Developers — Codex Best practices](https://developers.openai.com/codex/learn/best-practices)

Codex app 명령 문서에서도 `/plan`은 multi-step planning을 위한 slash command로 설명됩니다. 계획을 먼저 다듬은 뒤 목표나 실행으로 넘어가는 흐름이 적합합니다.

- 참고: [OpenAI Developers — Codex app commands](https://developers.openai.com/codex/app/commands)

Codex CLI 문서도 `/plan` 입력으로 plan mode에 들어가며, inline prompt나 이미지 첨부도 함께 사용할 수 있다고 안내합니다.

- 참고: [OpenAI Developers — Codex CLI slash commands](https://developers.openai.com/codex/cli/slash-commands)

## Codex Browser

Codex의 built-in Browser는 사용자와 Codex가 같은 렌더링 화면을 보고 visual comment를 남길 수 있게 합니다. 로컬 앱 확인은 개발 서버를 먼저 실행하고, 터미널에 표시된 실제 Local URL을 열어야 합니다. Codex CLI와 IDE extension에서는 built-in Browser를 사용할 수 없으므로 데스크톱 앱 또는 스크린샷 대체 경로가 필요합니다.

- 참고: [OpenAI Developers — In-app browser](https://developers.openai.com/codex/app/browser)

공식 절차는 ChatGPT 데스크톱 앱에서 Codex를 선택하고, Plugins Directory에서 Browser를 설치한 뒤 `@Browser`로 참조하는 순서입니다. 화면 주석은 Annotation mode를 켜고 요소를 클릭하거나 영역을 드래그한 뒤, 주석을 작성·저장하고 채팅에서 반영을 요청합니다.

- 참고: [OpenAI Developers — In-app browser / Browser use](https://developers.openai.com/codex/app/browser)

공식 문서의 호출명은 `@Browser`입니다. 한국어 UI의 메뉴명과 권한 문구는 버전에 따라 다를 수 있지만, 수업의 권한 기본 선택은 `나 대신 승인`으로 통일합니다. Browser가 없거나 자동완성되지 않으면 일반 브라우저에서 스크린샷을 찍고 `Where (URL + Viewport) / Target / Evidence / Problem / Direction / Constraint`를 함께 전달합니다.

## AGENTS.md 활용

OpenAI Codex Best Practices는 반복되는 작업 규칙을 `AGENTS.md`에 넣으라고 안내합니다. 좋은 `AGENTS.md`에는 repo layout, 실행 방법, build/test/lint, 제약, 완료 기준과 검증 방법이 들어갑니다.

- 참고: [OpenAI Developers — Codex Best practices / AGENTS.md](https://developers.openai.com/codex/learn/best-practices)

3회차에서는 `AGENTS.md`에 디자인 작업 규칙과 백로그 위치만 둡니다. 실제 백로그 항목은 `docs/design-backlog/`의 별도 Markdown 파일로 관리합니다. 이렇게 하면 Codex가 반복 규칙은 항상 읽고, 수정 항목은 필요한 파일만 참조하게 할 수 있습니다.

## DESIGN.md 레퍼런스

- [getdesign.md](https://getdesign.md/)는 DESIGN.md analysis를 patterns, tokens, rules 관점의 coding agent inspiration으로 소개합니다.
- [Refero Styles](https://styles.refero.design/)는 AI-readable design systems를 colors, typography, spacing, components, DESIGN.md 형태로 탐색할 수 있다고 설명합니다.
- [designmd.app](https://designmd.app/)은 DESIGN.md를 project root의 Markdown 파일로 설명하며, colors, typography, visual patterns를 AI agent에게 알려주는 용도로 정리합니다.

수업에서는 세 사이트를 **복제 대상**이 아니라 **토큰 브리프 재료**로 씁니다.

## 3회차에 반영한 운영 원칙

```text
기존 레포에서 이어서 진행한다.
화면 증거, 레퍼런스, 선택 영역을 모은 뒤 Plan mode로 최종 계획을 받는다.
로컬 화면은 데스크톱 앱에서 개발 서버를 먼저 실행하고 실제 Local URL을 연다.
Plugins Directory에서 Browser를 설치하고 공식 호출명 `@Browser`를 사용한다.
Annotation mode에서 요소 클릭 또는 영역 드래그 → 주석 작성·저장 → 채팅 요청 순서로 진행한다.
Browser 권한 기본 선택은 `나 대신 승인`으로 통일한다.
Browser가 없으면 일반 브라우저 스크린샷과 6좌표를 사용한다.
레퍼런스는 원하는 요소 하나만 가져온다.
디자인 백로그는 `docs/design-backlog/`에 남긴다. AGENTS.md에는 해당 위치와 운영 규칙만 남긴다.
백로그 상태는 `planned → doing → done` 또는 `planned → doing → blocked`로 기록한다.
일반 디자인 수정에서는 고급 브라우저 디버깅 주제를 다루지 않는다.
```
