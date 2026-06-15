# 3회차 웹 리서치 노트

## Codex Plan mode

OpenAI Codex Best Practices는 복잡하거나 모호한 작업에서는 코딩 전에 계획을 세우라고 안내합니다. Plan mode는 Codex가 맥락을 모으고, 필요한 질문을 하고, 구현 전 더 강한 계획을 만들게 하는 용도이며 `/plan` 또는 `Shift`+`Tab`으로 전환할 수 있다고 설명합니다.

- 참고: [OpenAI Developers — Codex Best practices](https://developers.openai.com/codex/learn/best-practices)

Codex app 명령 문서에서도 `/plan`은 multi-step planning을 위한 slash command로 설명됩니다. 계획을 먼저 다듬은 뒤 목표나 실행으로 넘어가는 흐름이 적합합니다.

- 참고: [OpenAI Developers — Codex app commands](https://developers.openai.com/codex/app/commands)

Codex CLI 문서도 `/plan` 입력으로 plan mode에 들어가며, inline prompt나 이미지 첨부도 함께 사용할 수 있다고 안내합니다.

- 참고: [OpenAI Developers — Codex CLI slash commands](https://developers.openai.com/codex/cli/slash-commands)

## Codex 브라우저 / Browser

Codex in-app browser는 Codex와 사용자가 같은 렌더링 화면을 보는 기능입니다. 로컬 개발 서버, file-backed preview, 로그인 없는 public page에 적합하며 visual comments를 남길 수 있습니다.

- 참고: [OpenAI Developers — In-app browser](https://developers.openai.com/codex/app/browser)

Browser use는 Codex가 in-app browser를 직접 조작해 클릭, 입력, 렌더링 상태 확인, 스크린샷, read-only page inspection, 수정 검증을 하도록 돕습니다. 공식 문서는 Browser plugin을 설치하고 활성화한 뒤 `@Browser`로 직접 참조할 수 있다고 설명합니다.

- 참고: [OpenAI Developers — In-app browser / Browser use](https://developers.openai.com/codex/app/browser)

수업에서는 한국어 UI의 `@브라우저`와 영어 UI의 `@Browser`를 함께 안내합니다. 태그가 자동완성되지 않으면 설정의 브라우저 플러그인을 켜는 절차를 안내합니다.

## AGENTS.md 활용

OpenAI Codex Best Practices는 반복되는 작업 규칙을 `AGENTS.md`에 넣으라고 안내합니다. 좋은 `AGENTS.md`에는 repo layout, 실행 방법, build/test/lint, 제약, 완료 기준과 검증 방법이 들어갑니다.

- 참고: [OpenAI Developers — Codex Best practices / AGENTS.md](https://developers.openai.com/codex/learn/best-practices)

3회차에서는 디자인 백로그도 `AGENTS.md`의 작은 섹션으로 관리합니다. 이유는 Codex가 다음 턴에서 레포 규칙과 현재 디자인 목표를 함께 읽게 하기 위해서입니다.

## DESIGN.md 레퍼런스

- [getdesign.md](https://getdesign.md/)는 DESIGN.md analysis를 patterns, tokens, rules 관점의 coding agent inspiration으로 소개합니다.
- [Refero Styles](https://styles.refero.design/)는 AI-readable design systems를 colors, typography, spacing, components, DESIGN.md 형태로 탐색할 수 있다고 설명합니다.
- [designmd.app](https://designmd.app/)은 DESIGN.md를 project root의 Markdown 파일로 설명하며, colors, typography, visual patterns를 AI agent에게 알려주는 용도로 정리합니다.

수업에서는 세 사이트를 **복제 대상**이 아니라 **토큰 브리프 재료**로 씁니다.

## 3회차에 반영한 운영 원칙

```text
기존 레포에서 이어서 진행한다.
Plan mode로 먼저 계획을 받는다.
브라우저 태그는 @브라우저 / @Browser를 모두 안내한다.
태그가 안 되면 설정에서 브라우저 플러그인을 켠다.
레퍼런스는 원하는 요소 하나만 가져온다.
디자인 백로그는 AGENTS.md에 남긴다.
일반 디자인 수정에서는 고급 브라우저 디버깅 주제를 다루지 않는다.
```
