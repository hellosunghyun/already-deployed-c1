# 10. GitHub 저장소 만들기

## 목표

[GitHub](https://github.com/)에 개인 홈페이지를 올릴 저장소를 만듭니다.

## 왜 하는가

[GitHub Pages](https://pages.github.com/)는 GitHub 저장소에 있는 파일을 기준으로 사이트를 배포합니다. 내 컴퓨터에만 있는 파일은 인터넷에 올라가지 않습니다.

## 기본 트랙: 사용자 사이트

오늘은 가능하면 **사용자 사이트** 트랙을 사용합니다.

저장소 이름은 아래 형식이어야 합니다.

```text
<github-username>.github.io
```

예를 들어 GitHub 사용자명이 `hello123`이면 저장소 이름은 아래처럼 만듭니다.

```text
hello123.github.io
```

최종 주소는 아래처럼 됩니다.

```text
https://hello123.github.io
```

## GitHub 사용자명 확인하기

1. [GitHub](https://github.com/)에 로그인합니다.
2. 오른쪽 위 프로필을 누릅니다.
3. 프로필 페이지 주소를 봅니다.
4. `https://github.com/사용자명`에서 사용자명을 확인합니다.

## 공통 프롬프트

```text
이 프로젝트를 GitHub Pages 사용자 사이트로 배포하려고 해.

내 GitHub 사용자 사이트로 배포할 예정이라 저장소 이름은 <내 GitHub 사용자명>.github.io 형식이어야 한다고 알고 있어.

나를 도와줘.

1. 내가 GitHub 웹사이트에서 직접 해야 하는 일을 알려줘.
2. GitHub CLI를 사용할 수 있다면 터미널에서 도와줄 수 있는 일을 알려줘.
3. 아직 push하지 말고, 먼저 전체 계획을 설명해줘.
4. GitHub 사용자명과 저장소 이름이 왜 중요한지도 쉽게 설명해줘.
```

## GitHub 웹사이트에서 직접 할 일

1. [GitHub 새 저장소 만들기](https://github.com/new)로 이동합니다.
2. 저장소 이름을 `<github-username>.github.io`로 입력합니다.
3. Public 저장소로 만듭니다.
4. README는 지금 추가하지 않는 것을 추천합니다. 이미 로컬 프로젝트가 있기 때문입니다.
5. 저장소를 생성합니다.

## 체크박스

- [ ] GitHub 사용자명을 확인했다.
- [ ] `<username>.github.io` 이름의 저장소를 만들었다.
- [ ] 저장소 URL을 확인했다.
- [ ] AI가 다음 계획을 설명했다.

## Ready Gate

다음 단계로 넘어가기 전에 아래가 되어 있어야 합니다.

- GitHub 저장소가 만들어졌습니다.
- 저장소 이름이 `<username>.github.io` 형식입니다.
- 저장소 URL을 알고 있습니다.

## 힌트

<details>
<summary>Hint 1</summary>

저장소 이름이 정확해야 `https://<username>.github.io` 주소가 자연스럽게 만들어집니다.

</details>

<details>
<summary>Hint 2</summary>

이미 같은 이름의 저장소가 있다면 기존 개인 홈페이지가 있을 수 있습니다. 지우지 말고 도움을 요청하세요.

</details>

## 퀴즈

### 질문

GitHub Pages 사용자 사이트를 만들 때 기본 저장소 이름은?

A. `my-homepage`  
B. `portfolio`  
C. `<github-username>.github.io`  
D. `astro-project`

<details>
<summary>정답 보기</summary>

**정답**

C

</details>

## 다음 단계

[11. GitHub에 코드 올리기 →](./11-push-to-github.md)
