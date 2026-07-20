# 06. 레퍼런스 사이트 고르기

## 목표

현재 홈페이지의 문제와 가까운 레퍼런스 **1개**를 고르고, 다음 단계에서 분석할 요소 후보를 2~3개 남깁니다.

## 왜 하는가

레퍼런스가 없으면 "더 세련되게"처럼 해석이 넓은 요청을 하게 됩니다.
반대로 사이트 전체를 따라 하면 내 콘텐츠와 구조에 맞지 않는 디자인이 됩니다.
이번 단계에서는 비교 기준이 될 사이트 하나만 고르고, 아직 적용할 요소를 확정하지 않습니다.

## 쉬운 설명

| 구분 | 의미 |
|---|---|
| Reference | 방향을 비교할 사이트 1개 |
| Element candidate | 가져올지 검토할 작은 요소 후보 |
| Bring | 내 사이트에도 도움이 될 특징 |
| Avoid | 복제하지 않을 특징 |

레퍼런스는 완성본을 베끼는 대상이 아니라, **요구사항을 구체적으로 말하기 위한 재료**입니다.

## 시작 전에 확인

[05단계](./05-screenshot-comment-feedback.md)에서 작성한 아래 기록을 옆에 둡니다.

```text
Where:
- URL:
- Viewport:
Target:
Evidence:
Problem:
Direction:
Constraint:
```

## 참고할 수 있는 곳

- [getdesign.md](https://getdesign.md/)
- [Refero Styles](https://styles.refero.design/)
- [designmd.app](https://designmd.app/)
- 직접 찾은 홈페이지 URL

## 고르는 기준

```text
현재 기록한 Problem과 비교할 수 있는가?
텍스트 중심 개인 홈페이지에 적용 가능한가?
모바일에서도 무리 없는 패턴인가?
색상, 간격, 테두리처럼 작은 요소로 분해할 수 있는가?
로고나 브랜드 그래픽을 복제하지 않아도 특징을 설명할 수 있는가?
```

## 레퍼런스 비교 프롬프트

```text
아래는 내 Astro 개인 홈페이지에서 고치려는 화면 기록이야.

Where:
- URL: [입력]
- Viewport: [입력]
Target: [입력]
Evidence: [Before 스크린샷, Browser 주석 또는 관찰 기록]
Problem: [입력]
Direction: [입력]
Constraint: [입력]

검토할 Reference URL:
- [후보 URL 1]
- [후보 URL 2, 없으면 삭제]

요청:
1. 현재 Problem과 가장 가까운 레퍼런스 1개를 추천해줘.
2. 가져올 만한 요소 후보를 2~3개만 적어줘.
3. 각 후보가 현재 Problem에 어떤 도움을 주는지 한 문장으로 설명해줘.
4. 로고, 이미지, 브랜드 고유 그래픽처럼 가져오지 않을 것도 적어줘.
5. 아직 디자인 토큰을 확정하거나 파일을 수정하지 마.
```

## 레퍼런스 기록 폼

```text
Reference URL:
선택 이유:
현재 Problem과 연결되는 점:

Element candidate 1:
Element candidate 2:
Element candidate 3: [없으면 비움]

Bring 후보:
Avoid:
적용을 검토할 내 페이지:
```

## 체크박스

- [ ] 레퍼런스 URL을 1개만 골랐다.
- [ ] 05단계의 Problem과 연결되는 이유를 적었다.
- [ ] 분석할 요소 후보를 2~3개 적었다.
- [ ] 복제하지 않을 요소를 적었다.
- [ ] 아직 구현 파일을 수정하지 않았다.

## Ready Gate

다음 단계로 넘어가기 전에 아래가 모두 있어야 합니다.

- 레퍼런스 URL 1개
- 현재 Problem과 연결되는 선택 이유
- 토큰으로 비교할 요소 후보 2~3개
- `Avoid` 목록

## 힌트

<details>
<summary>좋아 보이는 사이트가 너무 많다면</summary>

가장 멋진 사이트보다 **지금 고치려는 Problem과 가장 가까운 사이트**를 고르세요.
예를 들어 카드 위계가 문제라면 화려한 랜딩 페이지보다 카드 목록이 잘 정리된 레퍼런스가 더 유용합니다.

</details>

## 퀴즈

### 질문

이번 단계에서 가장 알맞은 선택은 무엇인가요?

- A. 레퍼런스 세 곳의 전체 스타일을 모두 합친다.
- B. 레퍼런스 한 곳을 고르고 작은 요소 후보 2~3개만 남긴다.
- C. 레퍼런스의 로고와 이미지를 내려받는다.
- D. 바로 CSS 파일을 수정한다.

<details>
<summary>정답 보기</summary>

**정답: B**

07단계에서 후보를 토큰으로 비교하고, 08단계에서 실제 적용할 요소 하나를 확정합니다.

</details>

## 저장 체크포인트

레퍼런스 기록 폼을 현재 Codex 채팅이나 개인 메모에 저장합니다.
아직 프로젝트 파일에는 저장하지 않아도 됩니다.

## 관련 템플릿

- [원하는 요소만 따오기 템플릿](../templates/selective-reference-element-brief.md)
- [레퍼런스 디자인 토큰 브리프](../templates/reference-design-token-brief.md)

## 다음 단계

[07. 디자인 토큰 후보 분석하고 DESIGN.md에 저장하기 →](./07-design-token-brief.md)
