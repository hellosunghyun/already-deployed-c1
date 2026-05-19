# 03. 페이지 구조 만들기

## 목표

Astro 프로젝트에 `/about`, `/projects`, `/posts` 페이지를 추가합니다.

## 왜 하는가

Home 한 페이지에 모든 내용을 넣으면 방문자가 원하는 정보를 찾기 어렵습니다.
페이지를 역할별로 나누면 사이트가 읽기 쉬워집니다.

## 쉬운 설명

Astro에서는 `src/pages` 폴더 안의 파일이 주소가 됩니다.

```text
src/pages/index.astro     → /
src/pages/about.astro     → /about
src/pages/projects.astro  → /projects
src/pages/posts.astro     → /posts
```

오늘은 먼저 각 페이지에 임시 제목과 짧은 설명만 넣습니다.
디자인은 다음 단계에서 Layout을 만든 뒤 정리합니다.

여기서 나누는 Home / About / Projects / Posts 역할은 정답이 아닙니다.
이번 수업을 진행하기 위한 현재 기준입니다.
나중에 본인 홈페이지의 성격에 맞게 페이지 이름이나 역할을 바꿔도 됩니다.

그래도 페이지를 나누는 데는 이유가 있습니다.
About은 개인이나 회사 소개 페이지처럼 다양한 내용을 쭉 설명하기 좋습니다.
Projects는 비슷한 형식의 카드와 상세정보가 반복되는 구조에 잘 맞습니다.
Posts는 글 중심 콘텐츠를 쌓는 공간이고, 나중에 외부 콘텐츠 소스나 MDX 같은 글 파일 방식으로 확장하기 좋습니다.

## 아주 쉽게 말하면

오늘 이 단계는 "방을 만드는 작업"입니다.

```text
Home 방
About 방
Projects 방
Posts 방
```

아직 방 안을 예쁘게 꾸미지 않아도 됩니다.
먼저 문이 있고, 그 문을 열면 각 방으로 들어갈 수 있는지가 중요합니다.

그래서 이 단계에서 성공한 상태는 아래처럼 단순합니다.

```text
/about을 열면 About 제목이 보인다.
/projects를 열면 Projects 제목이 보인다.
/posts를 열면 Posts 제목이 보인다.
```

## SwiftUI와 비교해서 이해하기

SwiftUI를 조금이라도 본 적이 있다면 아래처럼 비교해볼 수 있습니다.

| Astro 웹사이트 | SwiftUI 앱 |
|---|---|
| `/about` 주소 | About 화면으로 이동 |
| `src/pages/about.astro` | `AboutView` 같은 화면 파일 |
| `<a href="/about">About</a>` 링크 | `NavigationLink` |
| 브라우저 주소창에 직접 입력 가능 | 앱 안에서 버튼이나 목록을 눌러 이동 |

완전히 같은 개념은 아닙니다.
웹사이트는 주소가 중요하고, iPhone 앱은 앱 안에서 화면을 이동하는 흐름이 중요합니다.
하지만 둘 다 **사용자가 어디로 이동할 수 있는지 정해두는 구조**라는 점은 같습니다.

## 공통 프롬프트

```text
현재 Astro 개인 홈페이지에 페이지 구조를 추가하고 싶어.

현재 목표:
- 기존 Home 페이지는 유지한다.
- /about 페이지를 만든다.
- /projects 페이지를 만든다.
- /posts 페이지를 만든다.
- 각 페이지에는 임시 제목과 짧은 설명만 넣는다.

각 페이지의 역할:
- Home: 전체 사이트의 입구
- About: 개인이나 회사 소개 페이지처럼 다양한 내용을 이어서 설명
- Projects: 비슷한 형식의 카드와 상세정보를 반복해서 보여줌
- Posts: 글 중심 콘텐츠를 보여줌

이 역할 구분은 이번 수업을 위한 기본 기준이야.
정답처럼 고정하지 말고, 나중에 내 홈페이지 성격에 맞게 바꿀 수 있다고 설명해줘.
다만 About / Projects / Posts를 나누는 이유는 설명해줘.
About은 소개 흐름, Projects는 반복되는 카드와 상세정보, Posts는 글 중심 콘텐츠라는 차이가 있다고 알려줘.

제약:
- 새 라이브러리를 추가하지 마.
- 기존 배포 설정을 바꾸지 마.
- 관련 없는 파일은 수정하지 마.
- 아직 Layout이나 복잡한 디자인을 만들지 마.
- 오늘은 파일 기반 라우팅을 이해하는 것이 목적이야.

작업 방식:
1. 먼저 현재 src/pages 구조를 확인해줘.
2. 추가하거나 수정할 파일 목록을 제안해줘.
3. Astro에서 파일 이름이 URL이 되는 방식을 초보자도 이해할 수 있게 설명해줘.
4. 가능하면 SwiftUI의 NavigationLink나 AboutView 같은 쉬운 화면 이동 개념과 비교해서 설명해줘.
5. 단, SwiftUI의 어려운 아키텍처 개념은 설명하지 마.
6. 아직 파일을 만들지 말고 계획만 말해줘.
7. 내가 승인하면 파일을 만들어줘.

완료 후 알려줄 것:
1. 생성한 파일 목록
2. 각 파일이 어떤 URL이 되는지
3. 브라우저에서 확인할 주소
4. 다음 단계에서 Layout이 왜 필요한지
5. SwiftUI와 비교했을 때 비슷한 점과 다른 점 한 줄
```

## 승인 후 추가 프롬프트

AI가 계획을 잘 설명했다면 이렇게 말합니다.

```text
좋아. 방금 계획대로 진행해줘.

진행할 때:
- 기존 Home 페이지 내용은 최대한 유지해줘.
- 새 페이지에는 임시 문장을 넣어도 돼.
- 수정 후 변경 파일 목록과 확인 방법을 알려줘.
```

## 브라우저 확인 요청

```text
로컬 개발 서버를 실행하고 브라우저에서 아래 주소가 열리는지 확인해줘.

- /
- /about
- /projects
- /posts

각 페이지가 열리는지, 404가 나는 페이지가 있는지 알려줘.
```

## 중간 점검 질문

페이지를 만들고 나서 바로 다음 단계로 넘어가지 말고 AI에게 한 번 물어봅니다.

```text
지금 만든 페이지 구조를 초보자 기준으로 다시 설명해줘.

특히 아래를 알려줘.
1. 어떤 파일이 어떤 주소가 되는지
2. 아직 Navigation이 없어도 왜 괜찮은지
3. 다음 Layout 단계에서 무엇을 해결할지
```

## 체크박스

- [ ] `/about` 페이지 파일이 생겼다.
- [ ] `/projects` 페이지 파일이 생겼다.
- [ ] `/posts` 페이지 파일이 생겼다.
- [ ] 각 페이지에 임시 제목과 설명이 있다.
- [ ] 브라우저에서 각 주소가 열린다.
- [ ] AI가 파일 기반 라우팅을 설명했다.

## Ready Gate

다음 단계로 넘어가기 전에 아래가 되어 있어야 합니다.

- `/about`, `/projects`, `/posts` 주소가 404 없이 열립니다.
- 새 페이지가 생긴 이유를 이해했습니다.
- 아직 Navigation이 없어도 괜찮다는 것을 알고 있습니다.

## 힌트

<details>
<summary>Hint 1</summary>

주소가 404라면 `src/pages` 아래 파일 이름을 확인하세요.

</details>

<details>
<summary>Hint 2</summary>

`about.astro`가 아니라 `about/index.astro`로 만들어도 `/about` 주소가 될 수 있습니다. 둘 중 하나만 일관되게 쓰면 됩니다.

</details>

<details>
<summary>Hint 3</summary>

AI가 너무 많은 디자인을 추가하면 이렇게 말하세요.

```text
지금은 페이지 구조만 확인하고 싶어.
디자인은 다음 Layout 단계에서 정리할 거니까 과한 스타일은 제거해줘.
```

</details>

<details>
<summary>Hint 4</summary>

SwiftUI 비교가 너무 어려워지면 이렇게 말하세요.

```text
SwiftUI 비교는 NavigationLink와 View 정도로만 설명해줘.
NavigationStack의 자세한 사용법이나 앱 아키텍처 이야기는 오늘 범위에서 빼줘.
```

</details>

## 퀴즈

### 질문

Astro에서 `src/pages/about.astro` 파일은 보통 어떤 주소가 되나요?

- A. `/about`
- B. `/projects`
- C. `/posts`
- D. `/src/pages/about`

<details>
<summary>정답 보기</summary>

**정답**

A

</details>

### 추가 질문

SwiftUI의 `NavigationLink`와 Astro의 `<a href="/about">About</a>` 링크가 비슷한 점은 무엇인가요?

- A. 둘 다 사용자를 다른 화면이나 페이지로 이동시킨다.
- B. 둘 다 GitHub 계정을 만든다.
- C. 둘 다 npm 패키지를 설치한다.
- D. 둘 다 외부 API token을 만든다.

<details>
<summary>정답 보기</summary>

**정답**

A

</details>

## 저장 체크포인트

`AGENTS.md`가 commit 규칙을 알려주므로, 여기서는 저장하기 좋은 시점과 메시지 예시만 남깁니다.
페이지가 모두 열리면 아래 문장을 commit 메시지로 사용할 수 있습니다.

```text
feat: 기본 페이지 구조 추가
```

## 다음 단계

[04. 공통 Layout과 Navigation 만들기 →](./04-layout-navigation.md)
