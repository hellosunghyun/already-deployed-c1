# Codex Browser 주석 프롬프트

## 사용 전 준비

```text
1. ChatGPT 데스크톱 앱에서 Codex를 선택한다.
2. Plugins Directory에서 Browser를 설치한다.
3. 개발 서버를 실행한다.
4. 터미널에 표시된 실제 Local URL을 복사한다.
5. Browser 승인 기본값은 `나 대신 승인`으로 선택한다.
```

Browser나 해당 설정이 보이지 않으면 아래의 스크린샷 대체 프롬프트를 사용합니다.

`나 대신 승인`을 선택해도 비밀번호·token·secret 입력, 결제, 삭제, commit·push는 별도 사용자 승인 없이 Browser에 맡기지 않습니다.

## 실제 Local URL 열기

```text
@Browser [터미널에 표시된 실제 Local URL]을 열어줘.

아직 수정하지 마.
현재 URL, viewport, 보이는 페이지 제목, 렌더링 오류 유무만 알려줘.
```

## Annotation 남기기

```text
1. Annotation mode를 켠다.
2. 고칠 요소를 클릭하거나 영역을 드래그한다.
3. Problem과 Direction을 적고 저장한다.
4. 아래 미리보기 프롬프트를 보낸다.
```

## 1. 주석 기준 변경 미리보기

```text
@Browser에서 내가 저장한 주석을 확인해줘.

Where (URL + Viewport): [입력]
Target: [입력]
Evidence: [저장한 Browser 주석]
Problem: [입력]
Direction: [입력]
Constraint: [입력]

아직 파일을 수정하지 마.
주석과 6좌표가 같은 영역을 가리키는지 확인하고, 원인 후보와 최소 수정 계획, 예상 변경 파일, 검증 방법만 보여줘.
```

## 2. 승인 후 실행·확인

이 프롬프트는 최종 Plan과 D-001을 만든 뒤 10단계에서만 사용합니다.

```text
아래 승인된 범위만 수정해줘.

Where (URL + Viewport): [입력]
Target: [입력]
Evidence: [저장한 Browser 주석]
Problem: [입력]
Direction: [입력]
Constraint: [입력]
Allowed files: [파일 경로 목록]
D-001: docs/design-backlog/D-001.md

먼저 D-001 본문과 docs/design-backlog/README.md 인덱스의 상태를 planned에서 doing으로 함께 바꿔줘.
수정 후 @Browser로 같은 URL의 현재 desktop과 390x844를 다시 확인해줘.
실제 변경 파일, before/after, Browser 확인 pass/fail, 390x844 pass/fail을 알려줘.
Allowed files와 D-001 결과 기록 밖의 파일은 수정하지 마.
local 검증이 통과하면 doing을 유지하고, 막히면 두 상태를 blocked로 맞춰 이유와 다음 행동을 기록해.
최종 done은 실제 Pages 확인 뒤 16단계에서만 기록해.
```

## Browser가 없을 때 스크린샷 대체 프롬프트

```text
첨부한 스크린샷을 기준으로 아래 화면만 검토해줘.

Where (URL + Viewport): [입력]
Target: [입력]
Evidence: [스크린샷 파일 경로 또는 첨부명]
Problem: [입력]
Direction: [입력]
Constraint: [입력]

아직 파일을 수정하지 마.
원인 후보와 최소 수정 계획, 예상 변경 파일, 같은 viewport에서 재검증할 항목만 보여줘.
```
