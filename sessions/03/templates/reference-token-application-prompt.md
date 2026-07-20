# 레퍼런스 토큰 적용 프롬프트

## 1. 적용 미리보기

```text
docs/design-backlog/D-001.md를 읽고 아래 입력값과 일치하는지 확인한 뒤 최소 수정 계획만 보여줘.

Where (URL + Viewport): [입력]
Target: [입력]
Evidence: [스크린샷 경로, 첨부명 또는 Browser 주석]
Problem: [입력]
Direction: [입력]
Constraint: [입력]

Reference URL: [입력]
Selected element: [입력]
Bring: [입력]
Avoid: [입력]
Color: [입력]
Typography: [입력]
Spacing: [입력]
Radius: [입력]
Border: [입력]
Shadow: [입력]
Component: [입력]
Allowed files: [파일 경로 목록]

조건:
- 레퍼런스 전체 복제 금지
- 선택한 요소 하나만 적용
- 새 라이브러리, 외부 font, 무거운 animation 추가 금지
- Allowed files 밖의 파일 수정 금지
- 기존 데이터 JSON 구조와 배포 설정 유지
- AGENTS.md 수정 금지
- 아직 파일을 수정하거나 명령을 실행하지 마.
- 예상 변경 파일, 최소 변경, 하지 않을 일, 검증 순서만 보여줘.
```

## 2. 승인 후 D-001 실행

```text
docs/design-backlog/D-001.md를 읽고 아래 승인된 범위 하나만 실행해줘.

Where (URL + Viewport): [입력]
Target: [입력]
Evidence: [스크린샷 경로, 첨부명 또는 Browser 주석]
Problem: [입력]
Direction: [입력]
Constraint: [입력]

Reference URL: [입력]
Selected element: [입력]
Bring: [입력]
Avoid: [입력]
Color: [입력]
Typography: [입력]
Spacing: [입력]
Radius: [입력]
Border: [입력]
Shadow: [입력]
Component: [입력]
Allowed files: [파일 경로 목록]

조건:
- 먼저 docs/design-backlog/D-001.md 본문과 docs/design-backlog/README.md 인덱스의 상태를 doing으로 갱신해.
- 선택한 요소 하나만 적용해.
- 새 라이브러리, 외부 font, 무거운 animation은 추가하지 마.
- Allowed files와 두 백로그 기록 파일 밖은 수정하지 마. AGENTS.md는 수정하지 마.
- 수정 후 현재 desktop과 390x844를 확인하고 npm run build를 실행해.
- 실제 변경 파일, before/after, 각 검증의 pass/fail, 실패 로그를 알려줘.
- commit과 push는 아직 하지 마.
- local 검증이 모두 통과하면 D-001 본문과 README 인덱스를 doing으로 유지하고 14단계로 이동한다고 기록해.
- 구현이나 local 검증이 막히면 두 파일을 blocked로 함께 갱신할 문안을 제안해.
- 최종 done은 commit, Actions, 실제 Pages 확인 뒤 16단계에서만 기록해.
```
