# 14. 모바일과 접근성 확인

## 목표

D-001 수정 결과가 현재 desktop과 390x844에서 실제로 동작하는지 확인합니다.
문제가 있으면 가장 작은 수정만 적용해 같은 조건으로 다시 확인하고, 해결하지 못하면 배포하지 않은 채 `blocked`로 기록합니다.

## 왜 하는가

desktop에서 좋아 보이는 수정이 모바일에서는 가로 스크롤, 과한 줄바꿈, 사라진 focus, 끊어진 링크를 만들 수 있습니다.
또 `npm run build`가 성공해도 화면과 키보드 사용성이 정상이라는 뜻은 아닙니다.

## 쉬운 설명

이번 검증에는 필수와 권장 범위가 있습니다.

```text
필수: 지금 사용 중인 desktop 크기 + 390x844
권장: 768x1024 + 1440x900
```

현재 desktop 크기는 임의의 숫자로 바꾸지 말고 Browser에 실제로 표시되는 viewport를 기록합니다.

## 검증 전 확인

- [ ] 10단계에서 D-001 하나만 구현했다.
- [ ] 확인할 실제 Local URL을 알고 있다.
- [ ] 변경한 Target과 영향 페이지를 알고 있다.
- [ ] 개발 서버가 실행 중이다.

## 1. 필수 viewport 검증

[모바일 체크리스트 템플릿](../templates/mobile-checklist.md)을 함께 사용합니다.

```text
@Browser로 D-001을 적용한 실제 Local URL을 검증해줘.

D-001의 6좌표:
- Where (URL + Viewport):
- Target:
- Evidence:
- Problem:
- Direction:
- Constraint:

필수 viewport:
1. 현재 Browser의 desktop viewport — 실제 크기를 기록
2. 390x844

권장 viewport:
3. 768x1024
4. 1440x900

필수 확인 항목:
1. 가로 스크롤과 화면 밖 overflow가 없는지
2. 제목과 본문 줄바꿈이 읽기 어려울 정도로 깨지지 않는지
3. Navigation, CTA, 카드, 글 링크를 실제로 클릭할 수 있는지
4. 링크가 의도한 route로 이동하는지
5. keyboard Tab 순서로 interactive element에 도달할 수 있는지
6. keyboard focus 표시가 눈에 보이는지
7. 텍스트와 배경, 링크와 주변 텍스트의 대비가 읽기 어려울 정도로 낮아지지 않았는지
8. 카드 padding, gap, 본문 줄 길이가 지나치게 답답하거나 넓지 않은지
9. 공통 Component를 수정했다면 영향받는 다른 페이지가 깨지지 않았는지

아직 추가 수정하지 마.
각 항목을 PASS / FAIL / 확인 불가로 나누고 화면 근거를 적어줘.
FAIL이 있으면 원인 후보와 가장 작은 수정 계획만 제안해줘.
```

## 2. 기록 폼

```text
D-001:
Where:
- URL:
- 현재 desktop viewport:
- 390x844:
Target:
Evidence:
Problem:
Direction:
Constraint:
현재 desktop 결과: PASS / FAIL / 확인 불가
390x844 결과: PASS / FAIL / 확인 불가
768x1024 결과: PASS / FAIL / 확인하지 않음
1440x900 결과: PASS / FAIL / 확인하지 않음
overflow:
줄바꿈:
링크 클릭과 route:
keyboard Tab 순서:
focus 표시:
contrast:
공통 영역 회귀:
남은 문제:
```

## 3. 문제가 발견됐을 때

먼저 수정 범위를 승인합니다.

```text
방금 확인한 FAIL 중 D-001 범위 안에서 해결할 수 있는 최소 수정만 적용해줘.

조건:
- 방금 제안한 파일과 Target만 수정해.
- 새 라이브러리, 외부 font, animation은 추가하지 마.
- 기존 href, route, data schema는 바꾸지 마.
- D-001과 무관한 시각 개선은 하지 마.
- 수정 후 같은 실제 URL에서 현재 desktop과 390x844를 다시 확인해.
- 실패했던 링크, keyboard focus, contrast, overflow 항목도 다시 확인해.
- 결과를 PASS / FAIL / 확인 불가로 보고해.
```

수정 후에는 처음부터 범위를 넓히지 않고 **실패했던 조건을 같은 viewport에서 다시 실행**합니다.

## 4. 해결하지 못했을 때

필수 항목의 FAIL이나 확인 불가가 남았는데 수업 시간 안에 안전하게 해결할 수 없다면 배포하지 않습니다.

```text
D-001 Status: blocked
막힌 URL과 viewport:
실패 항목:
관찰한 화면 또는 오류:
시도한 최소 수정:
남은 위험:
다음 질문:
배포 여부: no-deploy
```

[막혔을 때 질문 템플릿](../templates/stuck-question-template.md)을 채우고 [16단계](./16-record-result-homework.md)에서 `blocked`로 기록합니다.

## 체크박스

- [ ] 현재 desktop viewport 크기와 결과를 기록했다.
- [ ] 390x844 결과를 기록했다.
- [ ] overflow와 줄바꿈을 확인했다.
- [ ] 관련 링크를 직접 클릭하고 route를 확인했다.
- [ ] keyboard Tab 순서와 focus 표시를 확인했다.
- [ ] 읽기 어려운 contrast 문제가 없는지 확인했다.
- [ ] 공통 파일을 수정했다면 영향 페이지를 다시 확인했다.
- [ ] FAIL이 있었다면 최소 수정 후 같은 조건을 재검증했다.

## Ready Gate

다음 두 상태 중 하나가 명확해야 합니다.

### PASS: 15단계로 이동

- 현재 desktop과 390x844 필수 항목이 모두 PASS입니다.
- 링크와 route 회귀가 없습니다.
- keyboard focus와 읽기 쉬운 contrast가 유지됩니다.

### BLOCKED: 배포하지 않고 16단계로 이동

- 남은 FAIL 또는 확인 불가 항목이 정확히 기록돼 있습니다.
- D-001을 `blocked`로 표시할 문안이 있습니다.
- `no-deploy` 결정과 다음 질문이 있습니다.

## 힌트

<details>
<summary>Hint 1. 가로 스크롤 원인을 찾기 어렵다면?</summary>

고정 width, 긴 URL·문장, 큰 padding, viewport보다 넓은 이미지부터 확인합니다.
원인을 찾기 전 전체 CSS를 다시 쓰지 않습니다.

</details>

<details>
<summary>Hint 2. Browser에서 keyboard 검증이 어렵다면?</summary>

사용자가 실제 페이지를 열고 `Tab`을 반복해서 눌러 순서와 focus 표시를 직접 확인합니다.
하지 못했다면 PASS로 추측하지 말고 `확인 불가`로 기록합니다.

</details>

<details>
<summary>Hint 3. 권장 viewport까지 시간이 없다면?</summary>

현재 desktop과 390x844는 생략하지 않습니다.
768x1024와 1440x900은 `확인하지 않음`으로 정확히 남깁니다.

</details>

## 퀴즈

### 질문

390x844에서 가로 스크롤이 남았지만 build는 성공했습니다. 다음 행동은?

- A. build가 성공했으므로 바로 배포한다.
- B. 최소 수정 후 같은 viewport에서 재검증하거나, 해결하지 못하면 blocked/no-deploy로 기록한다.
- C. 문제를 기록하지 않고 desktop만 확인한다.
- D. 전체 CSS를 새 프레임워크로 바꾼다.

<details>
<summary>정답 보기</summary>

**정답: B**

</details>

## 저장 체크포인트

commit 전 검증 기록을 [Before / After 기록지](../templates/before-after-report.md)에 남깁니다.
PASS면 15단계로 이동하고, BLOCKED면 commit/push 없이 16단계로 이동합니다.

## 다음 단계

- PASS: [15. build / commit / deploy →](./15-build-deploy.md)
- BLOCKED: [16. 결과 기록과 4회차 준비 →](./16-record-result-homework.md)
