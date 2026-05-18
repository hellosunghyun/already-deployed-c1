# Slide 08. Layout과 Navigation

여러 페이지에 같은 Header, Navigation, Footer가 필요합니다.

나쁜 방식:

```text
about.astro에 Header 복붙
projects.astro에 Header 복붙
posts.astro에 Header 복붙
```

좋은 방식:

```text
Layout 하나를 만들고
모든 페이지가 그 Layout을 사용
```

---

## Layout이 필요한 이유

- 같은 코드를 여러 번 복사하지 않음
- Navigation을 한 곳에서 수정 가능
- 페이지마다 같은 사이트처럼 보임

---

## SwiftUI와 비교하면

SwiftUI에서도 같은 버튼이나 상단 영역을 여러 화면에 계속 복사하면 나중에 고치기 어렵습니다.

그래서 공통으로 쓰는 `View`를 따로 만들어 여러 화면에서 다시 씁니다.

Astro의 Layout도 비슷하게, 여러 페이지가 공유하는 바깥 틀입니다.

---

[← 이전](./07-astro-routing.md) · [다음 →](./09-component-data.md)

<details><summary>말할 포인트</summary>

Layout은 "여러 페이지가 공유하는 틀"입니다.
오늘은 완벽한 디자인 시스템을 만드는 것이 아니라, 공통 Header와 Navigation을 한 곳에 모으는 정도로 충분합니다.
SwiftUI의 어려운 `Layout` 프로토콜을 설명하지 않습니다. 여기서는 "공통 View를 만들어 재사용한다"는 쉬운 감각만 비교합니다.

</details>
