# 07. Projects 카드 만들기

## 목표

Projects 페이지에 프로젝트 또는 경험 3개를 카드 형태로 보여줍니다.

## 왜 하는가

Projects는 "나는 이런 것을 해봤다"를 보여주는 증거입니다.
단순히 이름만 나열하기보다, 무엇을 했고 무엇을 배웠는지 구조화하면 방문자가 이해하기 쉽습니다.

## 쉬운 설명

좋은 프로젝트 카드에는 아래 정보가 들어갑니다.

- 프로젝트 이름
- 한 줄 설명
- 내가 맡은 역할
- 사용한 도구 또는 기술
- 결과 또는 배운 점

반복되는 카드는 Component로 만들면 좋습니다.
프로젝트 내용은 배열 데이터로 두면 나중에 추가하기 쉽습니다.

## SwiftUI와 비교해서 이해하기

SwiftUI에서 비슷한 프로젝트 카드를 만든다면 보통 아래처럼 생각할 수 있습니다.

| Astro | SwiftUI에서 떠올릴 쉬운 개념 |
|---|---|
| `ProjectCard.astro` | `ProjectCardView` |
| 프로젝트 배열 | `projects` 배열 |
| 배열을 돌며 카드 표시 | `ForEach` |
| `title`, `description` 같은 값 | 카드에 넣을 데이터 |

핵심은 Swift 문법을 외우는 것이 아닙니다.
**프로젝트 내용**과 **카드를 보여주는 모양**을 나누면, 프로젝트가 늘어날 때 수정하기 쉽다는 점을 이해하면 됩니다.

## 프로젝트 정보 정리

3개가 없다면 임시 프로젝트, 수업 과제, 동아리 활동, 개인 학습 기록도 괜찮습니다.

```text
프로젝트 1
- title:
- description:
- role:
- tools:
- result:

프로젝트 2
- title:
- description:
- role:
- tools:
- result:

프로젝트 3
- title:
- description:
- role:
- tools:
- result:
```

템플릿은 [프로젝트 카드 데이터 템플릿](../templates/project-card-data.md)을 참고하세요.

## 공통 프롬프트

```text
Projects 페이지에 프로젝트 카드 3개를 추가하고 싶어.

현재 상태:
- Astro 개인 홈페이지가 있다.
- /projects 페이지가 있다.
- 공통 Layout과 Navigation이 있다.

내 프로젝트 정보:

프로젝트 1
- title: [입력]
- description: [입력]
- role: [입력]
- tools: [입력]
- result: [입력]

프로젝트 2
- title: [입력]
- description: [입력]
- role: [입력]
- tools: [입력]
- result: [입력]

프로젝트 3
- title: [입력]
- description: [입력]
- role: [입력]
- tools: [입력]
- result: [입력]

목표:
- Projects 페이지에 카드 3개를 보여준다.
- 각 카드에 title, description, role, tools, result가 보이게 한다.
- 프로젝트 데이터와 카드 화면을 분리한다.
- 같은 카드 구조를 반복해서 사용한다.
- 나중에 프로젝트를 쉽게 추가할 수 있게 한다.

구현 방향:
- 가능하면 ProjectCard 같은 작은 Component를 만든다.
- 프로젝트 목록은 배열 데이터로 관리한다.
- 데이터가 많아져도 카드 코드 자체를 계속 복사하지 않게 한다.

제약:
- 새 라이브러리를 추가하지 마.
- 관련 없는 파일은 수정하지 마.
- 디자인은 기존 Layout과 어울리게만 정리해줘.
- 너무 화려한 카드 디자인은 피하고 읽기 쉽게 해줘.
- 외부 이미지나 아이콘은 지금 추가하지 마.

작업 방식:
1. 먼저 현재 Projects 페이지 구조를 확인해줘.
2. 만들 파일과 수정할 파일을 제안해줘.
3. 배열 데이터와 Component가 각각 어떤 역할인지 초보자도 이해할 수 있게 설명해줘.
4. 가능하면 SwiftUI의 ProjectCardView, 배열, ForEach 정도와 비교해서 설명해줘.
5. 단, Identifiable, 상태 관리, 복잡한 데이터 흐름은 오늘 범위에서 빼줘.
6. 아직 수정하지 말고 계획만 보여줘.
7. 내가 승인하면 구현해줘.

완료 후 알려줄 것:
1. 변경한 파일 목록
2. 프로젝트 데이터가 어디에 있는지
3. 카드 Component가 있다면 그 역할
4. 프로젝트를 하나 더 추가하려면 어디를 수정하면 되는지
5. 브라우저 확인 주소
6. SwiftUI의 ForEach와 비교했을 때 비슷한 점 한 줄
```

## 프로젝트가 아직 없을 때 프롬프트

```text
아직 보여줄 프로젝트가 3개 없어서 임시 카드로 시작하고 싶어.

조건:
- 실제 경력처럼 과장하지 마.
- "준비 중", "학습 중", "워크숍 실습"처럼 솔직한 표현을 사용해줘.
- 나중에 쉽게 바꿀 수 있게 데이터 위치를 명확히 해줘.
- 카드 예시는 개인 홈페이지에 올려도 부끄럽지 않을 정도로 담백하게 써줘.
```

## 체크박스

- [ ] Projects 페이지에 카드 3개가 보인다.
- [ ] 각 카드에 제목이 있다.
- [ ] 각 카드에 한 줄 설명이 있다.
- [ ] 각 카드에 내 역할이 있다.
- [ ] 각 카드에 사용 도구 또는 기술이 있다.
- [ ] 각 카드에 결과 또는 배운 점이 있다.
- [ ] 프로젝트를 하나 더 추가할 위치를 안다.

## Ready Gate

다음 단계로 넘어가기 전에 아래가 되어 있어야 합니다.

- Projects 페이지가 단순 임시 제목만 있는 상태가 아닙니다.
- 카드가 반복 구조로 정리되어 있습니다.
- 프로젝트 데이터와 화면 구조가 어디에 있는지 알고 있습니다.

## 힌트

<details>
<summary>Hint 1</summary>

프로젝트가 거창할 필요는 없습니다. "첫 Astro 개인 홈페이지"도 오늘은 프로젝트 카드가 될 수 있습니다.

</details>

<details>
<summary>Hint 2</summary>

`tools`에는 프로그래밍 언어만 넣지 않아도 됩니다. Figma, Notion, GitHub, Codex 같은 도구도 들어갈 수 있습니다.

</details>

<details>
<summary>Hint 3</summary>

AI가 데이터를 카드 HTML 안에 모두 직접 박아 넣었다면 이렇게 말하세요.

```text
프로젝트 내용을 배열 데이터로 분리하고,
카드는 같은 Component를 반복해서 렌더링하는 구조로 바꿔줘.
초보자도 어디에 새 프로젝트를 추가해야 하는지 알 수 있게 설명해줘.
```

</details>

<details>
<summary>Hint 4</summary>

SwiftUI 비교가 너무 어려워지면 이렇게 범위를 줄이세요.

```text
SwiftUI 비교는 ProjectCardView, 배열, ForEach까지만 해줘.
Identifiable이나 상태 관리 같은 개념은 오늘 설명하지 마.
```

</details>

## 퀴즈

### 질문

프로젝트 데이터를 배열로 관리하는 이유로 가장 적절한 것은?

A. 프로젝트가 많아져도 추가와 수정이 쉬워지기 때문에
B. GitHub Pages가 반드시 요구하기 때문에
C. npm 설치가 빨라지기 때문에
D. localhost 주소가 바뀌기 때문에

<details>
<summary>정답 보기</summary>

**정답**

A

</details>

### 추가 질문

Astro의 프로젝트 배열과 SwiftUI의 `ForEach` 예시를 비교할 때 핵심은 무엇인가요?

A. 같은 모양의 카드를 여러 데이터로 반복해서 보여줄 수 있다는 것
B. GitHub Pages 설정을 자동으로 바꾼다는 것
C. Notion token을 숨겨준다는 것
D. 브라우저 주소를 없앤다는 것

<details>
<summary>정답 보기</summary>

**정답**

A

</details>

## 커밋 가이드

Projects 카드가 안정적으로 보이면 commit을 권장합니다.

```text
feat: 프로젝트 카드 섹션 추가
```

## 다음 단계

[08. Posts 기본 구조 만들기 →](./08-posts-list.md)
