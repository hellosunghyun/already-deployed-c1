# 13. Projects 또는 Posts D-001 후보

## 목표

Projects 카드 또는 Posts 목록 중 하나만 골라 데이터 구조를 보존하는 D-001 후보를 만듭니다.

이 단계는 직렬 과제가 아닙니다.
[08단계](./08-selective-element.md)에서 Projects 또는 Posts를 골랐을 때만 진행하고, 둘 중 **한 페이지·한 Target만** 선택합니다.
후보를 완성하면 [02단계](./02-plan-mode.md)에서 최종 Plan을 받습니다.

## 왜 하는가

2회차에서는 화면 코드와 콘텐츠 데이터를 나눴습니다.
예를 들어 Projects는 `ProjectCard` 같은 Component와 `projects.json` 같은 데이터 파일을 사용할 수 있습니다.
개인 레포의 실제 구조를 확인하지 않고 페이지 파일만 `Allowed files`로 고정하면, 필요한 Component를 놓치거나 디자인 수정 때문에 데이터 구조까지 바꿀 수 있습니다.

## 쉬운 설명

반복 목록은 보통 세 부분으로 나뉩니다.

```text
page = 목록을 배치하는 곳
Component = 카드나 행의 모양
data = 제목, 설명, slug 같은 내용
```

이번 목표는 모양을 고치는 것입니다.
데이터 내용이나 JSON 구조를 바꿀 이유가 없다면 그대로 유지합니다.

## 고를 수 있는 Target

아래에서 **하나만** 고릅니다.

### Projects

```text
카드 제목·설명·태그의 위계
카드 사이 gap
카드 border·radius·padding
자세히 보기 링크의 시각 위계
390x844 카드 폭
```

### Posts

```text
제목과 날짜의 위계
요약의 줄 길이
태그 밀도
목록 행 간격
390x844에서 메타데이터 배치
```

## 1. 실제 파일과 데이터 흐름 확인

```text
현재 Astro 레포에서 Projects와 Posts의 실제 구조를 확인해줘.

Projects에서 확인할 것:
1. `/projects` page 파일
2. ProjectCard 같은 카드 Component가 있는지와 실제 경로
3. `projects.json` 같은 데이터 파일이 있는지와 실제 경로
4. title, description, role, tools, result, detail, slug 중 실제로 쓰는 필드
5. 카드 또는 자세히 보기 링크가 slug와 route를 만드는 방식

Posts에서 확인할 것:
1. `/posts` page 파일
2. Post 목록 Component가 있는지와 실제 경로
3. posts 데이터 파일이 있는지와 실제 경로
4. 제목, 날짜, 요약, 태그, slug 중 실제로 쓰는 필드
5. 글 링크가 route를 만드는 방식

아직 수정하지 마.
내가 선택한 페이지와 Target 하나에 필요한 최소 파일만 `Allowed files 후보`로 보여줘.
시각 수정에 데이터 파일 변경이 필요 없다면 데이터 파일을 Allowed files에서 제외해줘.
구조가 없거나 2회차 작업이 미완료라면 새 구조를 추측하지 말고 현재 상태와 막힌 지점을 알려줘.
```

## 2. D-001 후보 브리프 작성

[원하는 요소만 따오기 템플릿](../templates/selective-reference-element-brief.md)과 [레퍼런스 디자인 토큰 브리프](../templates/reference-design-token-brief.md)를 참고합니다.

```text
D-001 후보: Projects 또는 Posts 중 하나
Where:
- URL: 터미널에 출력된 실제 페이지 URL
- Viewport: 현재 desktop, 390x844
Target: 예) ProjectCard 제목·설명·태그 위계
Evidence: Browser 주석, screenshot 경로 또는 링크 클릭 결과
Problem: 화면에서 관찰한 문제 한 가지
Direction: 유지할 것과 바꿀 것
Constraint: 기존 data field·slug·route 유지 등
Reference URL:
Selected element:
Bring:
Avoid:
현재 page 파일:
현재 Component 파일 또는 없음:
현재 data 파일 또는 없음:
유지할 data field와 slug/route:
Allowed files 후보: Codex가 실제 레포에서 확인한 최소 경로
Verification: 현재 desktop, 390x844, 카드/글 링크 직접 클릭, npm run build
```

## Codex에게 보낼 확인 프롬프트

```text
@Browser로 내가 선택한 Projects 또는 Posts의 실제 Local URL을 확인해줘.

내 D-001 후보 브리프:
[위 브리프 붙여넣기]

아직 수정하지 말고 아래를 확인해줘.
1. 현재 desktop과 390x844에서 Problem이 실제로 보이는지
2. page, Component, data가 현재 어떻게 연결되는지
3. 시각 수정에 필요한 최소 파일
4. 유지해야 할 JSON field, slug, href, route
5. 수정 후 직접 클릭해 확인할 카드 또는 글 링크

출력:
- 화면 관찰 근거
- 실제 구조 요약
- Allowed files 후보
- 데이터와 링크를 보존하는 제약
- D-001에 넣을 검증 목록
```

## 구조가 없을 때

`ProjectCard`, 데이터 파일, 목록 route가 실제로 없다면 디자인 수정으로 숨기지 않습니다.

```text
현재 구조에서 찾지 못한 것:
화면에 보이는 현재 방식:
2회차에서 먼저 완료해야 할 항목:
지금 남길 수 있는 D-001 후보:
```

구조 미완료가 선택한 Target을 막는다면 아직 D-001 상태를 만들지 않습니다. 현재 blocker와 다음 행동을 기록한 뒤 2회차 구조를 복구하거나 다른 챌린지 하나를 선택합니다. 이후에도 이 후보를 D-001로 확정한다면 09단계에서 `planned`로 만들고, 10단계에서 `doing`으로 전환한 뒤 실제 차단이 확인될 때만 `blocked`로 기록합니다.

## 체크박스

- [ ] Projects 또는 Posts 중 하나만 골랐다.
- [ ] 그 페이지 안에서도 Target을 하나만 골랐다.
- [ ] 실제 page, Component, data 경로를 확인했다.
- [ ] 유지할 data field와 slug/route를 기록했다.
- [ ] 디자인 수정에 불필요한 data 파일은 Allowed files에서 제외했다.
- [ ] 카드 또는 글 링크를 직접 클릭하는 검증 기준이 있다.

## Ready Gate

아래가 모두 정리됐을 때만 최종 Plan으로 이동합니다.

```text
선택한 페이지와 Target이 각각 하나다.
Where (URL + Viewport), Target, Evidence, Problem, Direction, Constraint가 있다.
실제 page / Component / data 구조를 안다.
Allowed files 후보가 실제 경로로 적혀 있다.
보존할 data field와 slug/route가 있다.
desktop, 390x844, 링크 클릭, build 검증 기준이 있다.
```

## 힌트

<details>
<summary>Hint 1. ProjectCard가 별도 파일이라면?</summary>

카드 모양을 만드는 Component가 실제 수정 후보일 가능성이 큽니다.
`projects.astro`와 style 파일만 고정하지 말고 현재 import 관계를 확인합니다.

</details>

<details>
<summary>Hint 2. JSON도 같이 고쳐야 하나요?</summary>

문제가 문구나 누락 데이터가 아니라 시각 위계라면 보통 JSON 구조 변경은 필요하지 않습니다.
필요성이 확인되지 않았다면 `기존 데이터 구조 유지`를 제약에 적습니다.

</details>

## 퀴즈

### 질문

Projects 카드의 시각 위계를 고칠 때 가장 안전한 파일 범위 선택은?

- A. 무조건 `projects.astro`와 전역 CSS만 수정한다.
- B. 레포를 확인해 page, ProjectCard, style, data 연결을 파악한 뒤 필요한 최소 파일만 고른다.
- C. JSON field 이름을 모두 바꾼다.
- D. Projects와 Posts를 동시에 다시 만든다.

<details>
<summary>정답 보기</summary>

**정답: B**

</details>

## 다음 단계에서 참고할 내용

이 단계에서는 코드를 수정하거나 commit하지 않습니다.
현재 page·Component·data 경로, 보존할 schema, `Allowed files 후보`를 후보 브리프와 함께 저장합니다.

## 다음 단계

[02. Plan mode로 최종 수정 계획 받기 →](./02-plan-mode.md)

다른 후보를 선택했다면 [11. Home hero](./11-home-hero-challenge.md) 또는 [12. Navigation / 레이아웃](./12-navigation-layout-challenge.md) 중 하나만 진행합니다.
