# 04. Codex Browser comments로 영역 선택하기

## 목표

Codex Browser에서 특정 요소나 영역에 주석을 달고, 그 주석을 기준으로 수정 요청을 만듭니다.

## 왜 하는가

"첫 번째 카드 아래쪽" 같은 말은 사람마다 다르게 이해할 수 있습니다.
Browser comment를 쓰면 Codex가 봐야 할 위치를 더 정확히 고정할 수 있습니다.

## Codex Browser 기본 흐름

```text
npm run dev
→ Codex Browser에서 localhost 열기
→ 고칠 영역에 comment 달기
→ comment 기준으로 수정 계획 요청
→ 승인 후 수정
→ Browser에서 다시 확인
```

## Codex에게 보낼 프롬프트

```text
@Browser http://localhost:4321 을 열어줘.

내가 Browser comment로 표시한 영역을 기준으로 디자인 문제를 봐줘.

요청:
1. comment가 붙은 요소나 영역이 어떤 페이지의 어떤 부분인지 설명해줘.
2. 가능하면 관련 CSS selector 후보를 찾아줘.
3. 이 영역에 적용된 font-size, line-height, margin, padding, gap, max-width 같은 주요 스타일을 확인해줘.
4. 문제 원인 후보를 2~3개로 정리해줘.
5. 아직 파일을 수정하지 말고, 최소 수정 계획만 제안해줘.

제약:
- 새 라이브러리 추가하지 마.
- 관련 없는 페이지는 수정하지 마.
- 기존 콘텐츠와 데이터 구조는 유지해.
- 전체 리디자인이 아니라 comment 영역 중심으로 수정해.
```

## Browser comment에 적을 문장 예시

```text
이 제목과 설명 사이의 위계를 더 분명하게 하고 싶음.
색상 전체는 유지하고 글자 크기, 굵기, 줄 간격만 조정.
모바일 390px에서도 확인 필요.
```

```text
카드 사이 간격이 답답해 보임.
카드 내부 padding은 크게 바꾸지 말고 grid gap과 border/shadow만 최소 조정.
```

```text
모바일에서 Navigation이 두 줄로 깨져 보임.
링크 간격과 header padding을 조정하되 메뉴 항목은 유지.
```

## Developer mode / CDP를 쓸 때

일반 디자인 수정은 Browser comment와 화면 확인으로 충분합니다.
아래 상황에서만 더 깊은 브라우저 디버깅을 요청합니다.

- 콘솔 오류가 화면 문제와 관련 있어 보임
- 특정 CSS가 적용되지 않는 원인을 찾아야 함
- 네트워크나 hydration 문제를 확인해야 함
- 모바일 시뮬레이션에서 렌더링 상태를 더 정확히 봐야 함

요청 예시:

```text
이 문제는 CSS 적용 여부를 더 봐야 할 것 같아.
Developer mode 또는 CDP 접근이 필요하다면, 왜 필요한지 먼저 설명하고 내가 승인하기 전에는 사용하지 마.
민감한 정보나 로그인 페이지는 열지 마.
```

## 체크박스

- [ ] Codex Browser에서 로컬 페이지를 열었다.
- [ ] 고칠 영역에 comment를 달았다.
- [ ] comment가 가리키는 target을 Codex가 설명했다.
- [ ] Codex가 원인 후보를 먼저 설명했다.
- [ ] 아직 파일을 수정하지 않았다.
- [ ] 최소 수정 계획을 받았다.

## Ready Gate

다음 단계로 넘어가기 전에 아래가 되어 있어야 합니다.

- Browser comment 또는 6좌표 피드백이 있습니다.
- Codex가 고칠 위치를 정확히 이해했습니다.
- 수정 전 계획이 있습니다.

## 다음 단계

[05. 레퍼런스를 요구사항으로 분해하기 →](./05-reference-analysis.md)
