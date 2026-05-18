# 07. localhost에서 확인하기

## 목표

내 컴퓨터에서 홈페이지가 열리는지 확인합니다.

## 왜 하는가

배포 전에 가장 빠른 검증은 내 컴퓨터에서 먼저 보는 것입니다. 여기서 화면이 안 보이면 GitHub Pages에 올려도 성공하기 어렵습니다.

## 쉬운 설명

| 단어 | 의미 |
|---|---|
| localhost | 내 컴퓨터 안에서만 보이는 주소 |
| dev server | 개발 중 화면을 확인하기 위해 잠시 켜는 서버 |
| npm run dev | 개발 서버를 실행하는 명령어 |

## SwiftUI와 비교해서 이해하기

SwiftUI 앱을 만들 때는 Xcode Preview, Simulator, 실제 기기에서 화면을 확인합니다.

Astro 웹사이트는 브라우저에서 `localhost` 주소를 열어 확인합니다.

| SwiftUI 앱 | Astro 웹사이트 |
|---|---|
| Preview / Simulator에서 확인 | 브라우저에서 `localhost` 확인 |
| 앱 안 화면이 보임 | 웹페이지가 보임 |
| 기기 밖 친구는 바로 볼 수 없음 | `localhost`도 내 컴퓨터에서만 보임 |

둘 다 배포 전 내 컴퓨터에서 먼저 확인하는 과정입니다.

## 공통 프롬프트

```text
프로젝트를 로컬에서 확인하고 싶어.

npm run dev로 개발 서버를 실행하고,
브라우저에서 첫 화면이 보이는지 확인해줘.

확인 후 아래를 알려줘.

1. 접속 주소
2. 화면이 정상적으로 보이는지
3. 문제가 있다면 에러 원인
4. 다음 단계로 넘어가도 되는지
5. SwiftUI Preview나 Simulator와 비교했을 때 localhost가 어떤 역할인지 한 줄로 설명
```

## Codex에서 @browser / Browser 사용

Codex에서 `@browser` 또는 Browser 도구가 보이면 이렇게 요청하세요.

```text
@browser http://localhost:4321 을 열어서 화면이 정상적으로 보이는지 확인해줘.
보이는 내용과 이상한 점이 있는지 알려줘.
```

만약 `@browser`가 보이지 않으면 Safari 또는 Chrome을 열고 `http://localhost:4321`을 직접 입력하세요.

## Claude Code 사용자는

Preview / Browser 기능이 보이면 로컬 주소를 열어 확인합니다. 안 보이면 일반 브라우저로 확인하고, 화면 캡처를 Claude에게 보여줄 수 있습니다.

## Antigravity 사용자는

Browser에서 로컬 주소를 열고, screenshot artifact를 만들게 요청하세요.

## 체크박스

- [ ] `npm run dev`가 실행되었다.
- [ ] `localhost` 주소를 확인했다.
- [ ] 브라우저에서 홈페이지가 열렸다.
- [ ] 화면에 기본 페이지 또는 초안이 보인다.

## Ready Gate

다음 단계로 넘어가려면 아래가 되어 있어야 합니다.

- `localhost` 주소가 열립니다.
- 브라우저에 홈페이지 화면이 보입니다.

## 힌트

<details>
<summary>Hint 1</summary>

주소는 보통 `http://localhost:4321`입니다.

</details>

<details>
<summary>Hint 2</summary>

`localhost`는 인터넷 주소가 아닙니다. 친구에게 보내도 친구는 볼 수 없습니다.

</details>

<details>
<summary>Hint 3</summary>

화면이 안 열리면 터미널 에러를 복사해서 AI에게 질문하세요.

</details>

<details>
<summary>Hint 4</summary>

SwiftUI와 비교하면 `localhost`는 "내 컴퓨터에서만 열리는 미리보기 주소"입니다. 앱의 Preview처럼 다른 사람에게 바로 공유하는 최종 결과는 아닙니다.

</details>

## 퀴즈

### 질문

`http://localhost:4321` 주소를 친구에게 보내면 친구도 볼 수 있을까요?

A. 네
B. 아니요

<details>
<summary>정답 보기</summary>

**정답**

B

**해설**

localhost는 내 컴퓨터 안에서만 보이는 주소입니다. 친구에게 보여주려면 GitHub Pages의 `github.io` 주소가 필요합니다.

</details>

### 추가 질문

SwiftUI Preview와 `localhost`의 비슷한 점은 무엇인가요?

A. 배포 전 내 컴퓨터에서 화면을 먼저 확인한다.
B. 둘 다 App Store 심사를 통과시킨다.
C. 둘 다 GitHub 계정을 만든다.
D. 둘 다 Notion API token을 만든다.

<details>
<summary>정답 보기</summary>

**정답**

A

</details>

## 다음 단계

[08. Home 페이지 초안 만들기 →](./08-homepage-draft.md)
