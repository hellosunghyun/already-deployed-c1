# 05. 스크린샷과 브라우저 주석 피드백

## 목표

Codex가 고칠 위치를 추측하지 않게 합니다.

## 6좌표

```text
URL:
Viewport:
Target:
Problem:
Direction:
Constraint:
```

## 브라우저 주석 문장 예시

```text
이 카드 영역의 제목과 설명 위계를 더 분명하게 해줘.
색상 톤은 유지하고 font-size, font-weight, gap만 조정해줘.
```

## 스크린샷만 있을 때 프롬프트

```text
첨부한 스크린샷을 기준으로 봐줘.

URL: [예: /projects]
Viewport: [예: 390x844]
Target: [예: 첫 번째 프로젝트 카드]
Problem: [예: 제목, 설명, 태그가 모두 비슷하게 보여 읽는 순서가 약함]
Direction: [예: 제목은 더 굵게, 설명은 조금 작게, 태그는 덜 튀게]
Constraint: 새 라이브러리 추가 금지, 데이터 구조 변경 금지, 전체 색상 톤 유지

아직 수정하지 말고 원인 후보와 최소 수정 계획만 말해줘.
```

## Ready Gate

- [ ] 6좌표가 채워졌다.
- [ ] 고칠 영역이 하나로 좁혀졌다.
- [ ] Codex에게 아직 실행하지 말라고 했다.

## 다음 단계

[06. 레퍼런스 사이트 고르기 →](./06-reference-pick.md)
