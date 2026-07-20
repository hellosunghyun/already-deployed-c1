# 스크린샷 피드백 템플릿

## 6좌표

```text
Where (URL + Viewport): [예: /projects, 390x844]
Target: [예: 첫 번째 프로젝트 카드]
Evidence: [스크린샷 경로 또는 첨부명]
Problem: [관찰 가능한 문제]
Direction: [원하는 결과]
Constraint: [유지할 구조와 금지할 변경]
```

## 1. 스크린샷 기준 변경 미리보기

```text
첨부한 스크린샷과 아래 6좌표를 기준으로 검토해줘.

Where (URL + Viewport): [입력]
Target: [입력]
Evidence: [스크린샷 경로 또는 첨부명]
Problem: [입력]
Direction: [입력]
Constraint: [입력]

아직 파일을 수정하지 마.
Evidence가 Target과 Problem을 뒷받침하는지 먼저 확인하고, 원인 후보, 예상 변경 파일, 최소 수정 계획, 같은 화면에서 재검증할 항목만 보여줘.
```

## 2. 승인 후 적용

이 프롬프트는 최종 Plan과 D-001을 만든 뒤 10단계에서만 사용합니다.

```text
첨부한 스크린샷과 아래 승인된 6좌표 범위만 수정해줘.

Where (URL + Viewport): [입력]
Target: [입력]
Evidence: [스크린샷 경로 또는 첨부명]
Problem: [입력]
Direction: [입력]
Constraint: [입력]
Allowed files: [파일 경로 목록]
D-001: docs/design-backlog/D-001.md

먼저 D-001 본문과 docs/design-backlog/README.md 인덱스의 상태를 planned에서 doing으로 함께 바꿔줘.
수정 후 같은 URL의 현재 desktop과 390x844에서 다시 확인해줘.
실제 변경 파일, before/after, 화면 확인 pass/fail을 알려줘.
Allowed files와 D-001 결과 기록 밖은 수정하지 마.
local 검증이 통과하면 doing을 유지하고, 막히면 두 상태를 blocked로 맞춰 이유와 다음 행동을 기록해.
최종 done은 실제 Pages 확인 뒤 16단계에서만 기록해.
```

## 완성 예시

```text
Where (URL + Viewport): /projects, 390x844
Target: 첫 번째 프로젝트 카드
Evidence: before-projects-390.png
Problem: 제목, 설명, 태그가 모두 비슷하게 보여 읽는 순서가 약함
Direction: 제목 굵기를 높이고 설명 줄 간격을 조정하며 태그의 대비를 낮춘다
Constraint: 새 라이브러리를 추가하지 않고 projects.json 구조와 전체 색상 톤을 유지한다
```
