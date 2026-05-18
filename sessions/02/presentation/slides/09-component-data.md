# Slide 09. Component와 데이터

Projects 페이지에는 비슷한 카드가 여러 개 나옵니다.

```text
프로젝트 이름
한 줄 설명
내 역할
사용 도구
결과 또는 배운 점
```

이런 반복 화면은 Component로 만들기 좋습니다.

---

## 데이터와 화면을 나누기

```text
프로젝트 데이터 = 무엇을 보여줄지
ProjectCard Component = 어떻게 보여줄지
```

이렇게 나누면 프로젝트가 3개에서 10개로 늘어나도 추가하기 쉽습니다.

---

## SwiftUI와 비교하면

SwiftUI에서도 반복되는 카드는 보통 작은 `View`로 나눕니다.

```text
ProjectCard Component ≈ ProjectCardView
프로젝트 배열 ≈ projects 배열
반복 표시 ≈ ForEach
```

중요한 감각은 "내용"과 "보여주는 모양"을 나누는 것입니다.

---

[← 이전](./08-layout-navigation.md) · [다음 →](./10-posts-before-notion.md)

<details><summary>말할 포인트</summary>

배열, 객체, 컴포넌트라는 단어가 나올 수 있습니다.
문법을 다 외우는 것보다 "반복되는 카드를 하나의 틀로 만든다"는 개념을 먼저 잡습니다.
SwiftUI 비교는 `View`, 배열, `ForEach`까지만 다룹니다. `Identifiable`, 상태 관리, 복잡한 데이터 흐름은 오늘 범위가 아닙니다.

</details>
