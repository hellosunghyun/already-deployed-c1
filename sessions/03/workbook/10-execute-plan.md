# 10. D-001 계약 확인하고 실행하기

## 목표

02단계의 최신 Plan과 `docs/design-backlog/D-001.md`가 같은 작업을 가리키는지 확인하고, 구현 모드에서 D-001 하나만 실행합니다.

## 왜 하는가

화면 증거와 선택 요소가 정해진 뒤에도 오래된 Plan을 실행하면 다른 파일이나 영역을 고칠 수 있습니다.
실행 직전에 Plan과 D-001의 6좌표·Allowed files·Verification을 맞춰 보고, 구현 중 상태와 실제 결과를 같은 파일에 기록해야 다음 사람이 무엇이 끝났는지 알 수 있습니다.

## 쉬운 설명

```text
02단계 최신 Plan
        ↕ 같은 범위인지 확인
docs/design-backlog/D-001.md
        ↓
구현 모드로 전환
        ↓
planned → doing
        ↓
Allowed files만 수정
        ↓
desktop before/after + 390x844 + build
        ↓
doing 유지 또는 blocked + 중간 결과 기록
```

이 단계에서는 새 Plan을 만들지 않습니다.
둘이 다르면 실행하지 말고 [02단계](./02-plan-mode.md)에서 Plan을 다시 확정한 뒤 [09단계](./09-design-backlog-folder.md)에서 D-001을 맞춥니다.

## 1. Plan과 D-001 정합성 확인

```text
02단계에서 확정한 최신 Plan과 아래 파일을 비교해줘.

- DESIGN.md
- AGENTS.md
- docs/design-backlog/D-001.md

아래 항목을 표로 비교해줘.
1. Where (URL + Viewport)
2. Target
3. Evidence
4. Problem
5. Direction
6. Constraint
7. Selected element와 token brief
8. Allowed files
9. 구현 순서와 Verification

판정 규칙:
- 모두 같으면 `실행 가능`이라고 말해줘.
- 하나라도 다르면 `실행 보류`라고 말하고 차이만 알려줘.
- 아직 파일을 수정하거나 새 Plan을 만들지 마.
```

`실행 보류`가 나오면 이 단계에서 자연어로 범위를 고쳐서 진행하지 않습니다.
02단계와 09단계로 돌아가 Plan과 계약 파일을 다시 일치시킵니다.

## 2. 구현 모드 확인

Codex의 Plan mode는 `/plan` 또는 `Shift+Tab`으로 전환할 수 있습니다.
현재 Plan mode 표시가 켜져 있다면 같은 방법으로 Plan mode를 끄고 구현 모드로 돌아옵니다.

```text
/plan
```

또는 `Shift+Tab`을 누릅니다.

화면에서 Plan mode 표시가 사라진 것을 확인한 뒤 아래처럼 묻습니다.

```text
지금 파일을 수정할 수 있는 구현 모드인지 한 문장으로 확인해줘.
아직 수정은 시작하지 마.
```

## 3. 실행 전 Before 증거 저장

```text
Browser 또는 현재 화면 스크린샷으로 D-001의 URL과 Target을 열어줘.

실행 전 할 일:
- D-001에 적힌 desktop viewport에서 Before 화면을 저장해줘.
- 저장한 스크린샷 또는 Browser 주석의 위치를 알려줘.
- 현재 화면이 D-001의 Problem을 재현하는지 확인해줘.
- 재현되지 않으면 수정하지 말고 멈춰줘.
```

## 4. D-001 실행 프롬프트

Plan과 D-001이 일치하고 Before 문제도 재현되면 아래 프롬프트를 보냅니다.

```text
좋아. 02단계에서 승인한 최신 Plan과 docs/design-backlog/D-001.md 계약대로 D-001 하나만 실행해줘.

실행 순서:
1. docs/design-backlog/D-001.md와 docs/design-backlog/README.md의 Status를 planned에서 doing으로 바꿔.
2. 수정 전 예상 변경 파일이 D-001의 Allowed files와 같은지 확인해.
3. Allowed files 안에서 승인된 Plan 순서대로 구현해.
4. Allowed files 밖의 수정이 필요하면 범위를 넓히지 말고 이유와 필요한 파일을 알려준 뒤 멈춰.
5. desktop의 같은 URL·viewport에서 After 화면을 확인하고 Before와 비교해.
6. 390x844에서 제목 줄바꿈, 가로 스크롤, 간격, Target의 위계를 확인해.
7. npm run build를 실행해.
8. D-001의 Result에 아래를 실제 결과로 기록해.
   - Summary
   - Actual changed files와 각 파일의 변경 이유
   - Desktop before/after 증거 위치와 판정
   - 390x844 검증 결과
   - build 명령과 성공 또는 실패 로그
   - Remaining issue
9. 이 단계의 local 검증이 모두 통과하면 D-001과 README 인덱스의 Status를 doing으로 유지하고, 14단계로 이동한다고 기록해.
10. 구현이나 local 검증이 막혀 다음 단계로 진행할 수 없으면 Status를 blocked로 바꾸고 이유와 다음 행동을 기록해.

금지:
- D-002 이후 항목을 만들거나 실행하지 마.
- 새 프로젝트를 만들지 마.
- 새 라이브러리, 외부 font, 무거운 animation을 추가하지 마.
- 관련 없는 리팩터링, 파일 이동, 데이터 구조 변경을 하지 마.
- AGENTS.md나 DESIGN.md에 D-001 결과 로그를 복사하지 마.
```

## 완료 보고 형식

```text
D-001 Status: doing / blocked
실제 변경 파일:
- [경로]: [변경 이유]

Desktop Before:
Desktop After:
Desktop 판정:
390x844 판정:
Build 명령:
Build 결과:
Remaining issue:
D-001 Result 갱신: 완료 / 미완료
README 인덱스 갱신: 완료 / 미완료
```

## 실행 중 멈춰야 할 때

```text
잠깐 멈춰.
추가 수정은 하지 말고 아래만 알려줘.

1. 현재 D-001 Status
2. 지금까지 실제로 수정한 파일
3. 마지막으로 통과한 검증
4. 막힌 이유
5. 되돌리거나 이어서 해야 할 다음 한 단계

docs/design-backlog/D-001.md의 Result에 현재 상태를 기록해줘.
```

## 체크박스

- [ ] 02단계 Plan과 D-001의 6좌표를 비교했다.
- [ ] Selected element, token brief, Allowed files, 구현 순서, Verification도 비교했다.
- [ ] 판정이 `실행 가능`이었다.
- [ ] Plan mode 표시가 꺼진 구현 모드임을 확인했다.
- [ ] desktop Before 증거를 저장하고 Problem을 재현했다.
- [ ] 구현 시작 시 D-001과 README 인덱스를 `doing`으로 바꿨다.
- [ ] 실제 변경 파일이 모두 Allowed files 안에 있다.
- [ ] desktop Before/After를 같은 URL·viewport로 비교했다.
- [ ] 390x844를 확인했다.
- [ ] `npm run build` 결과가 있다.
- [ ] D-001 Result에 실제 변경 파일과 검증 결과를 기록했다.
- [ ] 이 단계의 Status가 `doing` 또는 이유가 적힌 `blocked`다.

## Ready Gate

다음 단계로 넘어가려면 아래 중 하나를 충족해야 합니다.

### 다음 검증으로 진행하는 경로

- D-001과 README 인덱스가 `doing`입니다.
- Actual changed files가 비어 있지 않고 모두 Allowed files 안에 있습니다.
- 같은 desktop viewport의 Before/After 증거가 있습니다.
- 390x844와 build가 모두 통과했습니다.

### 중단 경로

- D-001과 README 인덱스가 `blocked`입니다.
- 실패 로그, 현재 화면, 다음 행동이 Result에 기록되어 있습니다.
- 해결되지 않은 상태를 `done`으로 표시하지 않았습니다.

`doing`이면 14단계로 진행하고, `blocked`면 이 단계에서 추가 범위 승인을 받기 전까지 멈춥니다. 최종 `done` 판정은 15단계의 실제 배포 확인 뒤 16단계에서 기록합니다.

## 힌트

<details>
<summary>Plan과 D-001의 파일 목록이 다르면</summary>

더 넓은 목록을 임의로 선택하지 마세요.
현재 코드 구조와 Target을 다시 확인한 뒤 02단계에서 Plan을 확정하고, 09단계에서 D-001의 Allowed files와 Approved plan을 같은 내용으로 갱신합니다.

</details>

## 퀴즈

### 질문

구현 중 Allowed files 밖의 파일을 수정해야 한다는 사실을 발견하면 어떻게 해야 하나요?

- A. 작은 변경이므로 바로 수정한다.
- B. `src` 전체를 Allowed files로 바꾼다.
- C. 이유와 필요한 파일을 알리고 멈춘 뒤 범위 승인을 받는다.
- D. D-001을 done으로 표시하고 나중에 고친다.

<details>
<summary>정답 보기</summary>

**정답: C**

D-001은 수정 범위 계약입니다. 필요한 범위가 달라지면 Plan과 계약을 먼저 다시 맞춰야 합니다.

</details>

## 다음 단계에서 참고할 내용

```text
D-001 Status:
Before 증거 위치:
After 증거 위치:
Actual changed files:
Desktop 판정:
390x844 판정:
Build 결과:
Remaining issue:
```

이 기록이 `docs/design-backlog/D-001.md`의 Result와 같은지 확인합니다.

## 관련 템플릿

- [Plan mode 프롬프트 모음](../templates/plan-mode-prompts.md)
- [레퍼런스 토큰 적용 프롬프트](../templates/reference-token-application-prompt.md)
- [Before / After 기록지](../templates/before-after-report.md)

## 다음 단계

[14. 모바일 최종 확인 →](./14-mobile-check.md)
