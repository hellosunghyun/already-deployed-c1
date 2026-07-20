# 09. 디자인 계약 파일 실제 생성하기

## 목표

최종 Plan과 선택 브리프를 기준으로 `DESIGN.md`, `AGENTS.md`, `docs/design-backlog/README.md`, `docs/design-backlog/D-001.md`를 실제로 만들거나 갱신합니다.

## 왜 하는가

Plan이 채팅에만 있고 디자인 기준과 작업 결과가 파일로 나뉘어 있지 않으면, 다음 요청에서 범위가 다시 넓어질 수 있습니다.
네 파일의 역할을 분리하면 디자인 방향, 반복 규칙, 작업 인덱스, 오늘 실행할 항목을 서로 섞지 않고 이어갈 수 있습니다.

## 쉬운 설명

| 파일 | 역할 | 넣지 않는 것 |
|---|---|---|
| `DESIGN.md` | 선택한 디자인 토큰과 가져오지 않을 기준 | 오늘 작업의 진행 로그 |
| `AGENTS.md` | 반복해서 지킬 레포 규칙과 문서 경로 | D-001의 상세 내용, 일회성 목표 |
| `docs/design-backlog/README.md` | 백로그 ID·Target·현재 상태 인덱스 | 긴 구현 설명 |
| `docs/design-backlog/D-001.md` | 오늘 실행할 한 항목의 계약과 결과 | D-002 이후의 추가 아이디어 |

## 시작 전에 준비할 것

- [07단계](./07-design-token-brief.md)에서 저장한 `DESIGN.md`
- [08단계](./08-selective-element.md)의 선택 브리프
- 11/12/13 중 선택한 챌린지에서 보완한 화면 증거
- [02단계](./02-plan-mode.md)에서 확정한 최신 Plan

하나라도 없다면 파일을 만들기 전에 해당 단계로 돌아갑니다.

## 만들 구조

```text
프로젝트 루트/
├── DESIGN.md
├── AGENTS.md
└── docs/
    └── design-backlog/
        ├── README.md
        └── D-001.md
```

## 상태 값

상태는 아래 네 값 중 하나만 사용합니다.

| Status | 의미 |
|---|---|
| `planned` | 범위와 Plan을 확정했지만 아직 구현하지 않음 |
| `doing` | 현재 D-001을 구현 중 |
| `done` | 구현과 화면·키보드·build·실제 배포 검증이 모두 끝남 |
| `blocked` | 구현 또는 필수 검증이 막혀 이유를 기록함 |

`done → blocked`처럼 순서대로 이동하는 단계가 아닙니다.

## D-001 필수 구조

```markdown
# D-001. [한 항목 제목]

Status: planned
Design source: ../../DESIGN.md

## Where

- URL:
- Viewport:

## Target

[입력]

## Evidence

- Before screenshot, Browser 주석 또는 관찰 기록:

## Problem

[입력]
## Direction

[입력]
## Constraint

[입력]
## Reference

- Reference URL:
- Selected element:
- Bring:
- Avoid:

## Token brief

- Color:
- Typography:
- Spacing:
- Radius:
- Border:
- Shadow:
- Component:

## Allowed files

- [실제 경로]: [수정이 필요한 이유]

## Do not change

- [유지할 파일·데이터·배포 설정]

## Approved plan

- 승인 문장:
- 02단계 최종 Plan 위치:

## Steps

1. [02단계에서 확정한 구현 단계]

## Verification

- [ ] @Browser 또는 일반 브라우저로 현재 desktop 확인
- [ ] 390x844 확인
- [ ] keyboard focus 확인
- [ ] 읽기 쉬운 contrast 확인
- [ ] 관련 링크 클릭과 route 확인
- [ ] `npm run build`
- [ ] `git status`와 실제 변경 파일 확인
- [ ] GitHub Pages의 asset과 내부 링크 확인

## Result

- Summary: 완료 후 작성
- Actual changed files: 완료 후 작성
- Before screenshot: 작업 전 경로 또는 첨부명
- After screenshot: 작업 후 경로 또는 첨부명
- Before: 작업 전 관찰
- After: 작업 후 관찰
- Current desktop: not run
- 390x844: not run
- Keyboard focus: not run
- Contrast: not run
- Links and routes: not run
- Build: not run
- Failure log: 없음
- Commit: not run
- Push: not run
- Deployment decision: not run / deploy / no-deploy
- GitHub Actions: not run
- GitHub Pages: not run / URL
- Pages asset and links: not run
- Remaining issue: 없음 / 입력
- Next action: 없음 / 입력
```

## 1차 프롬프트: 네 파일 문안 미리 보기

아래 입력란에 08단계 브리프와 02단계 최종 Plan을 그대로 붙여 넣습니다.

```text
3회차 디자인 계약 파일을 정리하려고 해.

먼저 읽을 것:
- 프로젝트 루트 DESIGN.md
- 프로젝트 루트 AGENTS.md가 있으면 전체 내용
- 현재 프로젝트 파일 구조
- 아래 선택 브리프와 최종 Plan

선택 브리프:
[08단계와 선택한 챌린지의 최종 브리프 전체 붙여넣기]

02단계 최종 Plan:
[최신 Plan 전체 붙여넣기]

요청:
1. DESIGN.md에서 Decision status를 selected로 바꾸고, 최종 Selected element와 아래 필드를 확정한 문안을 보여줘.
   - Color, Typography, Spacing, Radius, Border, Shadow, Component
   - Bring, Avoid, Allowed files, Verification
2. AGENTS.md를 감사해서 아래를 구분해줘.
   - 계속 유지할 현재 레포 규칙
   - 이미 끝난 회차 목표, 낡은 경로, 일회성 작업 지시
   - 중복되거나 충돌하는 규칙
3. AGENTS.md에는 반복해서 지킬 규칙만 남기는 최소 변경 문안을 보여줘.
   - 구현 전 선택한 백로그 파일과 DESIGN.md를 읽는다.
   - Allowed files 밖의 변경은 먼저 이유를 설명하고 승인을 받는다.
   - 새 라이브러리, 외부 font, 무거운 animation을 임의로 추가하지 않는다.
   - desktop, 390x844, npm run build로 검증한다.
   - 실제 백로그 본문은 docs/design-backlog에 둔다.
4. docs/design-backlog/README.md에는 D-001 인덱스와 Status 설명만 넣어줘.
5. docs/design-backlog/D-001.md에는 Where (URL + Viewport), Target, Evidence, Problem, Direction, Constraint와 선택 브리프의 token brief, Allowed files, Do not change를 빠짐없이 전달해줘.
6. D-001의 Approved plan에는 승인 문장·02단계 Plan 위치를 적고, Steps는 최종 Plan과 같은 범위와 순서로 적어줘.
7. 만들거나 갱신할 네 파일의 완성 문안과 예상 diff를 먼저 보여줘.

중요:
- 아직 어떤 파일도 수정하지 마.
- 기존 AGENTS.md를 통째로 교체하지 마.
- 여전히 유효한 빌드 명령, 코드 스타일, 금지 규칙은 보존해.
- 낡은 목표를 지울 필요가 있으면 대상 문장과 이유를 먼저 보여줘.
- AGENTS.md에 D-001의 URL, Target, Problem, token brief를 복사하지 마.
- 구현 파일은 수정하지 마.
```

미리 보기에서 아래를 확인합니다.

- `DESIGN.md`의 최종 토큰과 D-001의 token brief가 같습니다.
- `Allowed files`가 08단계에서 확정한 실제 경로와 같습니다.
- D-001의 Do not change, Approved plan, Steps가 02단계 최종 Plan과 충돌하지 않습니다.
- `AGENTS.md`에는 반복 규칙만 있고 일회성 D-001 본문이 없습니다.
- 지우거나 바꾸는 기존 AGENTS.md 문장이 있다면 이유가 납득됩니다.

## 2차 프롬프트: 승인 후 실제 생성

미리 본 문안이 맞으면 반드시 아래 프롬프트를 이어서 보냅니다.

```text
좋아. 방금 보여준 문안 그대로 아래 네 파일을 실제로 만들거나 갱신해줘.

- DESIGN.md
- AGENTS.md
- docs/design-backlog/README.md
- docs/design-backlog/D-001.md

실행 조건:
- 기존 파일이 있으면 방금 승인한 부분만 수정해.
- AGENTS.md의 여전히 유효한 기존 규칙은 보존해.
- AGENTS.md의 낡은 목표와 중복 규칙은 방금 미리 보기에서 승인한 범위만 정리해.
- DESIGN.md와 D-001의 token brief, Bring, Avoid, Allowed files, Verification을 일치시켜.
- README.md와 D-001의 Status는 planned로 시작해.
- 아직 Astro 구현 파일은 수정하지 마.
- 완료 후 실제 변경한 파일 목록과 각 파일의 역할을 알려줘.
- 마지막에 git diff -- DESIGN.md AGENTS.md docs/design-backlog 결과를 요약해줘.
```

## 체크박스

- [ ] 네 파일의 문안을 먼저 미리 봤다.
- [ ] AGENTS.md에서 낡은 목표와 유지할 규칙을 구분했다.
- [ ] 삭제·교체할 AGENTS.md 문장을 승인했다.
- [ ] 승인 후 실제 파일 생성 프롬프트를 보냈다.
- [ ] `DESIGN.md`의 Decision status가 `selected`다.
- [ ] `docs/design-backlog/README.md`와 D-001의 Status가 `planned`다.
- [ ] D-001에 전체 token brief와 Allowed files가 들어갔다.
- [ ] 아직 구현 파일은 수정하지 않았다.

## Ready Gate

다음 단계로 넘어가기 전에 파일 탐색기 또는 터미널에서 실제 존재를 확인합니다.

- [ ] 프로젝트 루트에 `DESIGN.md`가 있다.
- [ ] 프로젝트 루트에 `AGENTS.md`가 있다.
- [ ] `docs/design-backlog/README.md`가 있다.
- [ ] `docs/design-backlog/D-001.md`가 있다.
- [ ] D-001의 Where (URL + Viewport), Target, Evidence, Problem, Direction, Constraint가 비어 있지 않다.
- [ ] D-001의 Token brief, Allowed files, Do not change, Approved plan, Steps, Verification이 비어 있지 않다.
- [ ] `git diff -- DESIGN.md AGENTS.md docs/design-backlog`를 확인했다.

문안만 채팅에 있고 파일이 없다면 Ready Gate를 통과한 것이 아닙니다.

## 힌트

<details>
<summary>AGENTS.md가 이미 길다면</summary>

새로운 "3회차 규칙"을 통째로 덧붙이지 마세요.
기존 규칙 중 같은 의미가 있는 문장은 유지하거나 한 문장으로 합치고, 이번 작업에서만 쓰는 URL·Target·토큰은 D-001에 둡니다.

</details>

## 퀴즈

### 질문

`AGENTS.md`에 가장 적합한 내용은 무엇인가요?

- A. D-001의 오늘자 before 스크린샷 경로
- B. `/projects` 첫 카드의 상세 색상 값
- C. 작업 전 DESIGN.md와 선택한 백로그를 읽는 반복 규칙
- D. 02단계 채팅의 전체 Plan

<details>
<summary>정답 보기</summary>

**정답: C**

일회성 범위와 결과는 D-001에 두고, `AGENTS.md`에는 다음 작업에도 반복해서 적용할 규칙만 둡니다.

</details>

## 다음 단계에서 참고할 내용

```text
DESIGN.md: selected / 확인함
AGENTS.md: 반복 규칙만 있음 / 확인함
docs/design-backlog/README.md: D-001 planned / 확인함
docs/design-backlog/D-001.md: token + Allowed files + Plan 있음 / 확인함
구현 파일 변경: 없음
```

## 관련 템플릿

- [레퍼런스 디자인 토큰 브리프](../templates/reference-design-token-brief.md)
- [AGENTS.md 3회차 업데이트 템플릿](../templates/AGENTS-session-03-update.md)
- [디자인 백로그 폴더 양식](../templates/design-change-backlog.md)

## 다음 단계

[10. D-001 계약 확인하고 실행하기 →](./10-execute-plan.md)
