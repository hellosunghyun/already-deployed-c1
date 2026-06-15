# 09. 디자인 백로그 폴더 만들기

## 목표

`AGENTS.md`에는 **규칙과 참조 경로만** 적고, 실제 디자인 백로그는 별도 폴더에 적습니다.

```text
AGENTS.md = 작업 규칙

docs/design-backlog/ = 실제 수정 항목
```

## 만들 구조

프로젝트 루트에 아래 폴더를 만듭니다.

```text
docs/
└── design-backlog/
    ├── README.md
    └── D-001.md
```

## AGENTS.md에 넣을 규칙

```markdown
## 3회차 디자인 작업 규칙

- 새 프로젝트를 만들지 않고 기존 Astro 개인 홈페이지에서 이어서 작업한다.
- 디자인 수정 전에는 Plan mode 또는 계획 응답을 먼저 사용한다.
- 스크린샷, 브라우저 주석, URL, viewport를 기준으로 Target을 좁힌다.
- 한국어 UI에서는 `@브라우저`, 영어 UI에서는 `@Browser`를 사용해 화면을 확인한다.
- 레퍼런스는 전체 복제하지 않고 선택한 요소 하나만 토큰으로 적용한다.
- 새 라이브러리, 외부 font, 무거운 animation은 사용자 승인 없이 추가하지 않는다.
- 수정 후 desktop, 390px 모바일, `npm run build`로 확인한다.
- 디자인 백로그 본문은 `AGENTS.md`에 적지 않는다.
- 디자인 백로그는 `docs/design-backlog/` 폴더의 Markdown 파일로 관리한다.
- 한 번에 하나의 백로그 파일만 실행한다. 예: `docs/design-backlog/D-001.md`.
- 작업 후 완료 상태와 검증 결과는 해당 백로그 파일에 갱신한다.
```

## `docs/design-backlog/README.md` 예시

```markdown
# Design Backlog

3회차 디자인 수정 항목을 관리하는 폴더입니다.
`AGENTS.md`는 이 폴더를 참조하는 규칙만 갖고, 실제 수정 내용은 여기에 둡니다.

## Items

| ID | Target | Status |
|---|---|---|
| D-001 | /projects 첫 번째 카드 | planned |

## Status

planned → doing → done → blocked
```

## `docs/design-backlog/D-001.md` 예시

```markdown
# D-001. Projects 카드 위계 개선

Status: planned

## Scope

- URL: /projects
- Viewport: 390x844
- Target: 첫 번째 프로젝트 카드

## Problem

제목, 설명, 태그의 위계가 약해서 카드 안에서 무엇을 먼저 읽어야 하는지 불분명하다.

## Direction

제목 굵기와 간격을 조정하고, 설명과 태그의 톤을 낮춘다.

## Reference

- Reference URL: https://styles.refero.design/
- Selected element: Project card framing
- Bring: 카드 gap, muted text 위계, 얇은 border
- Avoid: 전체 dark theme, logo, animation, 외부 font

## Allowed files

- src/pages/projects.astro
- src/styles/global.css

## Verification

- @브라우저 또는 @Browser로 desktop 확인
- 390px 모바일 확인
- npm run build

## Result

- 변경 후 작성
```

## Codex에게 보낼 프롬프트

```text
3회차 디자인 백로그를 정리하고 싶어.

중요:
- AGENTS.md에는 규칙과 `docs/design-backlog/` 참조만 넣어.
- 실제 D-001 내용은 AGENTS.md에 적지 말고 `docs/design-backlog/D-001.md`에 적어.
- `docs/design-backlog/README.md`에는 백로그 인덱스만 만들어.
- 기존 AGENTS.md 규칙은 지우지 마.
- 너무 긴 규칙 파일로 만들지 마.
- 아직 수정하지 말고 만들 파일과 추가할 문안만 먼저 보여줘.

백로그 항목:
- ID: D-001
- URL: [입력]
- Viewport: [입력]
- Target: [입력]
- Problem: [입력]
- Direction: [입력]
- Reference: [입력]
- Selected element: [입력]
- Bring: [입력]
- Avoid: [입력]
- Verification: @브라우저 또는 @Browser 확인, 390px 모바일, npm run build
```

## Ready Gate

- [ ] `AGENTS.md`에는 백로그 규칙과 경로만 있다.
- [ ] `docs/design-backlog/README.md`가 있다.
- [ ] `docs/design-backlog/D-001.md`가 있다.
- [ ] 오늘 실행할 항목이 하나로 좁혀졌다.

## 다음 단계

[10. 플랜 실행하기 →](./10-execute-plan.md)
