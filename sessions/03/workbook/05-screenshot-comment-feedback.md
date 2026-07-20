# 05. 스크린샷과 Browser 주석 피드백

## 목표

B-001에서 고칠 영역을 Browser 주석 또는 스크린샷으로 정확히 표시하고, 완전한 6좌표로 수정 요구사항 후보를 만듭니다.

## 왜 하는가

`카드를 예쁘게 해줘`만으로는 어느 카드, 어느 화면 크기, 무엇을 유지해야 하는지 알 수 없습니다. 화면에 위치를 표시하고 여섯 값을 함께 주면 Codex가 다른 영역을 추측해서 고칠 가능성이 줄어듭니다.

## 쉬운 설명

6좌표는 디자인 요청의 주소입니다.

| 좌표 | 적을 내용 |
|---|---|
| Where | base 경로를 포함한 정확한 전체 URL과 viewport. 예: `[터미널에서 복사한 전체 URL] @ 390x844` |
| Target | 화면에서 선택한 구체적인 요소 하나 |
| Evidence | Browser 댓글이나 스크린샷에서 직접 확인되는 내용과 위치 |
| Problem | 현재 화면에서 관찰한 문제 |
| Direction | 어떤 방향으로 달라져야 하는지 |
| Constraint | 유지할 것과 하지 않을 일 |

## Browser 주석 남기기

1. `@Browser`로 B-001의 정확한 전체 URL을 엽니다.
2. B-001과 같은 viewport로 맞춥니다.
3. Browser의 **Annotation mode**를 켭니다.
4. 한 요소는 클릭하고, 여러 요소를 포함한 영역은 드래그해서 선택합니다.
5. 선택한 영역에 Problem, Direction, Constraint가 드러나는 댓글을 씁니다.
6. 댓글을 저장합니다.
7. Codex 채팅으로 돌아와 저장한 Browser 댓글을 검토하라고 요청합니다.

댓글 예시:

```text
Evidence: 제목, 설명, 태그가 화면에서 비슷한 굵기와 명도로 보임.
Problem: 카드 안에서 무엇을 먼저 읽어야 하는지 불분명함.
Direction: 제목 위계를 높이고 설명과 태그는 덜 강조하기.
Constraint: 현재 색상, 카드 데이터, 전체 레이아웃은 유지하기.
```

저장 후 Codex에게 보낼 프롬프트:

```text
방금 B-001 화면에 저장한 Browser 댓글을 검토해줘.

Where: [B-001 전체 URL] @ [B-001 viewport]

저장한 Browser 댓글을 아래 6좌표 순서로 다시 적어줘.
- Where
- Target
- Evidence
- Problem
- Direction
- Constraint

아직 파일을 수정하지 말고, 빠진 6좌표가 있으면 질문해줘.
```

다른 예시는 [Codex Browser 댓글 프롬프트](../templates/codex-browser-comment-prompts.md)를 참고합니다.

## Browser를 사용할 수 없을 때

일반 브라우저에서 B-001과 같은 URL과 viewport를 열고 스크린샷을 저장합니다. 가능하면 기본 마크업 도구로 Target에 사각형이나 화살표를 표시한 뒤 Codex 채팅에 첨부합니다.

[스크린샷 피드백 템플릿](../templates/screenshot-feedback-template.md)을 복사해 여섯 값을 모두 채웁니다.

```text
첨부한 스크린샷을 기준으로 봐줘.

Where: [base 경로를 포함한 B-001 전체 URL] @ [예: 390x844]
Target: [예: 첫 번째 프로젝트 카드 안의 제목·설명·태그 영역]
Evidence: [예: 첨부한 before-projects-390.png에서 제목·설명·태그의 굵기와 명도가 비슷함]
Problem: [예: 세 요소의 굵기와 명도가 비슷해 읽는 순서가 약함]
Direction: [예: 제목 위계를 높이고 설명과 태그는 덜 강조하기]
Constraint: [예: 현재 색상, 카드 데이터, 전체 레이아웃 유지. 새 라이브러리와 외부 font 추가 금지]

먼저 아래만 알려줘.
1. 네가 이해한 Target
2. 화면에서 확인되는 Problem
3. 빠졌거나 모호한 좌표
4. 원인 확인에 읽어야 할 파일 후보

아직 파일을 수정하지 말고 최소 수정 계획 후보만 말해줘.
```

## 6좌표 기록 폼

```text
Where: [정확한 전체 URL] @ [viewport]
Target:
Evidence: [Browser 댓글 또는 스크린샷 이름과 직접 확인되는 내용]
Problem:
Direction:
Constraint:

Verification: 같은 URL과 viewport에서 after 확인
```

06~08단계에서 레퍼런스를 확인한 뒤 Direction은 더 구체화할 수 있습니다. 하지만 Where (URL + Viewport), Target, Evidence, Problem은 B-001과 연결된 상태로 유지합니다.

## 체크박스

- [ ] B-001과 같은 URL과 viewport를 Where에 적었다.
- [ ] Annotation mode에서 클릭 또는 드래그로 Target을 표시했다. 또는 표시한 스크린샷을 첨부했다.
- [ ] Browser 댓글을 저장하고 Codex 채팅에서 검토를 요청했다. 또는 스크린샷 대체 프롬프트를 보냈다.
- [ ] Where (URL + Viewport), Target, Evidence, Problem, Direction, Constraint를 모두 채웠다.
- [ ] Codex가 Target을 같은 말로 이해했는지 확인했다.
- [ ] 아직 파일을 수정하지 않았다.

## Ready Gate

- Browser 댓글 또는 첨부 스크린샷에서 Target이 하나로 표시되어 있습니다.
- 6좌표에 빈칸이 없습니다.
- Problem은 관찰 가능한 문장이고 Direction과 구분됩니다.
- Constraint에 유지할 것과 금지할 일이 모두 있습니다.
- after 화면을 같은 URL과 viewport에서 검증한다고 적혀 있습니다.

## 힌트

<details>
<summary>Hint 1</summary>

Annotation mode에서 요소 하나가 선택되지 않으면 해당 영역을 드래그해 묶고, 댓글 안에 `첫 번째 카드의 제목·설명·태그 영역`처럼 글로도 적으세요.

</details>

<details>
<summary>Hint 2</summary>

Problem에는 현재 보이는 사실을, Direction에는 원하는 변화를 적습니다. `간격을 8px로 바꾸기`처럼 해결책부터 확정하지 않아도 됩니다.

</details>

<details>
<summary>Hint 3</summary>

스크린샷을 첨부했는데 Codex가 다른 곳을 가리키면 표시를 더 선명하게 하고 Target 문장을 좁힌 뒤 다시 확인합니다.

</details>

## 퀴즈

### 질문

다음 중 완전한 6좌표 요청에 가장 가까운 것은?

- A. `사이트를 예쁘게 해줘.`
- B. `/projects가 별로야.`
- C. 정확한 Where에서 첫 카드 제목을 Target으로 잡고 Evidence, Problem, Direction, Constraint를 함께 적은 요청
- D. 레퍼런스 사이트 전체를 복제해달라는 요청

<details>
<summary>정답 보기</summary>

**정답: C**

대상과 관찰, 방향, 제약을 함께 주면 수정 범위를 가장 정확히 좁힐 수 있습니다.

</details>

## 다음 단계에서 참고할 내용

완성한 `Where (URL + Viewport) / Target / Evidence / Problem / Direction / Constraint`를 현재 Codex 채팅 또는 개인 노트에 저장합니다. 09단계에서 `D-001.md`에 그대로 옮깁니다.

## 다음 단계

[06. 레퍼런스 사이트 고르기 →](./06-reference-pick.md)
