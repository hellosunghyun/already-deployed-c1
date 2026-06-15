# 12. Navigation / 레이아웃 챌린지

## 목표

페이지 이동과 레이아웃 밀도를 개선합니다.

## 고를 수 있는 문제

```text
모바일에서 링크가 너무 붙음
Header 높이가 과함
현재 페이지가 구분되지 않음
본문 max-width가 너무 넓거나 좁음
섹션 간격이 페이지마다 다름
```

## 요청 예시

```text
@브라우저 또는 @Browser로 /about과 /projects를 확인해줘.
Target은 공통 Navigation과 page width야.

Problem:
- 모바일에서 Navigation 링크 간격이 좁아 터치하기 어려움
- 페이지별 본문 시작 위치가 다르게 보여 사이트가 덜 정돈됨

Direction:
- 링크 gap과 padding을 모바일에서 조정
- 공통 page width와 section spacing을 정리

Constraint:
- 라우팅 구조와 href는 바꾸지 마
- 새 라이브러리 추가하지 마
- Header/Footer 구조를 복잡하게 만들지 마

먼저 수정 계획만 말해줘.
```

## 완료 기준

- [ ] Navigation 링크가 모바일에서 읽고 누르기 쉽다.
- [ ] 공통 레이아웃 밀도가 안정적이다.
- [ ] href가 깨지지 않았다.

## 다음 단계

[13. Projects / Posts 챌린지 →](./13-projects-posts-challenge.md)
