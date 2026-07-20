# 11. Home hero D-001 후보

## 목표

Home 첫 화면에서 고칠 대상 하나를 화면 증거와 실제 파일 경로로 좁혀 D-001 후보를 만듭니다.

이 단계는 10단계 뒤에 추가로 실행하는 과제가 아닙니다.
[08단계](./08-selective-element.md)에서 Home hero를 골랐을 때만 진행하고, 후보를 완성하면 [02단계](./02-plan-mode.md)에서 최종 Plan을 받습니다.

## 왜 하는가

`Home을 예쁘게 해줘`라는 요청은 범위가 너무 큽니다.
제목, 소개 문장, CTA, 여백 중 하나를 고르고 실제 수정 파일 후보까지 확인해야 Codex가 관련 없는 영역을 건드리지 않습니다.

## 쉬운 설명

Hero는 Home에 들어왔을 때 처음 보이는 큰 영역입니다.
이 단계에서는 아직 코드를 고치지 않고 아래 네 가지를 확정합니다.

```text
어느 URL인가
어느 요소인가
화면에서 무엇이 문제인가
어느 파일이 관련돼 있는가
```

## 고를 수 있는 문제

아래에서 **하나만** 고릅니다.

```text
제목 크기 또는 줄바꿈
제목과 소개 문장의 간격
소개 문장의 줄 길이
CTA 링크의 시각 위계
Hero 전체의 위아래 여백
```

## 1. 실제 파일 범위 확인

개인 레포마다 Home과 공통 스타일의 위치가 다를 수 있습니다.
파일명을 추측해서 `Allowed files`에 넣지 말고 Codex가 먼저 확인하게 합니다.

```text
현재 Astro 레포에서 Home hero가 만들어지는 실제 파일을 확인해줘.

확인할 것:
1. `/` route를 만드는 page 파일
2. Hero가 별도 Component라면 그 파일
3. Hero에 적용되는 기존 style 파일 또는 style block
4. 공통 Layout 파일이 Hero 모양에 실제로 영향을 주는지

아직 수정하지 마.
Home hero의 선택한 요소 하나를 고치는 데 필요한 최소 파일만 `Allowed files 후보`로 보여줘.
공통 파일은 다른 페이지에 미칠 영향도 함께 설명해줘.
```

## 2. D-001 후보 브리프 작성

[원하는 요소만 따오기 템플릿](../templates/selective-reference-element-brief.md)과 [레퍼런스 디자인 토큰 브리프](../templates/reference-design-token-brief.md)를 참고합니다.

```text
D-001 후보: Home hero
Where:
- URL: 터미널에 출력된 실제 Home URL
- Viewport: 현재 desktop, 390x844
Target: 예) Hero 제목과 소개 문장 사이 간격
Evidence: Browser 주석, screenshot 경로 또는 화면에서 관찰한 문구
Problem: 화면에서 관찰한 문제 한 가지
Direction: 유지할 것과 바꿀 것
Constraint: 기존 콘텐츠·링크 유지, 새 라이브러리 추가 금지 등
Reference URL:
Selected element:
Bring:
Avoid:
Allowed files 후보: Codex가 실제 레포에서 확인한 경로
Verification: 현재 desktop, 390x844, npm run build
```

## Codex에게 보낼 확인 프롬프트

```text
@Browser로 Home의 실제 Local URL을 확인해줘.
Target은 내가 적은 Home hero 요소 하나야.

내 D-001 후보 브리프:
[위 브리프 붙여넣기]

확인할 것:
- 현재 desktop에서 Problem이 실제로 보이는지
- 390x844에서 같은 문제가 보이는지
- 유지해야 할 색상, 콘텐츠, 링크가 무엇인지
- Allowed files 후보가 실제 Target과 연결되는지

아직 수정하지 마.
관찰한 화면 근거와 D-001에 넣을 문안만 보여줘.
```

## 체크박스

- [ ] Home의 실제 Local URL을 기록했다.
- [ ] Hero에서 고칠 요소를 하나만 골랐다.
- [ ] 현재 desktop과 390x844에서 문제를 확인했다.
- [ ] 레퍼런스에서 가져올 것과 가져오지 않을 것을 분리했다.
- [ ] 실제 레포를 확인한 `Allowed files 후보`가 있다.
- [ ] 색상, 콘텐츠, 링크처럼 유지할 요소를 적었다.

## Ready Gate

아래 문장을 구체적으로 채울 수 있을 때만 최종 Plan으로 이동합니다.

```text
Where는 [실제 URL + viewport]이고 Target은 [정확한 요소]다.
[Evidence]에서 [Problem]이 관찰된다.
[Selected element]만 참고해 [Direction]으로 고치고 [Constraint]를 지킨다.
수정 후보는 [실제 파일 경로]이고 [현재 desktop, 390x844, build]로 확인한다.
```

## 힌트

<details>
<summary>Hint 1. 제목이 몇 줄이면 과한가요?</summary>

줄 수만 정답으로 정하지 않습니다.
390x844에서 제목이 소개 문장과 CTA를 과도하게 아래로 밀어내는지 함께 봅니다.

</details>

<details>
<summary>Hint 2. 공통 style 파일만 나온다면?</summary>

공통 파일을 수정할 수는 있지만 다른 페이지 회귀 위험을 D-001에 적습니다.
가능하다면 Hero에 한정되는 기존 selector 또는 Component 범위를 우선합니다.

</details>

## 퀴즈

### 질문

Home hero 후보를 정할 때 가장 먼저 해야 할 일은?

- A. 새 CSS 라이브러리를 설치한다.
- B. 제목, 문장, CTA, 여백을 한 번에 전부 바꾼다.
- C. 화면에서 문제 하나를 고르고 실제 관련 파일을 확인한다.
- D. 레퍼런스의 색상을 모두 복사한다.

<details>
<summary>정답 보기</summary>

**정답: C**

</details>

## 다음 단계에서 참고할 내용

이 단계에서는 commit하지 않습니다.
채팅 또는 개인 메모에 D-001 후보 브리프와 `Allowed files 후보`를 남긴 뒤, 02단계 최종 Plan과 09단계 실제 백로그에 사용합니다.

## 다음 단계

[02. Plan mode로 최종 수정 계획 받기 →](./02-plan-mode.md)

다른 후보를 선택했다면 [12. Navigation / 레이아웃](./12-navigation-layout-challenge.md) 또는 [13. Projects / Posts](./13-projects-posts-challenge.md) 중 하나만 진행합니다.
