# 04. 환경 확인과 설치

## 목표

[Node.js](https://nodejs.org/), [npm](https://docs.npmjs.com/about-npm), [Git](https://git-scm.com/), [GitHub CLI](https://cli.github.com/)가 준비되어 있는지 확인하고, 없으면 AI에게 설치를 도와달라고 요청합니다.

## 왜 하는가

- Astro 프로젝트를 만들려면 Node.js와 npm이 필요합니다.
- GitHub에 올리려면 Git이 필요합니다.
- GitHub CLI가 있으면 GitHub 로그인과 저장소 연결을 더 쉽게 할 수 있습니다.

## 쉬운 설명

| 단어 | 오늘 필요한 의미 |
|---|---|
| Terminal | Mac에서 명령어를 실행하는 앱 |
| Node.js | JavaScript 프로젝트 도구를 실행하는 환경 |
| npm | 패키지 설치와 명령어 실행 도구 |
| Git | 변경 기록을 남기는 도구 |
| GitHub CLI | 터미널에서 GitHub 작업을 쉽게 하는 도구 |
| Homebrew | Mac에서 개발 도구를 설치하는 패키지 관리자 |

## 공통 프롬프트

아래 프롬프트는 Codex / Claude Code / Antigravity에서 모두 사용할 수 있습니다.

```text
내 Mac에서 Astro 개인 홈페이지 프로젝트를 만들 준비가 되었는지 확인해줘.

아래 항목을 확인해줘.

- Node.js 설치 여부
- npm 설치 여부
- Git 설치 여부
- GitHub CLI 설치 여부
- Homebrew 설치 여부

중요:
1. 아직 아무 파일도 만들지 마.
2. 먼저 어떤 명령어로 확인할지 계획을 설명해줘.
3. 내가 승인하면 확인 명령을 실행해줘.
4. 설치가 필요한 항목이 있으면, 어떤 도구를 왜 설치해야 하는지 설명해줘.
5. 설치도 내가 승인한 뒤 진행해줘.
6. 설치 후 다시 버전을 확인해줘.
```

## 설치가 필요할 때 추가 프롬프트

```text
필요한 도구가 설치되어 있지 않다면 설치를 도와줘.

조건:
- Mac 기준으로 안내해줘.
- Homebrew가 있으면 Homebrew를 사용해도 돼.
- 설치 전에 어떤 명령어를 실행할지 먼저 설명해줘.
- 내가 승인하면 설치를 진행해줘.
- 설치 후 node -v, npm -v, git --version, gh --version으로 다시 확인해줘.
```

## Codex 사용 팁

Codex 안에 터미널 영역이 있으면 거기서 확인합니다. 터미널이 보이지 않으면 Codex에게 이렇게 물어보세요.

```text
Codex에서 터미널을 열고 명령어를 실행하려면 어떻게 해야 해?
지금 화면 기준으로 안내해줘.
```

## 체크박스

- [ ] Node.js 버전이 확인되었다.
- [ ] npm 버전이 확인되었다.
- [ ] Git 버전이 확인되었다.
- [ ] GitHub CLI 버전이 확인되었거나 설치 필요 여부를 알게 되었다.
- [ ] 필요한 설치가 있다면 AI가 계획을 설명했다.
- [ ] 설치 후 다시 버전 확인을 했다.

## Ready Gate

다음 단계로 넘어가기 전에 아래가 되어 있어야 합니다.

- `node -v` 결과가 나오거나, 설치가 필요하다는 것을 확인했습니다.
- `npm -v` 결과가 나오거나, 설치가 필요하다는 것을 확인했습니다.
- `git --version` 결과가 나오거나, 설치가 필요하다는 것을 확인했습니다.

## 힌트

<details>
<summary>Hint 1</summary>

버전 숫자가 나오면 대부분 준비된 것입니다.

</details>

<details>
<summary>Hint 2</summary>

`command not found`가 나오면 설치가 필요하다는 뜻일 가능성이 큽니다.

</details>

<details>
<summary>Hint 3</summary>

설치가 오래 걸릴 수 있습니다. 멈춘 것처럼 보여도 잠시 기다려보세요.

</details>

## 퀴즈

### 질문

오늘 npm의 역할에 가장 가까운 것은?

- A. 홈페이지를 인터넷에 배포하는 서비스
- B. 프로젝트에 필요한 패키지를 설치하고 명령어를 실행하는 도구
- C. GitHub 계정을 만드는 도구
- D. 브라우저 주소

<details>
<summary>정답 보기</summary>

**정답**

B

**해설**

npm은 배포 서비스가 아닙니다. 오늘은 `npm run dev`, `npm run build` 같은 프로젝트 명령어를 실행하는 데 사용합니다.

</details>

## 다음 단계

[05. AGENTS.md / CLAUDE.md 만들기 →](./05-agent-instruction-file.md)
