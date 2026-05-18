# 04. 공통 Layout과 Navigation 만들기

## 목표

모든 페이지에서 공통으로 사용할 Layout과 Navigation을 만듭니다.

## 왜 하는가

여러 페이지에 Header와 Navigation을 복사해서 붙이면 나중에 수정이 어려워집니다.
Layout을 만들면 모든 페이지가 같은 틀을 공유할 수 있습니다.

## 쉬운 설명

Layout은 여러 페이지가 같이 쓰는 바깥 틀입니다.

```text
Layout
├── Header
├── Navigation
├── 현재 페이지 내용
└── Footer
```

페이지는 자신의 내용만 가지고, 공통 구조는 Layout이 담당합니다.

## SwiftUI와 비교해서 이해하기

SwiftUI에서도 여러 화면에 같은 상단 영역이나 버튼 묶음을 계속 복사하면 나중에 수정이 어렵습니다.
그래서 공통으로 쓰는 작은 `View`를 따로 만들어 여러 화면에서 다시 씁니다.

| Astro | SwiftUI에서 떠올릴 쉬운 개념 |
|---|---|
| `Layout.astro` | 여러 화면이 같이 쓰는 공통 `View` |
| Header / Navigation | 상단 제목, 버튼 묶음 |
| `<slot />` | 각 페이지의 실제 내용이 들어가는 자리 |

여기서 말하는 Layout은 SwiftUI의 어려운 `Layout` 프로토콜 이야기가 아닙니다.
오늘은 단순히 **공통 틀을 한 번 만들고 여러 화면에서 다시 쓴다**는 감각만 가져가면 됩니다.

## 공통 프롬프트

```text
이제 모든 페이지에서 공통으로 사용할 Layout과 Navigation을 만들고 싶어.

현재 상태:
- Astro 개인 홈페이지 프로젝트가 있다.
- /, /about, /projects, /posts 페이지가 있다.
- 아직 페이지마다 공통 Header와 Navigation이 정리되어 있지 않다.

목표:
- 공통 Layout 파일을 만든다.
- Header를 만든다.
- Navigation에 Home / About / Projects / Posts 링크를 넣는다.
- Footer를 만든다.
- 모든 페이지가 같은 Layout을 사용하게 한다.

디자인 방향:
- 흰 배경
- 넓은 여백
- 읽기 쉬운 고딕 느낌
- 링크는 명확하게 보이게
- 모바일에서도 줄이 깨지지 않게
- 과한 애니메이션이나 장식 없음

제약:
- 새 라이브러리를 추가하지 마.
- 기존 배포 설정을 바꾸지 마.
- 관련 없는 파일은 수정하지 마.
- Header와 Footer를 각 페이지에 복붙하지 말고 공통 Layout으로 분리해줘.
- 초보자가 이해할 수 있게 Layout, slot, Navigation의 역할을 설명해줘.
- SwiftUI를 예로 들 때는 공통 View를 재사용하는 정도로만 쉽게 비교해줘.
- SwiftUI의 어려운 Layout 프로토콜이나 앱 아키텍처 이야기는 하지 마.

작업 방식:
1. 먼저 현재 파일 구조를 확인해줘.
2. 만들거나 수정할 파일 목록을 제안해줘.
3. Layout을 어떤 경로에 만들지 설명해줘.
4. 아직 파일을 수정하지 말고 계획만 말해줘.
5. 내가 승인하면 진행해줘.

완료 후 알려줄 것:
1. 변경한 파일 목록
2. 각 파일의 역할
3. Navigation 링크가 가리키는 주소
4. 브라우저에서 확인할 주소
5. 다음에 Home 페이지를 어떻게 정리하면 좋을지
6. SwiftUI의 공통 View와 비교했을 때 비슷한 점 한 줄
```

## 승인 후 추가 프롬프트

```text
좋아. 방금 계획대로 Layout과 Navigation을 만들어줘.

추가 조건:
- 모든 페이지가 같은 Layout을 사용해야 해.
- 현재 페이지 내용은 사라지면 안 돼.
- Navigation 링크는 /, /about, /projects, /posts 네 개를 포함해줘.
- 수정 후 npm run build는 아직 하지 말고, 먼저 변경 내용을 설명해줘.
```

## 브라우저 확인 요청

```text
로컬에서 화면을 확인해줘.

확인할 것:
- Home / About / Projects / Posts 네 페이지 모두 같은 Header가 보이는지
- Navigation 링크를 눌렀을 때 각 페이지로 이동하는지
- 모바일 폭에서도 Navigation이 너무 심하게 깨지지 않는지
- Footer가 모든 페이지에 보이는지

문제가 있으면 어떤 파일을 고치면 되는지 알려줘.
```

## 체크박스

- [ ] 공통 Layout 파일이 생겼다.
- [ ] 모든 페이지에 같은 Header가 보인다.
- [ ] Navigation에 Home / About / Projects / Posts 링크가 있다.
- [ ] Navigation 링크로 페이지 이동이 된다.
- [ ] Footer가 모든 페이지에 보인다.
- [ ] AI가 Layout과 slot의 역할을 설명했다.

## Ready Gate

다음 단계로 넘어가기 전에 아래가 되어 있어야 합니다.

- 네 페이지 모두 같은 Navigation을 사용합니다.
- Header나 Navigation을 한 곳에서 수정할 수 있는 구조입니다.
- 페이지 내용이 사라지지 않았습니다.

## 힌트

<details>
<summary>Hint 1</summary>

Astro Layout은 보통 `src/layouts/Layout.astro` 같은 위치에 둡니다.

</details>

<details>
<summary>Hint 2</summary>

Astro에서 Layout 안에 페이지 내용을 넣으려면 보통 `<slot />`을 사용합니다.

</details>

<details>
<summary>Hint 3</summary>

Navigation이 모든 페이지에 안 보이면 각 페이지가 Layout을 실제로 import하고 있는지 확인하세요.

</details>

<details>
<summary>Hint 4</summary>

`<slot />`이 어렵다면 이렇게 생각하세요.

```text
Layout은 공통 껍데기이고,
slot은 각 페이지 내용이 들어갈 빈자리입니다.
```

</details>

## 퀴즈

### 질문

Layout을 사용하는 가장 큰 이유는 무엇인가요?

A. 같은 Header와 Navigation을 여러 페이지에 복사하지 않기 위해
B. GitHub 계정을 만들기 위해
C. npm 설치를 빠르게 하기 위해
D. 모든 페이지 주소를 없애기 위해

<details>
<summary>정답 보기</summary>

**정답**

A

</details>

### 추가 질문

SwiftUI와 비교했을 때 Astro Layout을 이해하는 쉬운 방식은 무엇인가요?

A. 여러 화면에서 같이 쓰는 공통 View처럼 생각한다.
B. 앱의 데이터베이스처럼 생각한다.
C. GitHub 로그인 화면처럼 생각한다.
D. npm 설치 도구처럼 생각한다.

<details>
<summary>정답 보기</summary>

**정답**

A

</details>

## 커밋 가이드

Layout과 Navigation이 안정적으로 보이면 commit을 권장합니다.

```text
feat: 공통 레이아웃과 내비게이션 추가
```

## 다음 단계

[05. Home 페이지를 입구로 정리하기 →](./05-home-entry.md)
