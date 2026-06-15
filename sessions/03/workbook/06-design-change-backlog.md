# 06. 디자인 수정 backlog 만들기

## 목표

수정하고 싶은 디자인 문제를 우선순위가 있는 backlog로 정리합니다.

## 왜 하는가

디자인 문제는 끝이 없습니다.
우선순위를 정하지 않으면 AI에게 계속 새 수정을 요청하다가 build, commit, 기록을 놓치기 쉽습니다.

## 우선순위 기준

```text
P0: 사용을 방해함
예: 모바일에서 가로 스크롤, 링크 클릭 불가, 텍스트 겹침

P1: 읽기 어렵거나 이동이 헷갈림
예: 제목 위계 약함, Navigation 약함, 카드 밀도 과함

P2: 더 좋아질 수 있는 polish
예: shadow, border, 색상 미세 조정, 섹션 리듬
```

## backlog 양식

```text
ID:
Priority:
URL:
Viewport:
Target:
Problem:
Direction:
Constraint:
Reference source:
Selected reference element:
Reference token:
Rejected token:
Verification:
Status:
```

## Codex에게 보낼 프롬프트

```text
지금까지 나온 디자인 문제를 3회차 실습용 backlog로 정리해줘.

입력 자료:
- baseline 관찰 결과
- screenshot feedback
- Browser comments
- 레퍼런스 분석 결과
- 레퍼런스 디자인 토큰 브리프

요청:
1. 문제를 P0 / P1 / P2로 나눠줘.
2. 한 번에 고칠 수 있는 작은 작업 단위로 쪼개줘.
3. 각 항목마다 URL, viewport, target, problem, direction, constraint, verification을 적어줘.
4. 레퍼런스 토큰을 쓰는 항목은 reference source, selected element, token, rejected token을 같이 적어줘.
5. 전체를 따라 하는 항목은 제거하고, 원하는 요소만 가져오는 항목으로 바꿔줘.
6. 오늘 90분 안에 할 수 있는 핵심 작업 1~2개만 추천해줘.
7. 아직 파일 수정은 하지 마.

제약:
- 레퍼런스 전체 복제 금지
- 레퍼런스에서 원하는 요소 1개만 선택
- 전체 리디자인 금지
- 새 라이브러리 추가 금지
- 데이터 구조 변경 금지
- build 검증 가능한 단위로 나누기
```

## 체크박스

- [ ] 디자인 문제를 3개 이상 적었다.
- [ ] P0 / P1 / P2로 나눴다.
- [ ] 오늘 수정할 항목을 1~2개로 좁혔다.
- [ ] 각 항목에 verification이 있다.
- [ ] 수정 전 backlog가 저장되어 있다.

## Ready Gate

다음 단계로 넘어가기 전에 아래가 되어 있어야 합니다.

- 오늘 수정할 항목이 1개 이상 정해졌습니다.
- 작업 단위가 너무 크지 않습니다.
- 수정 후 어떻게 확인할지 적혀 있습니다.

## 다음 단계

[07. Home hero 디자인 챌린지 →](./07-home-hero-design.md)
