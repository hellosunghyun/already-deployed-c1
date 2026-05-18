# 1회차 완료 예제 코드베이스

이 폴더는 **1회차 워크북을 끝까지 진행했을 때의 예시 결과물**입니다.

1회차를 마치지 못한 사람은 이 폴더를 기준 상태로 열어 워크북 흐름을 이어갈 수 있습니다.

## 무엇이 들어 있나요?

- Astro 개인 홈페이지 프로젝트
- Home 페이지 첫 버전
- 이름 또는 닉네임을 넣을 수 있는 큰 제목
- 한 줄 소개
- GitHub Pages 배포 workflow 예시
- Codex가 지켜야 할 `AGENTS.md`

## 가장 쉬운 방법

터미널 명령어를 직접 치기보다, **Codex 앱에 일을 맡기는 방식**을 권장합니다.

1. Codex 앱을 엽니다.
2. ChatGPT 계정으로 로그인합니다.
3. 이 예제 폴더를 프로젝트 폴더로 선택합니다.
4. 아래 문장을 Codex에게 보냅니다.

```text
이 폴더는 1회차 완료 예제야.
파일 구조를 먼저 설명해줘.
그 다음 필요한 패키지를 설치하고, 로컬 미리보기 서버를 실행해줘.
브라우저에서 확인할 주소도 알려줘.
내가 직접 터미널 명령어를 입력하지 않아도 되게, 네가 가능한 작업은 직접 해줘.
```

## 폴더를 준비하는 방법

상황에 따라 둘 중 하나를 선택하면 됩니다.

### 이미 전체 저장소를 받은 경우

Codex 앱에서 아래 폴더를 프로젝트로 선택합니다.

```text
already-deployed-c1/sessions/01/example-homepage
```

그 다음 위의 “가장 쉬운 방법” 요청문을 Codex에게 보내면 됩니다.

### 예제 폴더만 가져오고 싶은 경우

GitHub 웹 화면에서는 하위 폴더 하나만 일반적인 방식으로 clone하기 어렵습니다.
이럴 때는 Codex에게 `sparse checkout` 방식으로 이 폴더만 가져오게 맡기면 됩니다.

1. Finder에서 비어 있는 작업 폴더를 하나 만듭니다.
2. 그 폴더를 Codex 앱 프로젝트로 엽니다.
3. Codex에게 아래처럼 요청합니다.

```text
GitHub 저장소 https://github.com/hellosunghyun/already-deployed-c1 에서
sessions/01/example-homepage 폴더만 이 현재 폴더로 가져와줘.

조건:
- git sparse checkout 방식을 사용해줘.
- 최종적으로 이 폴더에서 package.json이 바로 보이게 정리해줘.
- 가져온 뒤 파일 구조를 설명해줘.
- 필요한 패키지를 설치하고 로컬 미리보기 서버를 실행해줘.
- 내가 직접 해야 하는 단계가 있으면, 왜 직접 해야 하는지 먼저 설명해줘.
```

## Codex에게 시킬 일

### 1. 실행시키기

```text
필요한 패키지를 설치하고 로컬 미리보기 서버를 실행해줘.
실행이 끝나면 브라우저에서 열 주소를 알려줘.
```

### 2. 내 정보로 바꾸기

```text
내 이름과 한 줄 소개만 내 정보로 바꿔줘.
새 라이브러리는 추가하지 말고, 수정 후 npm run build로 확인해줘.
```

### 3. 배포 전 확인하기

```text
GitHub Pages 배포 전 확인을 해줘.
astro.config.mjs의 site 값을 내 GitHub Pages 주소에 맞게 바꿔야 하는지 확인하고,
npm run build로 배포 가능한 상태인지 검증해줘.
내가 GitHub 웹사이트에서 직접 해야 하는 설정이 있으면 체크리스트로 알려줘.
```

## 직접 입력해야 할 때만 쓰는 명령

```bash
npm install
npm run dev
```

Codex가 대신 실행할 수 없는 환경에서만 위 명령어를 직접 입력합니다.
브라우저에서는 보통 아래 주소를 엽니다.

```text
http://localhost:4321
```

## 배포 전 확인

```bash
npm run build
```

오류 없이 끝나면 배포 가능한 정적 파일이 `dist` 폴더에 만들어집니다.

## GitHub Pages 주소 바꾸기

`astro.config.mjs`의 `site` 값을 본인의 GitHub Pages 주소로 바꿉니다.

```js
site: "https://your-github-username.github.io"
```

예시:

```js
site: "https://hellosunghyun.github.io"
```

## 파일 구조

```text
.
├── .github/workflows/deploy.yml
├── public/favicon.svg
├── src/pages/index.astro
├── src/styles/global.css
├── AGENTS.md
├── astro.config.mjs
├── package.json
└── tsconfig.json
```

## 참고

OpenAI의 Codex 안내에 따르면 Codex 앱은 컴퓨터의 폴더 또는 git 저장소를 프로젝트로 연결해서 작업합니다.
이 예제에서는 `sessions/01/example-homepage` 폴더 자체를 Codex 프로젝트로 여는 방식이 가장 단순합니다.

- [OpenAI Codex 시작하기](https://openai.com/codex/get-started/)
- [OpenAI Academy: How to get started with Codex](https://openai.com/academy/codex-how-to-start/)
