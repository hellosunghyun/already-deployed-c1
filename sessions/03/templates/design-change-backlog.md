# 디자인 수정 Backlog 템플릿

## 우선순위 기준

```text
P0: 사용을 방해함
P1: 읽기 어렵거나 이동이 헷갈림
P2: 더 좋아질 수 있는 polish
```

## Backlog

| ID | Priority | URL | Viewport | Target | Problem | Reference token | Direction | Constraint | Verification | Status |
|---|---|---|---|---|---|---|---|---|---|---|
| D-001 | P1 | / | 390x844 | Home hero 제목 | 제목이 4줄로 깨짐 | typography.hero | 모바일 제목 크기와 line-height 조정 | 색상 유지, 새 라이브러리 금지 | 390px 확인, build | Todo |
| D-002 | P1 | /projects | desktop/mobile | 카드 목록 | 제목/설명/태그 위계 약함 | spacing.card-gap, color.muted | 제목 강화, 보조 정보 약화 | projects.json 유지 | /projects 확인, build | Todo |
| D-003 | P2 | /posts | desktop | 글 목록 | 날짜와 태그가 제목보다 튐 | typography.meta, color.muted | 날짜/태그 크기와 색 낮추기 | posts.json 유지 | /posts 확인 | Todo |

## 오늘 선택할 항목

```text
오늘 반드시 할 것:
오늘 시간이 남으면 할 것:
오늘 하지 않을 것:
```

## Codex에게 보낼 문장

```text
아래 design backlog에서 오늘 할 항목을 고르고 싶어.

[backlog 붙여넣기]

기준:
- 90분 안에 끝낼 수 있어야 함
- browser와 mobile 확인 가능해야 함
- build까지 검증 가능해야 함
- 새 라이브러리 없이 해결 가능해야 함
- 레퍼런스 토큰을 쓰는 항목은 어떤 token을 쓰는지 명확해야 함

오늘 할 항목 1~2개만 추천하고,
아직 파일 수정은 하지 마.
```
