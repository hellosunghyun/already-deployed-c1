# 12. Navigation / 레이아웃 D-001 후보

## 목표

공통 Navigation 또는 page width 중 하나를 골라 실제 파일 범위와 링크 회귀 검증까지 포함한 D-001 후보를 만듭니다.

이 단계는 직렬 과제가 아닙니다.
[08단계](./08-selective-element.md)에서 Navigation 또는 레이아웃을 골랐을 때만 진행하고, 후보를 완성하면 [02단계](./02-plan-mode.md)에서 최종 Plan을 받습니다.

## 왜 하는가

Navigation과 공통 레이아웃은 여러 페이지에 동시에 나타납니다.
작은 간격 수정도 Home, About, Projects, Posts의 링크나 정렬을 함께 깨뜨릴 수 있으므로 실제 공통 파일과 기존 route를 먼저 알아야 합니다.

## 쉬운 설명

Navigation은 페이지를 오가는 링크 묶음이고, 공통 레이아웃은 페이지 내용이 놓이는 기본 틀입니다.

```text
Navigation을 고쳤다
→ 링크가 실제로 눌리는지 확인한다
→ 각 페이지가 올바른 주소로 열리는지 확인한다
→ desktop과 390x844에서 다시 확인한다
```

화면 모양만 좋아지고 링크 이동이 깨졌다면 완료가 아닙니다.

## 고를 수 있는 문제

아래에서 **하나만** 고릅니다.

```text
모바일 링크 간격과 누르기 쉬운 영역
Header 높이
현재 페이지 표시
본문 max-width
페이지별 본문 시작 위치
공통 section spacing
```

## 1. 실제 구조와 링크 확인

```text
현재 Astro 레포의 Navigation과 공통 레이아웃 구조를 확인해줘.

확인할 것:
1. Navigation 또는 Header Component의 실제 경로
2. 공통 Layout과 공통 style의 실제 경로
3. Navigation에 있는 모든 href
4. href가 연결되는 실제 page route
5. GitHub Pages base 경로를 고려하는 기존 방식

아직 수정하지 마.
선택한 Target 하나를 고치는 데 필요한 최소 파일만 `Allowed files 후보`로 보여줘.
href나 route 변경이 필요하다고 판단하면 이유를 별도로 설명하고 임의로 바꾸지 마.
```

## 2. D-001 후보 브리프 작성

[원하는 요소만 따오기 템플릿](../templates/selective-reference-element-brief.md)과 [레퍼런스 디자인 토큰 브리프](../templates/reference-design-token-brief.md)를 참고합니다.

```text
D-001 후보: Navigation 또는 공통 레이아웃
Where:
- URL: 확인할 실제 Local URL 목록
- Viewport: 현재 desktop, 390x844
Target: 예) 모바일 Navigation 링크 gap과 padding
Evidence: Browser 주석, screenshot 경로 또는 링크 클릭 결과
Problem: 화면에서 관찰한 문제 한 가지
Direction: 유지할 것과 바꿀 것
Constraint: 기존 href·route·base 경로 유지 등
Reference URL:
Selected element:
Bring:
Avoid:
Allowed files 후보: Codex가 실제 레포에서 확인한 경로
Link regression: 기존 Navigation 링크를 하나씩 직접 클릭
Verification: 현재 desktop, 390x844, keyboard focus, 실제 링크 이동, npm run build
```

## Codex에게 보낼 확인 프롬프트

```text
@Browser로 현재 Navigation 또는 공통 레이아웃을 확인해줘.

내 D-001 후보 브리프:
[위 브리프 붙여넣기]

아직 수정하지 말고 아래를 먼저 확인해줘.
1. 현재 desktop과 390x844에서 Problem이 실제로 보이는지
2. 선택한 Target을 만드는 실제 파일
3. 공통 파일을 바꿀 때 영향받는 페이지
4. 현재 Navigation의 모든 링크와 연결 route
5. 수정 후 직접 클릭해 회귀 검증해야 할 링크 목록

출력:
- 화면 관찰 근거
- Allowed files 후보
- 유지해야 할 href와 route
- D-001에 넣을 검증 목록
```

## 링크 회귀 검증 기준

D-001에는 아래 기준을 넣습니다.

- [ ] 기존 Navigation 링크를 실제 화면에서 하나씩 클릭한다.
- [ ] 각 링크가 의도한 route로 이동한다.
- [ ] Home으로 돌아오는 링크가 동작한다.
- [ ] 상세 페이지 링크가 Navigation에 있다면 함께 확인한다.
- [ ] keyboard `Tab`으로 각 링크에 도달할 수 있다.
- [ ] focus 표시가 보인다.
- [ ] 현재 페이지 표시를 추가했다면 다른 페이지에서도 올바르게 바뀐다.
- [ ] GitHub Pages의 base 경로가 깨지지 않는다.

## 체크박스

- [ ] Navigation 또는 page width 중 하나만 골랐다.
- [ ] 실제 공통 Component, Layout, style 경로를 확인했다.
- [ ] 기존 href와 route 목록을 확보했다.
- [ ] 공통 파일의 영향 페이지를 확인했다.
- [ ] 실제 파일 경로로 된 `Allowed files 후보`가 있다.
- [ ] 클릭과 keyboard 회귀 검증 기준을 D-001 후보에 넣었다.

## Ready Gate

아래가 모두 관찰 가능하게 정리됐을 때만 최종 Plan으로 이동합니다.

```text
Where (URL + Viewport), Target, Evidence, Problem, Direction, Constraint가 있다.
실제 관련 파일과 영향 페이지를 안다.
유지해야 할 href와 route가 있다.
수정 후 직접 클릭할 링크 목록과 keyboard focus 확인 기준이 있다.
```

## 힌트

<details>
<summary>Hint 1. 현재 페이지 표시를 어떻게 확인하나요?</summary>

Home, About, Projects, Posts를 차례로 열었을 때 현재 페이지 표시가 해당 링크로 이동하는지 봅니다.
한 페이지에서만 맞아 보이는 것으로 끝내지 않습니다.

</details>

<details>
<summary>Hint 2. href를 바꾸라는 제안이 나오면?</summary>

디자인 수정인데 href 변경이 제안됐다면 먼저 이유를 묻습니다.
현재 링크가 정상이라면 D-001의 제약에 `기존 href와 route 유지`를 적습니다.

</details>

## 퀴즈

### 질문

Navigation 간격을 바꾼 뒤 반드시 해야 하는 검증은?

- A. 스크린샷 한 장만 저장한다.
- B. 기존 링크를 직접 클릭하고 keyboard focus와 이동 route를 확인한다.
- C. href를 모두 새 주소로 바꾼다.
- D. 새 Navigation 라이브러리를 설치한다.

<details>
<summary>정답 보기</summary>

**정답: B**

</details>

## 다음 단계에서 참고할 내용

이 단계에서는 코드를 수정하거나 commit하지 않습니다.
실제 href 목록, `Allowed files 후보`, 링크 회귀 검증 목록을 후보 브리프와 함께 저장합니다.

## 다음 단계

[02. Plan mode로 최종 수정 계획 받기 →](./02-plan-mode.md)

다른 후보를 선택했다면 [11. Home hero](./11-home-hero-challenge.md) 또는 [13. Projects / Posts](./13-projects-posts-challenge.md) 중 하나만 진행합니다.
