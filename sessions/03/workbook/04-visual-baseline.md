# 04. 현재 화면 baseline 기록

## 목표

수정할 후보 화면의 **수정 전 상태**를 Where와 Evidence로 기록하고, 2회차 숙제의 관찰이 지금도 유효한지 확인합니다.

## 왜 하는가

수정 전 화면이 없으면 바뀐 결과가 실제 개선인지 비교할 수 없습니다. URL이나 viewport가 다르면 같은 화면처럼 보여도 공정한 before/after 비교가 아닙니다.

## 쉬운 설명

**baseline**은 수정 전 기준 화면입니다. 정확한 URL과 viewport를 묶어 **Where**라고 부르고, 그 상태를 보여주는 Browser 화면이나 스크린샷을 **Evidence**라고 부릅니다.

```text
같은 Where = 같은 URL + 같은 viewport
+ 해당 화면의 Evidence
= 비교 가능한 before / after
```

화면 문제는 `예쁘지 않다`가 아니라 직접 확인할 수 있는 말로 기록합니다.

```text
관찰 가능: 390x844에서 제목이 세 줄이 되고 Navigation과 겹친다.
관찰 어려움: 뭔가 별로다.
```

## 2회차 숙제와 현재 화면 연결

01단계에서 회수한 숙제를 현재 화면과 비교합니다.

```text
2회차 스크린샷 위치:
고치고 싶었던 부분 3개:
모바일 문제 1개:
유지하고 싶은 부분 1개:
현재도 보이는 문제:
이미 달라진 항목:
```

숙제의 문제를 그대로 믿지 않고, 현재 Local URL에서 다시 보이는 것만 후보로 남깁니다.

## 확인할 URL과 viewport

01단계에서 기록한 **전체 URL**만 사용합니다. 없는 페이지를 이 단계에서 새로 만들지 않습니다.

```text
Home 전체 URL:
About 전체 URL 또는 없음:
Projects 전체 URL 또는 없음:
Posts 전체 URL 또는 없음:

필수 viewport:
- 현재 desktop viewport: [Browser에 표시된 실제 값]
- 모바일 viewport: 390x844
```

## Codex에게 보낼 프롬프트

Browser 경로:

```text
@Browser로 아래의 실제 Local URL을 확인해줘.

Home: [01단계 기록]
About: [01단계 기록 또는 없음]
Projects: [01단계 기록 또는 없음]
Posts: [01단계 기록 또는 없음]

2회차 숙제에서 기록한 내용:
- 고치고 싶었던 부분: [입력]
- 모바일 문제: [입력]
- 유지하고 싶은 부분: [입력]

먼저 현재 desktop viewport와 390x844에서 확인해줘.
숙제의 문제 중 지금도 화면에서 관찰되는 것만 남기고, 새로 관찰한 문제와 구분해줘.

각 후보에는 아래를 적어줘.
- Where: 정확한 전체 URL + 정확한 viewport
- Target
- Evidence: Browser 화면 또는 스크린샷에서 직접 확인되는 내용과 위치
- 화면에서 관찰한 사실
- 유지해야 할 부분

아직 문제를 해결하거나 파일을 수정하지 마.
오늘 수정할 Target도 아직 확정하지 마.
```

일반 브라우저 경로에서는 같은 URL과 viewport로 스크린샷을 찍어 첨부한 뒤 위 프롬프트에서 첫 문장만 아래처럼 바꿉니다.

```text
첨부한 일반 브라우저 스크린샷을 기준으로 확인해줘.
```

## baseline 기록 폼

후보마다 하나씩 작성합니다.

```text
Baseline ID:
Where: [정확한 전체 URL] @ [viewport]
Target:
Evidence: [Browser 화면 또는 스크린샷 이름과 직접 확인되는 내용]
관찰한 문제:
유지할 부분:
2회차 숙제와의 관계: 동일 / 달라짐 / 새로 발견
```

최종 before/after에 사용할 하나의 후보에는 `Baseline ID: B-001`을 붙입니다. 이후 피드백·레퍼런스·챌린지·Plan·백로그 단계에서 방향이 달라지더라도 기존 B-001을 지우지 말고 새 후보를 추가합니다.

최종 기록에는 [before/after 보고서 템플릿](../templates/before-after-report.md)을 참고할 수 있습니다.

## 체크박스

- [ ] 2회차 숙제의 스크린샷, 문제, 유지할 부분을 현재 화면과 대조했다.
- [ ] 터미널 기준의 정확한 전체 URL과 viewport를 Where로 묶어 기록했다.
- [ ] 현재 desktop viewport와 390x844에서 각각 확인했다.
- [ ] 문제를 관찰 가능한 문장으로 썼다.
- [ ] 유지할 부분도 함께 기록했다.
- [ ] B-001 Evidence가 있다.
- [ ] 아직 코드를 수정하지 않았다.

## Ready Gate

- B-001에 정확한 Where가 있습니다.
- 수정 전 Browser 화면 또는 스크린샷 Evidence가 있습니다.
- 문제와 유지할 부분이 각각 한 문장 이상 있습니다.
- 이후 after 화면을 같은 URL과 viewport에서 다시 확인할 수 있습니다.

## 힌트

<details>
<summary>Hint 1</summary>

viewport 숫자를 알 수 없다면 Browser에게 현재 viewport를 물어보거나 일반 브라우저 개발자 도구의 크기 표시를 기록하세요.

</details>

<details>
<summary>Hint 2</summary>

2회차 숙제의 스크린샷과 현재 화면이 다르면 현재 화면을 기준으로 새 baseline을 남깁니다. 예전 스크린샷을 삭제할 필요는 없습니다.

</details>

<details>
<summary>Hint 3</summary>

문제를 여러 개 발견해도 지금 모두 고르지 않습니다. 05단계의 주석과 06~08단계의 레퍼런스를 거친 뒤 D-001 하나로 좁힙니다.

</details>

## 퀴즈

### 질문

수정 전후를 비교하기 위한 가장 정확한 조합은?

- A. 서로 다른 페이지와 서로 다른 화면 크기
- B. 같은 URL과 같은 viewport
- C. 배포 URL과 기억에 남은 느낌
- D. CSS 파일 이름과 commit 메시지

<details>
<summary>정답 보기</summary>

**정답: B**

같은 조건에서 확인해야 변경의 효과를 구분할 수 있습니다.

</details>

## 다음 단계에서 참고할 내용

B-001의 Where (URL + Viewport), Target, Evidence, 관찰한 문제를 현재 채팅이나 개인 노트에 저장합니다. 이 단계에서는 프로젝트 파일을 commit하지 않습니다.

## 다음 단계

[05. 스크린샷과 Browser 주석 피드백 →](./05-screenshot-comment-feedback.md)
