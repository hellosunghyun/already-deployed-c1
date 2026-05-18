# 11. GitHub에 코드 올리기

## 목표

내 컴퓨터의 프로젝트 파일을 GitHub 저장소에 올립니다.

## 왜 하는가

GitHub Pages는 GitHub 저장소에 올라간 파일을 기준으로 배포합니다. 따라서 먼저 프로젝트를 GitHub에 저장해야 합니다.

## 공통 프롬프트

```text
이제 이 Astro 프로젝트를 방금 만든 GitHub 저장소에 올리고 싶어.

조건:
- 먼저 현재 git 상태를 확인해줘.
- GitHub remote가 연결되어 있는지 확인해줘.
- 아직 연결되어 있지 않다면 연결 방법을 설명해줘.
- GitHub CLI가 설치되어 있다면 gh 명령어 사용 가능 여부도 확인해줘.
- commit 메시지는 "chore: 초기 Astro 개인 홈페이지 생성"으로 해줘.
- push 전에 어떤 파일이 올라가는지 설명해줘.
- secret, token, password, API key 같은 민감한 정보가 올라가지 않는지 확인해줘.
- 내가 승인하면 commit과 push를 진행해줘.
```

## Codex에게 GitHub 로그인까지 도와달라고 하기

GitHub CLI가 설치되어 있다면 Codex에게 이렇게 요청할 수 있습니다.

```text
GitHub CLI를 사용해서 GitHub 인증 상태를 확인해줘.
로그인이 안 되어 있다면 gh auth login을 어떻게 진행해야 하는지 단계별로 설명해줘.
내가 직접 입력해야 하는 부분과 네가 실행할 수 있는 부분을 나눠서 알려줘.
```

## 체크박스

- [ ] AI가 git 상태를 확인했다.
- [ ] GitHub remote가 연결되었다.
- [ ] 첫 commit이 만들어졌다.
- [ ] GitHub에 push가 완료되었다.
- [ ] GitHub 웹사이트에서 프로젝트 파일이 보인다.

## Ready Gate

다음 단계로 넘어가기 전에 아래가 되어 있어야 합니다.

- GitHub 저장소에 프로젝트 파일이 보입니다.
- `package.json`, `src` 폴더가 GitHub에 올라가 있습니다.
- push 과정에서 권한 오류가 나지 않았습니다.

## 힌트

<details>
<summary>Hint 1</summary>

GitHub 웹사이트에서 파일이 보이면 push는 성공한 것입니다.

</details>

<details>
<summary>Hint 2</summary>

권한 오류가 나면 GitHub 로그인 또는 인증 문제가 있을 수 있습니다.

</details>

<details>
<summary>Hint 3</summary>

에러가 나면 이렇게 질문하세요.

```text
GitHub에 push하는 단계에서 아래 오류가 났어.
오류 원인을 초보자도 이해할 수 있게 설명하고, 다음 한 단계만 알려줘.

[오류 붙여넣기]
```

</details>

## 퀴즈

### 질문

`push`는 무엇에 가장 가까울까요?

A. 브라우저에서 홈페이지를 여는 것  
B. 내 컴퓨터의 변경 사항을 GitHub로 올리는 것  
C. 디자인을 바꾸는 것  
D. npm 패키지를 설치하는 것

<details>
<summary>정답 보기</summary>

**정답**

B

</details>

## 다음 단계

[12. GitHub Pages 배포하기 →](./12-deploy-github-pages.md)
