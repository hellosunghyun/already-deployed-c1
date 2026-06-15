# 디자인 백로그 폴더 양식

3회차 디자인 백로그는 `AGENTS.md`에 직접 적지 않습니다.
`AGENTS.md`에는 규칙과 경로만 두고, 실제 항목은 `docs/design-backlog/` 폴더에 둡니다.

## 폴더 구조

```text
docs/
└── design-backlog/
    ├── README.md
    └── D-001.md
```

## `docs/design-backlog/README.md`

```markdown
# Design Backlog

디자인 수정 항목을 관리하는 폴더입니다.

## Items

| ID | Target | Status |
|---|---|---|
| D-001 |  | planned |

## Status

planned → doing → done → blocked
```

## `docs/design-backlog/D-001.md`

```markdown
# D-001. [수정 제목]

Status: planned

## Scope

- URL:
- Viewport:
- Target:

## Problem


## Direction


## Reference

- Reference URL:
- Selected element:
- Bring:
- Avoid:

## Allowed files

-

## Verification

- @브라우저 또는 @Browser desktop 확인
- 390px 모바일 확인
- npm run build

## Result

- 완료 후 작성
```

## Codex 요청문

```text
디자인 백로그 폴더를 만들어줘.

조건:
- `docs/design-backlog/README.md`를 만든다.
- `docs/design-backlog/D-001.md`를 만든다.
- AGENTS.md에는 실제 백로그 본문을 적지 않는다.
- AGENTS.md에는 `docs/design-backlog/`를 참조하라는 규칙만 둔다.
- 아직 구현 파일은 수정하지 않는다.
```
