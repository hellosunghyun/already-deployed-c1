# Slide 07. Astro 파일 기반 라우팅

[Astro](https://astro.build/)에서는 `src/pages` 안의 파일이 주소가 됩니다.

```text
src/pages/index.astro     → /
src/pages/about.astro     → /about
src/pages/projects.astro  → /projects
src/pages/posts.astro     → /posts
```

---

## 오늘 필요한 감각

파일 이름을 잘 정하면 주소가 생깁니다.

복잡한 서버 설정을 먼저 배울 필요는 없습니다.

---

## SwiftUI와 비교하면

웹에서는 주소가 화면을 가리킵니다.

```text
/about 주소를 열면 About 페이지가 보임
```

SwiftUI 앱에서는 보통 버튼이나 목록을 눌러 다음 화면으로 이동합니다.

```text
NavigationLink를 누르면 AboutView가 보임
```

둘 다 핵심은 같습니다.

```text
사용자가 어디로 이동할 수 있는지 정해두는 것
```

---

[← 이전](./06a-page-section-exercise.md) · [다음 →](./08-layout-navigation.md)

<details><summary>발표자 노트</summary>

**슬라이드 화면 구성**

- `src/pages/*.astro → URL` 매핑 코드블록
- 오늘 필요한 감각: `파일 이름을 잘 정하면 주소가 생깁니다.`
- SwiftUI 비교는 `NavigationLink → AboutView` 정도만 보입니다.

**말할 내용**

Astro 전체 라우팅 문법으로 깊게 들어가지 않습니다.
오늘은 `src/pages`와 URL의 연결만 이해하면 충분합니다.

핵심은 이것입니다.

```text
파일을 만들었더니, 브라우저에서 열 수 있는 주소가 생긴다.
```

SwiftUI를 아는 참가자가 있으면 `NavigationLink`와 가볍게 비교합니다.
다만 iOS 앱에는 웹처럼 `/about` 주소가 항상 있는 것은 아니니, "웹은 주소로 이동하고 앱은 화면 흐름으로 이동한다" 정도만 짚습니다.

</details>
