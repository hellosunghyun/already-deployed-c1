# 3회차 템플릿 인덱스

각 템플릿의 `[입력]` 자리를 실제 값으로 바꾼 뒤 그대로 복사해 사용합니다.
파일을 바꾸는 작업은 **변경 미리보기 → 사용자 승인 → 실제 적용** 순서로 진행합니다.

## 워크북 단계별 매핑

| 진행 단계 | 사용할 템플릿 | 결과물 |
|---|---|---|
| 01 출발 상태 확인 | [막혔을 때 질문](./stuck-question-template.md) | A / B / C 상태와 다음 한 단계 |
| 03 Browser 준비 | [Browser 주석 프롬프트](./codex-browser-comment-prompts.md) | 실제 Local URL, Annotation 또는 스크린샷 대체 경로 |
| 04~05 baseline·피드백 | [스크린샷 피드백](./screenshot-feedback-template.md) | 6좌표와 수정 전 Evidence |
| 06~07 레퍼런스·토큰 | [레퍼런스 디자인 토큰 브리프](./reference-design-token-brief.md) | 선택한 요소와 7개 토큰 |
| 08 적용 요소 확정 | [원하는 요소만 선택하기](./selective-reference-element-brief.md) | Bring / Avoid / Allowed files |
| 11 / 12 / 13 중 하나 선택 | [원하는 요소만 선택하기](./selective-reference-element-brief.md) | Home / Navigation / Projects·Posts 중 한 Target |
| 02 증거 기반 최종 Plan | [최종 Plan 프롬프트](./plan-mode-prompts.md) | D-001 제목, 완료 조건, 최종 Plan |
| 09 규칙·백로그 생성 | [AGENTS.md 업데이트](./AGENTS-session-03-update.md), [디자인 백로그 양식](./design-change-backlog.md) | AGENTS.md 규칙, README 인덱스, D-001.md |
| 10 D-001 실행 | [레퍼런스 토큰 적용](./reference-token-application-prompt.md) | 선택한 변경 하나와 검증 결과 |
| 14 모바일 수정·재검증 | [모바일 체크리스트](./mobile-checklist.md) | desktop·390x844 pass/fail |
| 15~16 배포·기록 | [Before / After 기록지](./before-after-report.md), [디자인 백로그 양식](./design-change-backlog.md) | build·commit·push·Pages 증거, done 또는 blocked |

## Canonical source

같은 항목이 여러 파일에 나오면 아래 파일의 이름과 순서를 기준으로 맞춥니다.

| 기준 | Canonical source | 고정 스키마 |
|---|---|---|
| 화면 피드백 6좌표 | [screenshot-feedback-template.md](./screenshot-feedback-template.md) | Where (URL + Viewport) / Target / Evidence / Problem / Direction / Constraint |
| 디자인 토큰 | [reference-design-token-brief.md](./reference-design-token-brief.md) | Color / Typography / Spacing / Radius / Border / Shadow / Component |
| 레퍼런스 선택 | [selective-reference-element-brief.md](./selective-reference-element-brief.md) | Reference URL / Selected element / Bring / Avoid / Allowed files |
| D-001와 상태 | [design-change-backlog.md](./design-change-backlog.md) | `planned → doing → done` 또는 `planned → doing → blocked` |
| Browser 절차 | [codex-browser-comment-prompts.md](./codex-browser-comment-prompts.md) | 데스크톱 앱 / Browser 설치 / 실제 Local URL / `@Browser` / Annotation / `나 대신 승인` |
| 모바일 검증 | [mobile-checklist.md](./mobile-checklist.md) | 현재 desktop과 390x844 필수, 768x1024와 1440x900 권장 |
| 최종 증거 | [before-after-report.md](./before-after-report.md) | 실제 파일 / before·after / pass·fail / 실패 로그 / commit / push / Actions / Pages |

## 기록 원칙

- 확인하지 않은 검증은 `pass`로 추정하지 않고 `not run`으로 적습니다.
- `docs/design-backlog/README.md` 인덱스와 `D-001.md` 본문의 상태를 함께 갱신합니다.
- 화면 문제가 남거나 build·배포가 실패하면 `done` 대신 `blocked`로 남깁니다.
- secret, token, password, API key는 템플릿이나 채팅에 붙여넣지 않습니다.
