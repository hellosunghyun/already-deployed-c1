# AGENTS.md 3회차 업데이트 템플릿

기존 `AGENTS.md`에는 **규칙과 참조 경로만** 추가합니다.
실제 디자인 백로그 항목은 `docs/design-backlog/` 폴더에 둡니다.

## 추가할 규칙 원문

```md
## 3회차 디자인 작업 규칙

- 새 프로젝트를 만들지 않고 기존 Astro 개인 홈페이지에서 이어서 작업한다.
- baseline, 레퍼런스, 선택 영역을 확인한 뒤 Plan mode 또는 계획 응답으로 최종 계획을 받는다.
- 화면 요구사항은 `Where (URL + Viewport) / Target / Evidence / Problem / Direction / Constraint` 6좌표로 기록한다.
- Codex 데스크톱에서는 `@Browser`와 Annotation을 사용하고, 사용할 수 없으면 일반 브라우저 스크린샷과 6좌표를 사용한다.
- 레퍼런스는 전체 복제하지 않고 선택한 요소 하나만 토큰으로 적용한다.
- 새 라이브러리, 외부 font, 무거운 animation은 사용자 승인 없이 추가하지 않는다.
- 수정 후 현재 desktop과 390x844 모바일, `npm run build`로 확인한다.
- 디자인 백로그 본문은 `AGENTS.md`에 적지 않는다.
- 디자인 백로그는 `docs/design-backlog/` 폴더의 Markdown 파일로 관리한다.
- 작업 전 선택한 백로그 파일을 읽고, 그 항목 하나만 실행한다.
- 작업 상태는 `planned → doing → done` 또는 `planned → doing → blocked`로 갱신한다.
- 작업 후 실제 변경 파일, before/after, 검증 pass/fail, 실패 로그, commit과 Pages 결과를 해당 백로그 파일에 기록한다.
```

## 1. 변경 문안 미리보기

```text
현재 레포의 AGENTS.md를 읽고 아래 목적의 규칙을 어디에 추가할지 문안만 보여줘.

목적:
- 기존 Astro 홈페이지에서 이어서 작업
- 화면 증거를 모은 뒤 최종 Plan 작성
- Codex 데스크톱에서는 @Browser와 Annotation 사용
- Browser가 없으면 일반 브라우저 스크린샷과 Where (URL + Viewport), Target, Evidence, Problem, Direction, Constraint 사용
- 레퍼런스 요소 하나만 적용
- docs/design-backlog/[D-001.md] 한 항목만 실행
- 현재 desktop, 390x844, npm run build로 검증
- 결과는 실제 변경 파일, before/after, pass/fail, 실패 로그, commit, Pages URL까지 백로그에 기록

조건:
- 기존 규칙을 지우거나 의미를 약하게 만들지 마.
- AGENTS.md에는 실제 백로그 내용이나 완료 내역을 넣지 마.
- 새 라이브러리, 외부 font, 무거운 animation은 사용자 승인 없이 추가하지 않는다고 명시해.
- 중복되는 문장은 합쳐줘.
- 아직 파일을 수정하지 마.
- 추가 위치, 최종 문안, 중복 정리 이유만 보여줘.
```

## 2. 승인 후 적용

미리보기 결과를 확인한 뒤, 승인한 문안 전체를 아래 입력값에 붙여넣습니다.

```text
현재 레포의 AGENTS.md에 아래 승인된 문안만 적용해줘.

승인된 문안:
[승인한 규칙 문안 전체를 붙여넣기]

조건:
- 기존 규칙을 지우거나 의미를 약하게 만들지 마.
- 중복 문장은 의미를 유지한 채 합쳐.
- 실제 백로그 내용이나 완료 내역은 AGENTS.md에 넣지 마.
- AGENTS.md 외의 파일은 수정하지 마.

적용 후 실제 변경 위치와 합친 문장을 요약해줘.
```
