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

```md
# Design Backlog

디자인 수정 항목을 관리하는 폴더입니다.

## Items

| ID | Target | Status |
|---|---|---|
| D-001 | [Target] | planned |

## Status

성공: planned → doing → done

차단: planned → doing → blocked
```

## `docs/design-backlog/D-001.md`

```md
# D-001. [수정 제목]

Status: planned

## Scope

- Where (URL + Viewport): [입력]
- Target: [입력]
- Evidence: [스크린샷 경로, 첨부명 또는 Browser 주석]
- Problem: [입력]
- Direction: [입력]
- Constraint: [입력]

## Reference

- Reference URL: [입력]
- Selected element: [입력]
- Bring: [입력]
- Avoid: [입력]

## Token brief

- Color: [입력]
- Typography: [입력]
- Spacing: [입력]
- Radius: [입력]
- Border: [입력]
- Shadow: [입력]
- Component: [입력]

## Allowed files

- [파일 경로]

## Do not change

- [유지할 파일·데이터·배포 설정]

## Approved plan

- 승인 문장: [입력]
- 02단계 최종 Plan 위치: [현재 채팅 또는 기록 위치]

## Steps

1. [02단계에서 확정한 구현 단계]

## Verification plan

- [ ] @Browser 또는 일반 브라우저로 현재 desktop 확인
- [ ] 390x844 확인
- [ ] keyboard focus 확인
- [ ] 읽기 쉬운 contrast 확인
- [ ] 관련 링크 클릭과 route 확인
- [ ] `npm run build`
- [ ] `git status`와 실제 변경 파일 확인
- [ ] GitHub Pages의 asset과 내부 링크 확인

## Result

- Summary: [작업 전에는 비워둠]
- Actual changed files: [작업 전에는 비워둠]
- Before screenshot: [작업 전 경로 또는 첨부명]
- After screenshot: [작업 후 경로 또는 첨부명]
- Before: [작업 전 관찰]
- After: [작업 후 관찰]
- Current desktop: [not run]
- 390x844: [not run]
- Keyboard focus: [not run]
- Contrast: [not run]
- Links and routes: [not run]
- Build: [not run]
- Failure log: [없음]
- Commit: [not run]
- Push: [not run]
- Deployment decision: [not run / deploy / no-deploy]
- GitHub Actions: [not run]
- GitHub Pages: [not run / URL]
- Pages asset and links: [not run]
- Remaining issue: [없음 / 입력]
- Next action: [없음 / 입력]
```

## 1. 파일 생성 미리보기

```text
현재 레포에 3회차 디자인 백로그를 만들 계획만 보여줘.

D-001 입력값:
- 제목: [입력]
- Where (URL + Viewport): [입력]
- Target: [입력]
- Evidence: [스크린샷 경로, 첨부명 또는 Browser 주석]
- Problem: [입력]
- Direction: [입력]
- Constraint: [입력]
- Reference URL: [입력]
- Selected element: [입력]
- Bring: [입력]
- Avoid: [입력]
- Color: [입력]
- Typography: [입력]
- Spacing: [입력]
- Radius: [입력]
- Border: [입력]
- Shadow: [입력]
- Component: [입력]
- Allowed files: [파일 경로 목록]
- Do not change: [유지할 파일·데이터·배포 설정]
- 승인 문장: [입력]
- 02단계 최종 Plan 위치: [입력]
- Steps: [최종 Plan의 구현 단계]
- Before screenshot: [파일 경로 또는 첨부명]

만들 파일:
- docs/design-backlog/README.md
- docs/design-backlog/D-001.md

조건:
- README.md에는 인덱스와 상태 흐름만 둬.
- D-001.md에는 6좌표, 레퍼런스, 7개 토큰, Allowed files, Do not change, Approved plan, Steps, 검증 계획, 빈 Result를 둬.
- 상태는 planned로 시작해.
- AGENTS.md에는 백로그 본문을 넣지 마.
- 아직 어떤 파일도 수정하지 말고 두 파일의 전체 문안만 보여줘.
```

## 2. 승인 후 실제 파일 생성

```text
아래 승인된 값으로 디자인 백로그 파일을 실제 생성해줘.

D-001 입력값:
- 제목: [입력]
- Where (URL + Viewport): [입력]
- Target: [입력]
- Evidence: [스크린샷 경로, 첨부명 또는 Browser 주석]
- Problem: [입력]
- Direction: [입력]
- Constraint: [입력]
- Reference URL: [입력]
- Selected element: [입력]
- Bring: [입력]
- Avoid: [입력]
- Color: [입력]
- Typography: [입력]
- Spacing: [입력]
- Radius: [입력]
- Border: [입력]
- Shadow: [입력]
- Component: [입력]
- Allowed files: [파일 경로 목록]
- Do not change: [유지할 파일·데이터·배포 설정]
- 승인 문장: [입력]
- 02단계 최종 Plan 위치: [입력]
- Steps: [최종 Plan의 구현 단계]
- Before screenshot: [파일 경로 또는 첨부명]

조건:
- `docs/design-backlog/README.md`를 만든다.
- `docs/design-backlog/D-001.md`를 만든다.
- README 인덱스의 D-001 상태와 D-001 본문의 Status를 모두 planned로 맞춘다.
- Result 검증값은 실행 전이므로 `not run`으로 둔다.
- AGENTS.md와 구현 파일은 수정하지 않는다.
- 생성 후 실제 파일 경로와 핵심 내용을 요약한다.
- D-001 구현은 아직 시작하지 않는다.
```

## 완료 후 상태 갱신 미리보기

```text
아래 확인된 결과만 docs/design-backlog/D-001.md와 docs/design-backlog/README.md에 반영할 변경 문안으로 보여줘.

결과 입력값:
- 최종 Status: [done / blocked]
- Summary: [한 문장 결과 요약]
- 실제 변경 파일: [파일 경로 목록]
- Before screenshot: [경로 또는 첨부명]
- After screenshot: [경로 또는 첨부명]
- Before: [관찰]
- After: [관찰]
- Current desktop: [pass / fail / not run]
- 390x844: [pass / fail / not run]
- Keyboard focus: [pass / fail / not run]
- Contrast: [pass / fail / not run]
- Links and routes: [pass / fail / not run]
- Build: [pass / fail / not run]
- Failure log: [없음 / 핵심 오류]
- Commit SHA와 메시지: [없음 / 입력]
- Push: [pass / fail / not run]
- Deployment decision: [deploy / no-deploy]
- GitHub Actions: [pass / fail / not run]
- GitHub Pages URL과 결과: [입력]
- Pages asset and links: [pass / fail / not run]
- Remaining issue: [없음 / 입력]
- Next action: [없음 / 입력]

조건:
- 확인하지 않은 값은 성공으로 추정하지 마.
- current desktop, 390x844, keyboard focus, contrast, links and routes, Build, Push, GitHub Actions, 실제 GitHub Pages, Pages asset and links가 모두 pass이고 commit SHA가 있을 때만 done으로 판정해.
- fail, not run, 진행 중, 확인 불가, no-deploy 중 하나라도 남으면 입력된 Status와 관계없이 blocked로 판정하고 이유와 Next action을 제안해.
- D-001 본문과 README 인덱스의 상태를 같은 값으로 제안해.
- 아직 파일을 수정하지 말고 변경 문안만 보여줘.
```

## 승인 후 상태 갱신

```text
docs/design-backlog/D-001.md와 docs/design-backlog/README.md에 아래 확인된 결과를 실제 반영해줘.

결과 입력값:
- 최종 Status: [done / blocked]
- Summary: [한 문장 결과 요약]
- 실제 변경 파일: [파일 경로 목록]
- Before screenshot: [경로 또는 첨부명]
- After screenshot: [경로 또는 첨부명]
- Before: [관찰]
- After: [관찰]
- Current desktop: [pass / fail / not run]
- 390x844: [pass / fail / not run]
- Keyboard focus: [pass / fail / not run]
- Contrast: [pass / fail / not run]
- Links and routes: [pass / fail / not run]
- Build: [pass / fail / not run]
- Failure log: [없음 / 핵심 오류]
- Commit SHA와 메시지: [없음 / 입력]
- Push: [pass / fail / not run]
- Deployment decision: [deploy / no-deploy]
- GitHub Actions: [pass / fail / not run]
- GitHub Pages URL과 결과: [입력]
- Pages asset and links: [pass / fail / not run]
- Remaining issue: [없음 / 입력]
- Next action: [없음 / 입력]

조건:
- 확인하지 않은 값은 성공으로 추정하지 마.
- current desktop, 390x844, keyboard focus, contrast, links and routes, Build, Push, GitHub Actions, 실제 GitHub Pages, Pages asset and links가 모두 pass이고 commit SHA가 있을 때만 done으로 갱신해.
- fail, not run, 진행 중, 확인 불가, no-deploy 중 하나라도 남으면 입력된 Status와 관계없이 blocked로 갱신하고 이유와 Next action을 기록해.
- D-001 본문과 README 인덱스의 상태를 같은 값으로 갱신해.
- 백로그 두 파일 외에는 수정하지 마.
- 반영 후 변경한 필드와 최종 상태를 요약해줘.
```
