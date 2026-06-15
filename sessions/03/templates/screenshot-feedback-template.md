# 3회차 스크린샷 피드백 템플릿

스크린샷을 AI에게 보낼 때 아래를 같이 채웁니다.
이미지는 증거이고, 이 텍스트는 요구사항입니다.

## 기본 정보

```text
URL:
Viewport:
스크린샷 파일명:
캡처 시점:
```

## 고칠 영역

```text
Target:
예: Home hero 제목과 소개 문장
예: Projects 첫 번째 카드
예: 모바일 Navigation
```

## 문제 설명

```text
Problem:
예: 제목과 설명의 위계가 약해서 어디를 먼저 봐야 할지 헷갈림
예: 390px 모바일에서 제목이 4줄로 깨짐
예: 카드 간격이 좁아 서로 붙어 보임
```

## 원하는 방향

```text
Direction:
예: 제목은 조금 더 굵게, 설명은 조금 더 작고 옅게
예: 모바일에서 제목 크기를 줄이고 line-height를 조정
예: 카드 내부 padding은 유지하고 카드 사이 gap만 늘리기
```

## 제약

```text
Constraint:
- 새 라이브러리 추가 금지
- 외부 폰트 추가 금지
- 기존 색상 톤 유지
- 데이터 JSON 구조 유지
- 관련 없는 파일 수정 금지
```

## 검증 기준

```text
Verification:
- Codex Browser에서 같은 URL 확인
- 390px 모바일 확인
- npm run build 실행
```

## Codex에게 보낼 문장

```text
첨부한 스크린샷과 아래 6좌표를 기준으로 봐줘.

URL:
Viewport:
Target:
Problem:
Direction:
Constraint:

아직 파일을 수정하지 말고,
먼저 원인 후보와 최소 수정 계획을 제안해줘.
내가 승인하면 수정해줘.
```
