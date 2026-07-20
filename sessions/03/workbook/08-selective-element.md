# 08. 적용할 요소와 Allowed files 하나로 확정하기

## 목표

`DESIGN.md`의 후보 중 실제로 적용할 요소 **1개**를 고르고, 수정해도 되는 파일을 실제 프로젝트 구조 기준으로 확정합니다.

## 왜 하는가

후보가 여러 개 남아 있거나 수정 파일 범위가 열려 있으면 작은 디자인 개선이 전체 페이지 리뉴얼로 커질 수 있습니다.
이번 단계에서 `Selected element`, `Target`, `Allowed files`를 각각 하나의 닫힌 계약으로 만들면 이후 Plan과 D-001이 같은 범위를 가리킵니다.

## 쉬운 설명

| 항목 | 답해야 하는 질문 |
|---|---|
| Selected element | 레퍼런스에서 정확히 무엇을 가져오는가? |
| Apply to | 내 홈페이지의 어느 페이지·영역에 적용하는가? |
| Allowed files | Codex가 수정해도 되는 실제 파일은 무엇인가? |
| Verification | 적용 성공을 어떤 화면과 명령으로 확인하는가? |

`Allowed files`에는 추측 경로가 아니라, Codex가 현재 프로젝트에서 확인한 실제 경로만 적습니다.

## 선택할 수 있는 요소 예시

```text
Hero title scale
Navigation spacing
Project card framing
Posts list density
Color role
Section spacing rhythm
```

## 가져오지 않는 것

```text
레퍼런스 전체 색상과 레이아웃 복제
로고, 이미지, 브랜드 고유 그래픽 복제
무거운 animation 추가
외부 font 무단 추가
새 UI 라이브러리 설치
선택한 Target과 관련 없는 파일 정리
```

## 범위 확정 프롬프트

```text
프로젝트 루트의 DESIGN.md와 현재 Astro 프로젝트 구조를 읽어줘.

현재 화면 기록:
- Where:
  - URL: [입력]
  - Viewport: [입력]
- Target: [입력]
- Evidence: [Before 스크린샷, Browser 주석 또는 관찰 기록]
- Problem: [입력]
- Direction: [입력]
- Constraint: [입력]

DESIGN.md의 Candidate 중 오늘 적용할 요소 후보: [입력]

요청:
1. 현재 Problem을 가장 작게 해결할 Selected element 하나만 확정해줘.
2. Apply to를 페이지와 화면 영역 단위로 좁혀줘.
3. 실제 프로젝트 파일을 읽고 Allowed files를 필요한 파일만 적어줘.
4. 관련 컴포넌트가 따로 있으면 페이지 파일 대신 실제 컴포넌트 경로를 포함해줘.
5. 각 Allowed file이 필요한 이유를 한 문장씩 적어줘.
6. desktop 현재 viewport, 390x844, npm run build를 포함해 Verification을 정리해줘.
7. 아래 선택 브리프 형식으로 답해줘.

중요:
- 아직 DESIGN.md나 구현 파일을 수정하지 마.
- 관련 없는 리팩터링이나 파일 이동을 제안하지 마.
- Allowed files 밖의 수정이 꼭 필요하다면 임의로 넓히지 말고 이유와 함께 멈춰줘.
```

## 선택 브리프

```text
Reference URL:
Selected element:
Apply to:
선택 이유:

Where:
- URL:
- Viewport:
Target:
Evidence:
Problem:
Direction:
Constraint:

Color:
Typography:
Spacing:
Radius:
Border:
Shadow:
Component:

Bring:
Avoid:
Allowed files:
- [실제 경로]: [필요한 이유]

Verification:
- desktop [현재 viewport]
- 390x844
- npm run build
```

## 챌린지 하나 선택하기

이제 아래에서 **한 가지만** 엽니다. 세 챌린지를 차례로 모두 진행하지 않습니다.

| 선택 | 맞는 경우 | 이동 |
|---|---|---|
| Home hero | 첫 화면 제목·소개·CTA 위계를 고칠 때 | [11. Home hero 챌린지](./11-home-hero-challenge.md) |
| Navigation / 레이아웃 | 공통 메뉴·본문 폭·섹션 간격을 고칠 때 | [12. Navigation / 레이아웃 챌린지](./12-navigation-layout-challenge.md) |
| Projects / Posts | 카드나 글 목록의 반복 위계를 고칠 때 | [13. Projects / Posts 챌린지](./13-projects-posts-challenge.md) |

선택한 챌린지에서 화면 증거를 보완한 뒤 [02. 최종 Plan 확정](./02-plan-mode.md)으로 돌아갑니다.
02단계에서 최신 Plan을 확정한 다음 09단계로 진행합니다.

## 체크박스

- [ ] `DESIGN.md`의 후보 중 하나만 골랐다.
- [ ] Where (URL + Viewport), Target, Evidence, Problem, Direction, Constraint가 모두 채워졌다.
- [ ] Selected element와 Apply to가 한 영역으로 좁혀졌다.
- [ ] Allowed files가 현재 존재하는 실제 경로인지 확인했다.
- [ ] 각 Allowed file이 필요한 이유가 있다.
- [ ] Verification에 desktop, 390x844, build가 있다.
- [ ] 11/12/13 중 한 챌린지만 선택했다.
- [ ] 아직 프로젝트 파일을 수정하지 않았다.

## Ready Gate

선택한 챌린지로 이동하기 전에 아래를 한 문장으로 말할 수 있어야 합니다.

> `[Where]`의 `[Target]`에서 `[Evidence]`로 확인한 `[Problem]`을 `[Direction]`으로 고치되 `[Constraint]`를 지키고, `[Selected element]`와 `[Allowed files]`만 사용해 `[Verification]`으로 확인한다.

이 문장이 길거나 `그리고`가 여러 번 들어가면 범위를 한 번 더 줄입니다.

## 힌트

<details>
<summary>Allowed files를 고르기 어렵다면</summary>

Codex에게 Target을 렌더링하는 페이지와 컴포넌트의 정의 위치를 먼저 찾아달라고 하세요.
예제 경로를 그대로 복사하지 말고, 현재 레포에서 실제로 존재하는 경로인지 확인해야 합니다.

</details>

## 퀴즈

### 질문

Project 카드가 별도 `ProjectCard.astro` 컴포넌트에 있는데 예시 문서에는 `projects.astro`만 적혀 있다면 어떻게 해야 하나요?

- A. 예시를 그대로 사용한다.
- B. 전체 `src` 폴더를 Allowed files로 적는다.
- C. 실제 정의 위치를 확인해 필요한 컴포넌트 경로로 범위를 바로잡는다.
- D. 새 컴포넌트를 하나 더 만든다.

<details>
<summary>정답 보기</summary>

**정답: C**

Allowed files는 예시가 아니라 현재 프로젝트의 실제 구조를 기준으로 정합니다.

</details>

## 저장 체크포인트

선택 브리프 전체를 현재 채팅에 남깁니다.
선택한 챌린지를 마친 뒤에도 이 브리프를 유지하고, 02단계의 최종 Plan 입력으로 사용합니다.

```text
선택한 챌린지: 11 / 12 / 13
Selected element:
Allowed files:
다음 복귀 단계: 02
```

## 관련 템플릿

- [원하는 요소만 따오기 템플릿](../templates/selective-reference-element-brief.md)
- [레퍼런스 디자인 토큰 브리프](../templates/reference-design-token-brief.md)
- [레퍼런스 토큰 적용 프롬프트](../templates/reference-token-application-prompt.md)

## 다음 단계

선택 브리프의 Target에 맞는 챌린지 **하나만** 진행합니다.

- [11. Home hero 후보](./11-home-hero-challenge.md)
- [12. Navigation / 레이아웃 후보](./12-navigation-layout-challenge.md)
- [13. Projects 또는 Posts 후보](./13-projects-posts-challenge.md)

후보를 구체화한 뒤 [02. Plan mode로 최종 수정 계획 받기](./02-plan-mode.md)로 돌아옵니다.
