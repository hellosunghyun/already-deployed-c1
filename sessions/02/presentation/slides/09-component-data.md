# Slide 09. Component와 데이터

Projects 페이지에는 비슷한 카드가 여러 개 나옵니다.

```text
프로젝트 이름
한 줄 설명
내 역할
사용 도구
결과 또는 배운 점
상세 페이지용 slug
```

이런 반복 화면은 Component로 만들기 좋습니다.
카드를 누르면 `slug`를 이용해 프로젝트 상세정보를 볼 수 있게 만들 수도 있습니다.

---

## 데이터와 화면을 나누기

```text
src/data/projects.json = 무엇을 보여줄지
ProjectCard Component = 어떻게 보여줄지
slug = 어떤 상세 페이지 주소로 갈지
```

이렇게 나누면 프로젝트가 3개에서 10개로 늘어나도 추가하기 쉽습니다.
나중에 외부 데이터가 들어오더라도, 화면에서는 오늘 만든 단순한 JSON 모양으로 바꿔서 사용하면 됩니다.

---

## SwiftUI와 비교하면

SwiftUI에서도 반복되는 카드는 보통 작은 `View`로 나눕니다.

```text
ProjectCard Component ≈ ProjectCardView
projects.json ≈ 프로젝트 목록 데이터
반복 표시 ≈ ForEach
```

중요한 감각은 "내용"과 "보여주는 모양"을 나누는 것입니다.

---

[← 이전](./08-layout-navigation.md) · [다음 →](./09a-component-data-analogy.md)

<details><summary>말할 포인트</summary>

JSON, 객체, 컴포넌트라는 단어가 나올 수 있습니다.
여기서 문법을 전부 설명하려고 하면 수업이 무거워집니다.

오늘은 이렇게만 잡습니다.

```text
반복되는 카드는 하나의 틀로 만들고,
프로젝트 내용과 slug만 바꿔 끼운다.
```

SwiftUI 비교는 `View`, 목록 데이터, `ForEach` 정도까지만 갑니다.
`Identifiable`, 상태 관리, 복잡한 데이터 흐름은 오늘 범위가 아닙니다.

</details>
