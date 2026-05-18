# 08. Posts 기본 구조 만들기

## 목표

Posts 페이지에 샘플 글 목록을 만듭니다.

## 왜 하는가

4회차에는 Notion을 콘텐츠 관리 도구처럼 연결할 예정입니다.
하지만 Notion API를 붙이기 전에, 글 목록이 홈페이지에서 어떤 구조로 보일지 먼저 정해두면 이후 작업이 쉬워집니다.

## 쉬운 설명

오늘 Posts는 실제 블로그 시스템이 아닙니다.

오늘은 샘플 데이터로 아래 형태를 만듭니다.

- 글 제목
- 날짜
- 요약
- 태그

나중에 이 샘플 데이터를 Notion에서 가져온 데이터로 바꿀 수 있습니다.

## SwiftUI와 비교해서 이해하기

SwiftUI에서 글 목록을 만든다면 보통 여러 글 데이터를 배열로 두고 `List`나 `ForEach`로 보여주는 방식을 떠올릴 수 있습니다.

| Astro Posts | SwiftUI에서 떠올릴 쉬운 개념 |
|---|---|
| 샘플 글 배열 | 글 데이터 배열 |
| 글 카드 또는 목록 항목 | 글 하나를 보여주는 작은 View |
| `title`, `date`, `summary`, `tags` | 글 데이터의 속성 |
| 나중에 Notion 데이터로 교체 | 나중에 다른 데이터로 목록을 채움 |

오늘은 SwiftData, 서버 통신, 앱 상태 관리를 설명하지 않습니다.
단순히 **여러 개의 글 데이터를 같은 모양으로 보여준다**는 점만 비교합니다.

## 샘플 글 정보 정리

```text
글 1
- title:
- date:
- summary:
- tags:

글 2
- title:
- date:
- summary:
- tags:
```

템플릿은 [글 목록 샘플 데이터 템플릿](../templates/post-list-data.md)을 참고하세요.

## 공통 프롬프트

```text
Posts 페이지에 글 목록 기본 구조를 만들고 싶어.

현재 상태:
- Astro 개인 홈페이지가 있다.
- /posts 페이지가 있다.
- 공통 Layout과 Navigation이 있다.

목표:
- 샘플 글 1~2개를 보여준다.
- 각 글에는 title, date, summary, tags가 보이게 한다.
- 나중에 Notion에서 가져온 글로 대체할 수 있는 구조로 만든다.
- 지금은 Notion API를 붙이지 않는다.

샘플 글:

글 1
- title: [예: 첫 배포를 하며 배운 것]
- date: [예: 2026-05-19]
- summary: [예: Astro와 GitHub Pages로 개인 홈페이지를 처음 배포하며 배운 점을 정리합니다.]
- tags: [예: Astro, GitHub Pages, 회고]

글 2
- title: [예: AI에게 코딩을 맡길 때 필요한 맥락]
- date: [예: 2026-05-19]
- summary: [예: 좋은 프롬프트가 왜 필요한지, 계획과 검증을 어떻게 요청하는지 정리합니다.]
- tags: [예: Codex, AI, 작업기록]

제약:
- Notion API를 지금 붙이지 마.
- token, secret, API key를 만들거나 코드에 쓰지 마.
- 새 라이브러리를 추가하지 마.
- 관련 없는 파일은 수정하지 마.
- 실제 글 상세 페이지까지 만들 필요는 없어. 오늘은 목록 구조가 목표야.

작업 방식:
1. 먼저 현재 Posts 페이지를 확인해줘.
2. 샘플 데이터를 어디에 둘지 제안해줘.
3. 나중에 Notion 데이터로 바꿀 때 어떤 부분이 교체될지 설명해줘.
4. 가능하면 SwiftUI의 List나 ForEach와 비교해서 설명해줘.
5. 단, SwiftData, 서버 통신, 앱 상태 관리는 오늘 범위에서 빼줘.
6. 아직 수정하지 말고 계획만 보여줘.
7. 내가 승인하면 구현해줘.

완료 후 알려줄 것:
1. 변경한 파일 목록
2. 글 데이터가 어디에 있는지
3. title, date, summary, tags가 어디에 표시되는지
4. Notion 연결 전까지 이 구조가 어떤 역할을 하는지
5. 브라우저 확인 주소
6. SwiftUI의 List나 ForEach와 비교했을 때 비슷한 점 한 줄
```

## Notion을 붙이려는 AI를 막는 프롬프트

AI가 너무 빨리 Notion API를 붙이려고 하면 이렇게 말하세요.

```text
지금은 4회차가 아니라 2회차야.
Notion API, Integration, token, secret은 아직 사용하지 마.
오늘은 샘플 글 데이터로 Posts 목록 구조만 만들어줘.
나중에 Notion 데이터로 바꿀 수 있는 부분을 설명만 해줘.
```

## 체크박스

- [ ] Posts 페이지에 샘플 글이 보인다.
- [ ] 각 글에 제목이 보인다.
- [ ] 날짜가 보인다.
- [ ] 요약이 보인다.
- [ ] 태그가 보인다.
- [ ] Notion API를 붙이지 않았다.
- [ ] 나중에 바꿀 데이터 위치를 알고 있다.

## Ready Gate

다음 단계로 넘어가기 전에 아래가 되어 있어야 합니다.

- Posts 페이지가 단순 임시 제목만 있는 상태가 아닙니다.
- 샘플 글 목록이 보입니다.
- Notion 관련 secret이나 token을 만들지 않았습니다.

## 힌트

<details>
<summary>Hint 1</summary>

오늘 글 제목은 진짜 글이 아니어도 됩니다. 나중에 쓸 글의 자리라고 생각하세요.

</details>

<details>
<summary>Hint 2</summary>

날짜 형식은 `YYYY-MM-DD`처럼 단순하게 시작하세요.

</details>

<details>
<summary>Hint 3</summary>

AI가 글 상세 페이지까지 만들자고 하면 "오늘은 목록까지만"이라고 범위를 줄이세요.

</details>

<details>
<summary>Hint 4</summary>

SwiftUI 비교가 너무 깊어지면 이렇게 말하세요.

```text
SwiftUI 비교는 List와 ForEach 정도로만 설명해줘.
SwiftData, 네트워크 요청, 상태 관리는 오늘 범위에서 빼줘.
```

</details>

## 퀴즈

### 질문

2회차에서 Posts 구조를 만들 때 하지 않는 것은?

A. 샘플 글 목록 만들기
B. 글 제목, 날짜, 요약 표시하기
C. Notion API token을 코드에 넣기
D. 나중에 Notion으로 바꿀 수 있게 구조 생각하기

<details>
<summary>정답 보기</summary>

**정답**

C

</details>

### 추가 질문

Posts 목록을 SwiftUI의 `List`와 비교할 때 가장 비슷한 점은 무엇인가요?

A. 여러 글 데이터를 같은 목록 모양으로 보여준다.
B. GitHub 저장소를 만든다.
C. 배포 workflow를 실행한다.
D. Notion secret을 만든다.

<details>
<summary>정답 보기</summary>

**정답**

A

</details>

## 커밋 가이드

Posts 목록이 안정적으로 보이면 commit을 권장합니다.

```text
feat: 글 목록 기본 구조 추가
```

## 다음 단계

[09. 브라우저와 build로 검증하기 →](./09-browser-build-review.md)
