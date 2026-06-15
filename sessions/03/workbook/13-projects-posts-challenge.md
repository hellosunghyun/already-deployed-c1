# 13. Projects / Posts 챌린지

## 목표

반복 목록의 시각 위계를 개선합니다.

## Projects에서 볼 것

```text
카드 제목 / 설명 / 태그 위계
카드 간격
자세히 보기 링크
모바일 카드 폭과 padding
```

## Posts에서 볼 것

```text
제목과 날짜의 대비
요약 줄 길이
태그 밀도
목록 간격
```

## 요청 예시

```text
@브라우저 또는 @Browser로 /projects를 열어줘.
Target은 첫 번째 프로젝트 카드야.

Problem:
- 제목, 설명, 태그의 시각 위계가 약함
- 카드 사이 간격이 좁아 목록이 답답해 보임

Reference:
- [레퍼런스 URL]
- Selected element: Project card framing
- Bring: 카드 gap, muted text 위계, 얇은 border
- Avoid: 전체 색상 복제, 외부 font, animation

Constraint:
- src/data/projects.json 구조는 바꾸지 마
- 새 라이브러리 추가하지 마

먼저 최소 수정 계획만 말해줘.
```

## 완료 기준

- [ ] 목록을 훑을 때 제목이 먼저 보인다.
- [ ] 설명과 태그가 덜 경쟁한다.
- [ ] 데이터 JSON 구조는 유지됐다.

## 다음 단계

[14. 모바일 확인 →](./14-mobile-check.md)
