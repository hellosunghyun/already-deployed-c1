# 모바일 체크리스트

## 화면 입력

```text
Where (URL + Viewport): [예: /projects, 390x844]
Target: [입력]
Evidence: [스크린샷 경로, 첨부명 또는 Browser 주석]
Problem: [입력]
Direction: [입력]
Constraint: [입력]
```

필수 확인은 현재 desktop과 390x844입니다. 시간이 있으면 768x1024와 1440x900도 확인합니다.

## 체크리스트

- [ ] 가로 스크롤이 없다.
- [ ] 제목이 과하게 줄바꿈되지 않는다.
- [ ] Navigation 링크의 터치 영역이 충분하다.
- [ ] 카드 padding과 gap이 답답하지 않다.
- [ ] 본문 줄 길이가 너무 길거나 짧지 않다.
- [ ] CTA / 자세히 보기 링크가 보이고 작동한다.
- [ ] 키보드로 주요 링크에 접근할 수 있다.
- [ ] focus 표시가 사라지지 않았다.
- [ ] 텍스트와 배경의 대비가 지나치게 약해지지 않았다.

## 결과

```text
현재 desktop: [pass / fail / not run]
390x844: [pass / fail / not run]
768x1024: [pass / fail / not run]
1440x900: [pass / fail / not run]
실패한 항목과 Evidence: [없음 / 입력]
수정 필요 여부: [yes / no]
```

## 1. 문제 발견 시 수정 미리보기

```text
아래 모바일 문제의 최소 수정 계획만 보여줘.

Where (URL + Viewport): [입력]
Target: [입력]
Evidence: [스크린샷 경로, 첨부명 또는 Browser 주석]
Problem: [입력]
Direction: [입력]
Constraint: [입력]
Allowed files: [파일 경로 목록]

아직 파일을 수정하지 마.
원인 후보, 예상 변경 파일, 가장 작은 수정, 같은 viewport 재검증 방법만 보여줘.
```

## 2. 승인 후 수정·재검증

```text
아래 승인된 모바일 문제만 수정해줘.

Where (URL + Viewport): [입력]
Target: [입력]
Evidence: [스크린샷 경로, 첨부명 또는 Browser 주석]
Problem: [입력]
Direction: [입력]
Constraint: [입력]
Allowed files: [파일 경로 목록]

수정 후 같은 viewport와 현재 desktop을 다시 확인해줘.
두 화면의 pass/fail, 실제 변경 파일, 남은 문제를 알려줘.
문제가 남으면 배포 가능으로 표시하지 마.
```
