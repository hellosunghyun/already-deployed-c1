# 03. Browser 설치와 연결 확인

## 목표

Codex 데스크톱 앱에서 Browser를 설치하고, 01단계에서 기록한 정확한 Local URL을 Codex와 함께 볼 수 있는지 확인합니다.

## 왜 하는가

Codex가 화면을 직접 보지 못하면 파일 이름과 CSS만 보고 디자인 문제를 추측할 수 있습니다. 먼저 Browser 연결을 확인해야 다음 단계의 화면 기록과 주석이 같은 대상을 가리킵니다.

Browser는 모든 Codex 환경에서 제공되는 기능이 아닙니다. 현재 환경에서 사용할 수 없더라도 일반 브라우저와 스크린샷으로 같은 학습 목표를 달성할 수 있습니다.

## 쉬운 설명

- **Browser 플러그인**: Codex 데스크톱 앱 안에서 웹 화면을 함께 열고 확인하는 기능입니다.
- **`@Browser`**: 채팅에서 Browser를 호출하는 공식 태그입니다.
- **fallback**: Browser를 사용할 수 없을 때 일반 브라우저 스크린샷으로 진행하는 대체 경로입니다.

Codex CLI나 IDE에서 작업 중이라면 Browser 태그 대신 Codex 데스크톱 앱을 사용합니다. 데스크톱 앱에서도 Browser가 보이지 않으면 스크린샷 대체 경로를 사용합니다.

## Browser 설치와 설정

1. Codex 데스크톱 앱을 엽니다.
2. 플러그인 디렉터리에서 **Browser**를 찾아 설치합니다.
3. 설정의 통합 또는 Browser 항목에서 기능을 켭니다.
4. 채팅 입력창에서 `@Browser`가 자동완성되는지 확인합니다.

오늘 수업의 기본 설정은 아래와 같습니다.

```text
브라우저: 켬
주석 스크린샷: 항상 포함
승인: 나 대신 승인
```

참고 화면: [Browser 설정 스크린샷](../assets/codex-browser-settings.png)

`나 대신 승인`을 사용해도 비밀번호·token·secret 입력, 결제, 삭제, commit·push는 자동 실행 범위에 넣지 않습니다. 해당 작업은 워크북의 별도 사용자 승인 Gate를 따릅니다.

앱 버전에 따라 메뉴 문구나 위치가 다를 수 있습니다. `@Browser`가 자동완성되고 Local URL을 열 수 있으면 준비된 상태입니다.

## 정확한 Local URL로 연결 테스트

`http://localhost:4321/`을 새로 입력하지 말고 01단계에서 터미널이 출력한 값을 그대로 붙여넣습니다.

```text
@Browser [01단계에서 기록한 정확한 Local URL]을 열어줘.

아래만 확인해줘.
1. 페이지가 실제로 보이는지
2. 현재 전체 URL과 viewport
3. 페이지의 첫 번째 제목 문구
4. 로딩 오류나 빈 화면이 있는지

아직 파일을 수정하지 마.
```

복사 프롬프트는 [Codex Browser 프롬프트 모음](../templates/codex-browser-comment-prompts.md)에서도 확인할 수 있습니다.

## Browser를 사용할 수 없을 때

일반 브라우저에서 01단계의 정확한 Local URL을 엽니다.

1. 전체 URL이 보이도록 주소창을 확인합니다.
2. 화면 크기를 기록합니다.
3. 페이지 스크린샷을 저장합니다.
4. Codex 채팅에 스크린샷을 첨부합니다.
5. Browser 대신 스크린샷 경로를 사용한다고 알립니다.

```text
현재 환경에서는 @Browser를 사용할 수 없어 일반 브라우저 스크린샷으로 진행할게.

첨부한 화면의 정보:
- 정확한 URL: [입력]
- Viewport: [입력]
- 촬영 시각: [입력]

페이지가 보이는지와 첫 번째 제목 문구만 확인해줘.
아직 파일을 수정하지 마.
```

## 체크박스

- [ ] Codex 데스크톱 앱에서 Browser 설치 또는 지원 여부를 확인했다.
- [ ] Browser를 쓸 수 있다면 `@Browser`가 자동완성된다.
- [ ] 승인 기본값을 `나 대신 승인`으로 설정했다.
- [ ] 01단계에서 기록한 정확한 Local URL을 사용했다.
- [ ] Browser 또는 일반 브라우저 스크린샷 중 진행 경로를 정했다.
- [ ] Codex가 보이는 화면의 URL과 첫 제목을 설명했다.

## Ready Gate

- 경로 1: `@Browser`로 정확한 Local URL의 화면이 열립니다.
- 경로 2: 일반 브라우저에서 같은 URL을 열고 스크린샷을 Codex에 첨부했습니다.
- 두 경로 모두 현재 URL과 viewport를 기록했습니다.
- 아직 프로젝트 파일을 수정하지 않았습니다.

## 힌트

<details>
<summary>Hint 1</summary>

`@Browser`가 자동완성되지 않으면 한글 태그를 추측하지 말고 플러그인 설치와 현재 환경의 지원 여부를 먼저 확인하세요.

</details>

<details>
<summary>Hint 2</summary>

404가 보이면 서버를 다시 만들지 마세요. 01단계에서 기록한 base 경로가 URL에 포함됐는지 확인합니다.

</details>

<details>
<summary>Hint 3</summary>

Browser 설치가 수업 시간 안에 해결되지 않으면 즉시 스크린샷 경로로 전환하세요. 이후 단계의 6좌표와 검증 절차는 동일합니다.

</details>

## 퀴즈

### 질문

`@Browser http://localhost:4321/`에서 404가 보일 때 가장 먼저 확인할 것은?

- A. 새 Astro 프로젝트 생성
- B. 터미널이 출력한 실제 포트와 base 경로
- C. 외부 UI 라이브러리 설치
- D. Git 기록 삭제

<details>
<summary>정답 보기</summary>

**정답: B**

로컬 서버의 포트와 base 경로는 프로젝트 설정과 실행 상태에 따라 달라질 수 있습니다.

</details>

## 저장 체크포인트

```text
화면 확인 경로: @Browser / 일반 브라우저+스크린샷
정확한 Local URL:
Viewport:
페이지 첫 제목:
오류 또는 없음:
```

## 다음 단계

[04. 현재 화면 baseline 기록 →](./04-visual-baseline.md)
