# 02. Plan mode로 최종 수정 계획 받기

## 목표

Browser baseline, 6좌표, 레퍼런스 토큰, 선택한 챌린지를 하나의 최종 수정 계획으로 묶습니다.

## 왜 하는가

화면을 보기 전에 만든 계획은 추측에 가깝습니다. 이 단계는 03~08단계의 화면·레퍼런스 증거와 11~13단계 중 선택한 챌린지가 모두 준비된 뒤 진행합니다.

최종 Plan은 09단계에서 `D-001`로 기록할 구현 계약입니다. 사용자는 수정 대상 파일, 하지 않을 일, 검증 방법을 확인한 뒤 승인합니다.

## 쉬운 설명

Plan mode는 Codex가 파일을 고치기 전에 읽고, 질문하고, 작업 순서를 제안하는 모드입니다.

```text
03~05단계: 정확한 URL, baseline, 6좌표 준비
06~08단계: 레퍼런스 요소와 디자인 토큰 준비
11 / 12 / 13단계: 실제로 실행할 챌린지 하나 선택
02단계: 모든 증거를 반영한 최종 Plan 확인
09단계: 승인한 Plan을 D-001로 기록
10단계: D-001 하나만 구현하고 검증
```

## Plan mode 시작

Codex 입력창에서 `/plan`을 사용하거나, 지원되는 앱에서 `Shift + Tab`을 눌러 Plan mode로 전환합니다.

```text
/plan
```

입력창이나 화면의 모드 표시가 Plan인지 확인합니다. 현재 앱에서 Plan mode를 지원하지 않으면 일반 채팅에서 `아직 수정하지 말고 계획만 보여줘`라고 요청해도 됩니다.

관련 예시는 [Plan mode 프롬프트 모음](../templates/plan-mode-prompts.md)을 참고합니다.

## 이 단계로 들어오기 전 확인

아래 챌린지 중 **하나만** 선택한 뒤 이 단계로 돌아옵니다.

- [11. Home hero 챌린지](./11-home-hero-challenge.md)
- [12. Navigation과 Layout 챌린지](./12-navigation-layout-challenge.md)
- [13. Projects 또는 Posts 챌린지](./13-projects-posts-challenge.md)

준비되지 않은 값이 있으면 Plan을 만들지 말고 해당 단계로 돌아갑니다.

## Codex에게 보낼 프롬프트

```text
3회차에서 실행할 디자인 수정의 최종 Plan을 세워줘.
새 프로젝트를 만들지 말고 기존 2회차 Astro 홈페이지에서 이어서 진행해.

확정한 입력:
- Where: [B-001 전체 URL + 문제가 관찰된 viewport]
- Target: [6좌표]
- Evidence: [Browser 댓글 또는 스크린샷 이름과 관찰 내용]
- Problem: [6좌표]
- Direction: [6좌표]
- Constraint: [6좌표]
- 검증할 viewport: [현재 desktop 값], 390x844
- 유지할 부분: [입력]
- Reference URL: [입력]
- Selected element: [입력]
- Bring: [입력]
- Avoid: [입력]
- Token brief: [07단계 결과]
- 선택한 챌린지: [Home / Navigation·Layout / Projects·Posts 중 하나]
- Allowed files 후보: [08단계와 챌린지 결과]
- 현재 git status: [입력]

최종 Plan에 포함할 것:
1. 화면 증거와 실제 파일 구조를 근거로 한 원인
2. D-001에서 해결할 범위 하나와 하지 않을 일
3. 실제로 읽을 파일과 수정할 파일
4. 각 파일에서 바꿀 최소 내용
5. 기존 콘텐츠, 데이터 구조, 배포 설정을 보존하는 방법
6. 새 라이브러리와 외부 font 없이 구현하는 방법
7. 같은 URL의 desktop과 390x844에서 확인할 항목
8. npm run build 검증
9. 실패하거나 예상과 다를 때 멈출 조건과 되돌릴 파일
10. docs/design-backlog/D-001.md에 옮길 항목

중요:
- 아직 파일을 수정하지 마.
- 입력에 없는 다른 화면 문제를 추가하지 마.
- 레퍼런스 전체를 복제하지 마.
- Allowed files 밖의 수정이 필요하면 이유를 설명하고 멈춰.
- 명령을 실행하지 말고 최종 Plan만 보여줘.
```

## 체크박스

좋은 최종 Plan인지 아래 기준으로 확인합니다.

- [ ] B-001과 같은 Where와 Evidence를 사용한다.
- [ ] 선택한 챌린지와 Target이 하나다.
- [ ] Token brief의 Bring과 Avoid가 반영됐다.
- [ ] 실제 파일 구조를 읽은 근거가 있다.
- [ ] Allowed files와 하지 않을 일이 명확하다.
- [ ] desktop, 390x844, build 검증이 있다.
- [ ] D-001에 옮길 내용이 빠짐없이 있다.

## 구현 모드로 전환하는 시점

최종 Plan이 나와도 바로 UI를 수정하지 않습니다.

```text
1. 최종 Plan의 Target, 변경 파일, 금지 항목, 검증 방법을 확인한다.
2. 모호한 부분을 질문하고 수정된 Plan을 다시 받는다.
3. 사용자가 최종 Plan을 승인한다.
4. /plan 또는 Shift + Tab으로 Plan mode 표시가 꺼진 구현 모드로 전환한다.
5. 09단계에서 승인한 내용만 docs/design-backlog/D-001.md로 기록한다.
6. 10단계에서 D-001 하나만 실행한다.
```

앱의 모드 이름이나 버튼 위치가 다르면 실행 전에 Codex에게 현재 모드가 파일을 수정할 수 있는 모드인지 확인합니다.

## Ready Gate

- 최종 Plan이 B-001, `Where (URL + Viewport) / Target / Evidence / Problem / Direction / Constraint`, token brief, 선택한 챌린지를 모두 반영합니다.
- 수정할 파일과 수정하지 않을 파일이 명확합니다.
- 같은 URL의 desktop, 390x844, build 검증이 포함됐습니다.
- 사용자가 최종 Plan을 승인했습니다.
- 다음 단계에서는 UI가 아니라 D-001 기록만 만든다는 것을 알고 있습니다.
- Codex가 프로젝트 파일이나 개발 설정을 수정하지 않았습니다.

## 힌트

<details>
<summary>Hint 1</summary>

Plan이 선택하지 않은 챌린지나 다른 페이지까지 포함하면 `선택한 Target 하나와 Allowed files 안으로 다시 좁혀줘`라고 요청하세요.

</details>

<details>
<summary>Hint 2</summary>

Plan mode가 보이지 않으면 일반 채팅에서 파일 수정 금지와 결과 형식을 명확히 적어 최종 계획을 받습니다. 실행 전에는 현재 모드가 파일 수정이 가능한지 다시 확인합니다.

</details>

## 퀴즈

### 질문

최종 Plan을 받은 직후 UI를 수정하지 않고 09단계로 이동하는 이유는?

- A. 승인한 범위와 검증 조건을 D-001 하나로 남기기 위해
- B. 새 라이브러리를 선택하기 위해
- C. 다른 챌린지도 모두 추가하기 위해
- D. baseline을 삭제하기 위해

<details>
<summary>정답 보기</summary>

**정답: A**

승인한 계약을 D-001로 남겨야 10단계에서 다른 범위로 번지는 것을 막고 결과도 같은 항목에 기록할 수 있습니다.

</details>

## 저장 체크포인트

현재 채팅에 승인한 최종 Plan을 남겨둡니다. 아직 프로젝트 파일 변경이 없으므로 이 단계에서는 commit하지 않습니다.

```text
승인한 Target:
승인한 Where와 Evidence:
Allowed files:
하지 않을 일:
desktop / mobile 검증:
build 검증:
사용자 승인 문장:
```

## 다음 단계

[09. 승인한 계획을 디자인 백로그로 기록 →](./09-design-backlog-folder.md)
