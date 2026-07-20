# 07. 디자인 토큰 후보 분석하고 DESIGN.md에 저장하기

## 목표

06단계에서 남긴 요소 후보를 같은 형식의 디자인 토큰으로 비교하고, 분석 결과를 프로젝트 루트의 `DESIGN.md`에 저장합니다.

## 왜 하는가

"이 레퍼런스처럼 해줘"만으로는 Codex가 색, 간격, 테두리, 컴포넌트 구조 중 무엇을 따라야 하는지 알기 어렵습니다.
토큰으로 나누면 가져올 것과 버릴 것을 분명히 할 수 있고, `DESIGN.md`에 저장하면 이후 Plan과 구현에서 같은 기준을 다시 읽을 수 있습니다.

## 쉬운 설명

디자인 토큰은 화면의 느낌을 코드에 가까운 말로 나눈 기록입니다.

| 항목 | 이번 수업에서 보는 것 |
|---|---|
| Color | 배경, 본문, 보조 텍스트, 강조색 |
| Typography | 제목·본문 크기, 굵기, 줄 간격 |
| Spacing | 섹션 여백, gap, padding |
| Radius | 모서리 둥글기 |
| Border | 선의 두께, 색, 사용 위치 |
| Shadow | 그림자 유무와 강도 |
| Component | hero, navigation, card, list처럼 적용 단위 |

`Bring`, `Avoid`, `Allowed files`, `Verification`까지 함께 적어야 실행 범위가 닫힙니다.

## 표준 토큰 스키마

이후 `DESIGN.md`와 D-001에서도 아래 이름을 그대로 사용합니다.

```text
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
Verification:
```

## 1차 프롬프트: 후보 분석과 문안 미리 보기

```text
기존 Astro 개인 홈페이지와 아래 화면 기록, 레퍼런스를 함께 분석해줘.

현재 화면 기록:
- Where:
  - URL: [입력]
  - Viewport: [입력]
- Target: [입력]
- Evidence: [Before 스크린샷, Browser 주석 또는 관찰 기록]
- Problem: [입력]
- Direction: [입력]
- Constraint: [입력]

Reference URL: [입력]
Element candidates:
1. [후보 1]
2. [후보 2]
3. [후보 3, 없으면 삭제]

요청:
1. 각 후보를 Color, Typography, Spacing, Radius, Border, Shadow, Component로 분석해줘.
2. 각 후보마다 Bring, Avoid, Allowed files 후보, Verification을 적어줘.
3. Allowed files 후보는 실제 프로젝트 구조를 읽고 현재 존재하는 경로로 적어줘.
4. 현재 Problem을 가장 작게 해결할 후보 하나를 추천하되, 최종 선택은 하지 마.
5. 레퍼런스의 정확한 수치를 알 수 없으면 추측값이 아니라 적용 가능한 범위로 표시해줘.
6. 기존 DESIGN.md가 있으면 먼저 읽고, 유지할 규칙과 충돌할 후보를 구분해줘.
7. 프로젝트 루트 DESIGN.md에 추가하거나 갱신할 완성 문안을 보여줘.

중요:
- 레퍼런스 전체를 복제하지 마.
- 새 라이브러리, 외부 font, 무거운 animation을 제안하지 마.
- 아직 파일을 수정하지 마.
```

## `DESIGN.md`에 남길 구조

```markdown
# Design Direction

## Current reference

- Reference URL:
- Where:
  - URL:
  - Viewport:
- Target:
- Evidence:
- Problem:
- Direction:
- Constraint:
- Decision status: candidate

## Candidate A. [요소 이름]

- Color:
- Typography:
- Spacing:
- Radius:
- Border:
- Shadow:
- Component:
- Bring:
- Avoid:
- Allowed files:
- Verification:

## Candidate B. [요소 이름]

- Color:
- Typography:
- Spacing:
- Radius:
- Border:
- Shadow:
- Component:
- Bring:
- Avoid:
- Allowed files:
- Verification:

## Shared guardrails

- 기존 콘텐츠와 데이터 구조를 유지한다.
- 레퍼런스의 로고, 이미지, 브랜드 고유 그래픽을 복제하지 않는다.
- 실제 적용 요소와 Allowed files는 08단계에서 하나로 확정한다.
```

## 2차 프롬프트: 승인 후 실제 저장

미리 본 문안이 맞으면 아래 프롬프트를 보냅니다.

```text
좋아. 방금 보여준 문안을 프로젝트 루트의 DESIGN.md에 실제로 저장해줘.

조건:
- DESIGN.md가 없으면 새로 만든다.
- 이미 있으면 현재 프로젝트에 계속 필요한 규칙은 보존한다.
- 이번 후보 분석은 Current reference와 Candidate 섹션으로 정리한다.
- Color, Typography, Spacing, Radius, Border, Shadow, Component, Bring, Avoid, Allowed files, Verification 필드를 빠뜨리지 않는다.
- 아직 Candidate 상태이므로 Decision status는 candidate로 둔다.
- 구현 파일, AGENTS.md, docs/design-backlog 파일은 아직 수정하지 않는다.
- 저장 후 실제 변경한 파일과 추가한 섹션을 알려준다.
```

## 체크박스

- [ ] 모든 후보를 같은 토큰 스키마로 비교했다.
- [ ] 실제 프로젝트 구조를 기준으로 Allowed files 후보를 받았다.
- [ ] Bring과 Avoid가 분리되어 있다.
- [ ] 기존 `DESIGN.md`가 있다면 유지할 규칙을 확인했다.
- [ ] 미리 본 문안을 승인한 뒤 `DESIGN.md`에 저장했다.
- [ ] 구현 파일은 수정하지 않았다.

## Ready Gate

다음 단계로 넘어가기 전에 아래가 모두 확인되어야 합니다.

- 프로젝트 루트에 `DESIGN.md`가 실제로 있습니다.
- `DESIGN.md`에 후보별 표준 토큰 스키마가 있습니다.
- `Decision status: candidate`가 표시되어 있습니다.
- 추천 후보와 추천 이유를 설명할 수 있습니다.
- `git diff -- DESIGN.md`로 저장 내용을 확인했습니다.

## 힌트

<details>
<summary>토큰 값이 너무 구체적인 숫자로만 나오면</summary>

레퍼런스의 실제 CSS를 확인하지 않았다면 정확한 원본 숫자를 안다고 단정할 수 없습니다.
"현재 값보다 한 단계 작게" 또는 "기존 spacing 변수 범위 안에서"처럼 내 프로젝트에 적용 가능한 기준으로 다시 요청하세요.

</details>

## 퀴즈

### 질문

`DESIGN.md`에 후보 토큰을 저장하는 가장 중요한 이유는 무엇인가요?

- A. 레퍼런스 사이트를 통째로 복사하기 위해
- B. 이후 Plan과 구현이 같은 디자인 기준을 읽게 하기 위해
- C. npm 패키지를 자동으로 설치하기 위해
- D. GitHub Pages 주소를 바꾸기 위해

<details>
<summary>정답 보기</summary>

**정답: B**

`DESIGN.md`는 디자인 방향을 이어서 읽기 위한 프로젝트 문서이며, 실제 작업 항목은 이후 `docs/design-backlog/D-001.md`에 따로 둡니다.

</details>

## 다음 단계에서 참고할 내용

```text
저장 파일: DESIGN.md
Decision status: candidate
추천 후보:
아직 결정하지 않은 것: Selected element, 최종 Allowed files
```

## 관련 템플릿

- [레퍼런스 디자인 토큰 브리프](../templates/reference-design-token-brief.md)
- [레퍼런스 토큰 적용 프롬프트](../templates/reference-token-application-prompt.md)

## 다음 단계

[08. 적용할 요소와 Allowed files 하나로 확정하기 →](./08-selective-element.md)
