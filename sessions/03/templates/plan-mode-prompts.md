# 증거 기반 최종 Plan 프롬프트

이 프롬프트는 baseline, 레퍼런스, 토큰 브리프, 챌린지 선택을 끝낸 뒤 사용합니다.

## 최종 Plan만 받기

```text
/plan

기존 2회차 Astro 홈페이지 레포에서 아래 디자인 문제 하나의 최종 실행 계획을 세워줘.

선택한 챌린지: [Home / Navigation / Projects·Posts 중 하나]
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
Before screenshot: [파일 경로 또는 첨부명]

계획에 포함할 것:
1. D-001 제목과 완료 조건
2. 실제로 확인한 현재 구조
3. 수정 파일과 각 파일의 최소 변경
4. 하지 않을 일
5. 현재 desktop과 390x844 검증 순서
6. npm run build, git status, commit·push·Pages 확인 순서
7. 실패하면 blocked로 남길 로그

아직 파일을 수정하거나 명령을 실행하지 마.
먼저 최종 Plan과 docs/design-backlog/D-001.md 초안에 들어갈 값만 보여줘.
```

Plan을 승인한 뒤에는 [디자인 백로그 폴더 양식](./design-change-backlog.md)의 승인 후 생성 프롬프트로 이동합니다. 이 단계에서 바로 구현하지 않습니다.

## 실행 중 멈추기

```text
멈춰.
현재 작업 상태, 실제 수정한 파일, 실행한 검증과 실패 로그만 요약해줘.
추가 수정, commit, push는 하지 마.
```
