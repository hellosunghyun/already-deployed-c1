# 15. build / commit / deploy

## 목표

D-001 변경만 안전하게 commit하고 push한 뒤, GitHub Actions / Pages와 실제 배포 URL까지 확인합니다.

이 단계는 두 번의 프롬프트로 진행합니다.

```text
1단계: preflight와 commit 미리보기 — commit/push 금지
2단계: 사용자 승인 후 commit → push → Actions → Pages 실제 확인
```

## 왜 하는가

로컬 build 성공, push 성공, 배포 성공은 서로 다른 상태입니다.
또 작업 폴더에 관련 없는 변경이나 민감한 값이 섞여 있으면 그대로 commit해서는 안 됩니다.

## 쉬운 설명

```text
build = 배포용 결과를 만들 수 있는지 확인
commit = 승인한 파일만 저장점으로 기록
push = commit을 GitHub에 전송
Actions = GitHub의 배포 작업 상태
Pages = 방문자가 실제로 보는 사이트
```

14단계가 `blocked/no-deploy`라면 commit과 push를 진행하지 않고 [16단계](./16-record-result-homework.md)로 이동합니다.

## 1단계. preflight와 commit 미리보기

아래 프롬프트에서는 build까지 실행할 수 있지만 stage, commit, push는 하지 않습니다.

```text
3회차 D-001 변경을 배포하기 전에 preflight를 실행해줘.

D-001의 6좌표:
- Where (URL + Viewport):
- Target:
- Evidence:
- Problem:
- Direction:
- Constraint:

확인할 것:
1. `git status --short`와 dirty working tree 전체
2. D-001에서 예상한 변경, 문서 변경, 관련 없는 기존 변경을 분리한 목록
3. staged 파일과 아직 stage하지 않은 파일
4. `git diff --check`
5. package.json의 실제 build 명령과 `npm run build` 결과
6. dependency 또는 lockfile 변경 여부와 D-001에 필요한 변경인지
7. credential이 제거된 Git remote 이름과 저장소 URL
8. 현재 branch
9. remote 기본 branch와 GitHub Pages가 실제로 배포하는 branch 또는 workflow
10. 현재 branch를 push하면 배포가 실행되는지
11. 변경 diff에 secret, token, password, API key, 개인 정보가 의심되는 내용이 있는지
12. commit에 포함할 정확한 파일 목록과 제외할 파일 목록
13. 저장소 문체에 맞는 추천 commit 메시지 하나
14. push 후 확인할 Actions와 Pages URL

안전 규칙:
- 민감한 값의 내용은 출력하지 말고 파일 경로와 값의 종류만 알려줘.
- 관련 없는 변경은 수정하거나 되돌리지 마.
- deploy branch를 추측하지 말고 workflow, 설정 또는 remote 정보의 근거를 말해줘.
- 확인할 수 없는 항목은 `확인 불가`로 표시해.
- 아직 stage, commit, push하지 마.

마지막에 `COMMIT 가능` 또는 `중단 필요`로 판정하고 근거를 요약해줘.
```

## preflight 기록 폼

```text
D-001 Where (URL + Viewport):
D-001 Target:
D-001 Evidence:
D-001 Problem:
D-001 Direction:
D-001 Constraint:
git status:
D-001 변경 파일:
문서 변경 파일:
관련 없는 변경 파일:
staged 상태:
git diff --check:
build 명령과 결과:
dependency / lockfile:
remote:
현재 branch:
deploy branch 또는 workflow:
secret 검사:
commit 포함 파일:
commit 제외 파일:
추천 commit 메시지:
판정: COMMIT 가능 / 중단 필요
```

## 2단계. 승인 후 실제 배포

1단계 결과에서 `COMMIT 가능`이고 사용자가 포함 파일과 commit 메시지를 확인한 뒤 아래 프롬프트를 보냅니다.

```text
좋아. 방금 preflight에서 `commit 포함 파일`로 확정한 파일만 stage해서 commit하고 push해줘.

commit 메시지:
[승인한 메시지]

실행 조건:
- `git add .`로 관련 없는 파일을 함께 넣지 마.
- 승인한 정확한 파일만 stage해.
- 민감한 값이 발견되면 stage하지 말고 즉시 멈춰.
- build가 실패했거나 deploy branch가 확인되지 않았으면 commit/push하지 말고 멈춰.
- 다른 사람이 만든 관련 없는 변경은 수정하거나 되돌리지 마.
- commit 직전에 staged 파일 목록을 다시 확인해.
- commit 후 전체 commit hash를 알려줘.
- 확인한 remote와 올바른 branch로 push해.
- push 후 GitHub Actions 배포 실행이 완료될 때까지 상태를 확인해.
- Actions가 실패하면 실패한 workflow와 step을 기록하고 성공으로 보고하지 마.
- Actions가 성공하면 실제 GitHub Pages URL을 열어 최신 D-001이 반영됐는지 확인해.
- Pages에서는 Home과 D-001 수정 URL을 열고, D-001에 관련된 링크를 실제로 클릭해.
- CSS, 이미지, font 같은 asset이 base 경로 때문에 404가 되지 않는지 확인해.
- 마지막에 `git status --short`를 다시 확인해 남은 변경을 알려줘.

완료 보고 형식:
1. commit 메시지
2. 전체 commit hash
3. push한 remote와 branch
4. Actions workflow와 최종 상태
5. GitHub Pages 실제 URL
6. 확인한 페이지와 클릭한 링크
7. asset 로딩 결과
8. 최종 git status
9. 배포 판정: PASS / BLOCKED
```

## 실패 분기

| 실패 지점 | 행동 | 남길 증거 |
|---|---|---|
| 관련 없는 dirty 파일 | 해당 파일을 포함하거나 되돌리지 않고 중단 | 파일 목록과 소유 확인 질문 |
| secret 의심 | stage/commit 중단, 값을 출력하지 않음 | 파일 경로와 값의 종류 |
| build 실패 | commit/push하지 않음 | 실패 명령과 핵심 오류 로그 |
| remote 또는 deploy branch 확인 불가 | push하지 않음 | 확인한 remote/branch와 확인 불가 이유 |
| commit 실패 | push하지 않음 | commit 오류와 staged 상태 |
| push 실패 | 성공으로 보고하지 않음 | remote, branch, 오류 메시지 |
| Actions 실패 | Pages 반영으로 보고하지 않음 | workflow, 실패 step, 로그 위치 |
| Pages 미반영 또는 asset/link 오류 | 배포 완료로 표시하지 않음 | 실제 URL, 실패 경로, 화면 증거 |

실패했다면 [막혔을 때 질문 템플릿](../templates/stuck-question-template.md)에 실제 오류를 넣고 D-001을 `blocked`로 기록합니다.

## commit 메시지 예시

```text
feat: 홈 히어로 시각 위계 개선
feat: 프로젝트 카드 디자인 정리
fix: 모바일 내비게이션 간격 개선
docs: 디자인 수정 결과 기록
```

## 체크박스

- [ ] dirty working tree를 전체 확인하고 관련 변경과 무관한 변경을 분리했다.
- [ ] `git diff --check`와 `npm run build`가 성공했다.
- [ ] dependency / lockfile 변경 이유를 확인했다.
- [ ] secret 의심 값이 없는지 확인했다.
- [ ] remote, 현재 branch, deploy branch 또는 workflow를 근거와 함께 확인했다.
- [ ] 승인한 정확한 파일만 stage했다.
- [ ] commit hash와 push한 branch를 기록했다.
- [ ] GitHub Actions 최종 상태를 확인했다.
- [ ] 실제 Pages URL에서 D-001과 링크를 확인했다.
- [ ] 배포 asset이 정상 로드되는지 확인했다.

## Ready Gate

다음 두 상태 중 하나가 명확해야 합니다.

### PASS

- build, commit, push, Actions가 모두 성공했습니다.
- 전체 commit hash와 실제 Pages URL이 있습니다.
- 실제 URL에서 D-001, 관련 링크, asset을 확인했습니다.

### BLOCKED

- 중단한 단계와 이유가 정확히 기록돼 있습니다.
- 실패 로그 또는 화면 증거가 있습니다.
- 성공하지 않은 단계는 성공으로 표시하지 않았습니다.
- D-001을 `blocked`로 갱신할 문안과 다음 질문이 있습니다.

## 힌트

<details>
<summary>Hint 1. git status에 모르는 파일이 보이면?</summary>

그 파일을 지우거나 함께 commit하지 않습니다.
어떤 작업에서 생긴 파일인지 확인될 때까지 commit 포함 목록에서 제외합니다.

</details>

<details>
<summary>Hint 2. Actions가 아직 실행 중이면?</summary>

실행 중을 성공으로 기록하지 않습니다.
완료 상태가 될 때까지 확인하거나, 수업 종료 시점에는 `진행 중`과 확인 URL을 남깁니다.

</details>

<details>
<summary>Hint 3. Pages는 열리지만 CSS가 없다면?</summary>

배포 성공으로 끝내지 않습니다.
실제 깨진 asset URL과 Astro base 경로, Actions 산출물을 확인할 다음 질문을 남깁니다.

</details>

## 퀴즈

### 질문

push가 성공했지만 GitHub Actions가 실패했습니다. 올바른 기록은?

- A. push가 됐으니 배포 PASS다.
- B. Actions 실패 step과 로그 위치를 남기고 D-001을 blocked로 기록한다.
- C. 실패 기록을 지우고 다시 commit한다.
- D. Pages URL을 추측해서 적는다.

<details>
<summary>정답 보기</summary>

**정답: B**

</details>

## 저장 체크포인트

PASS면 commit hash, remote/branch, Actions 상태, 실제 Pages URL을 [Before / After 기록지](../templates/before-after-report.md)에 추가합니다.
BLOCKED면 새 commit을 억지로 만들지 않고 현재 상태와 실패 증거를 저장합니다.

## 다음 단계

[16. 결과 기록과 4회차 준비 →](./16-record-result-homework.md)
