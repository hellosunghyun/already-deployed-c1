# 16. 결과 기록과 4회차 준비

## 목표

D-001의 실제 결과를 `docs/design-backlog/D-001.md`와 `docs/design-backlog/README.md`에 함께 기록하고, 4회차 Notion DB 연결에 필요한 콘텐츠 구조를 준비합니다.

## 왜 하는가

채팅 요약만으로는 어떤 파일과 URL을 실제로 확인했는지 다음 세션에서 알기 어렵습니다.
백로그 항목과 인덱스의 상태를 함께 갱신하고 evidence 경로, commit hash, Pages URL, 검증 결과를 남겨야 같은 작업을 다시 조사하지 않습니다.

## 쉬운 설명

상태는 실제 결과에 맞게 둘 중 하나만 사용합니다.

```text
done = 필수 검증과 배포 확인까지 실제로 통과함
blocked = 실패 또는 확인 불가가 남았고 다음 행동이 필요함
```

`docs/design-backlog/D-001.md`만 바꾸고 `docs/design-backlog/README.md`의 표를 그대로 두면 서로 다른 상태가 되므로 두 파일을 함께 갱신합니다.

## 결과 기록 폼

[Before / After 기록지 템플릿](../templates/before-after-report.md)을 참고합니다.

```text
내 개인 레포 URL:
D-001의 6좌표:
- Where (실제 URL + 현재 desktop/390x844):
- Target:
- Evidence:
- Problem:
- Direction:
- Constraint:
Reference URL:
Selected element:
Bring:
Avoid:
Before 문제:
Before evidence 경로 또는 Browser 주석 handle:
After 결과:
After evidence 경로 또는 Browser 주석 handle:
Summary:
실제 변경 파일:
현재 desktop 확인: PASS / FAIL / 확인 불가
390x844 확인: PASS / FAIL / 확인 불가
keyboard focus: PASS / FAIL / 확인 불가
contrast: PASS / FAIL / 확인 불가
링크와 route: PASS / FAIL / 확인 불가
npm run build: PASS / FAIL
commit hash 또는 없음:
push한 branch 또는 없음:
배포 결정: deploy / no-deploy
GitHub Actions: PASS / FAIL / 진행 중 / 실행하지 않음
GitHub Pages 실제 URL 또는 없음:
Pages asset/link 확인: PASS / FAIL / 확인 불가
최종 Status: done / blocked
남은 문제:
다음 질문:
```

존재하지 않는 screenshot 경로나 Pages URL을 추측해서 적지 않습니다.
파일로 저장하지 않은 evidence는 `Browser 주석 handle` 또는 `로컬에서만 확인, 파일 없음`처럼 사실대로 기록합니다.

## 1단계. 백로그 갱신 미리보기

```text
3회차 D-001 결과를 백로그에 기록하고 싶어.

실제 결과:
[위 결과 기록 폼 붙여넣기]

먼저 확인할 것:
1. `docs/design-backlog/D-001.md` 현재 내용
2. `docs/design-backlog/README.md`의 D-001 행
3. 실제 git diff와 변경 파일
4. build, commit, push, Actions, Pages 확인 결과
5. before/after evidence 경로 또는 handle이 실제 기록과 일치하는지

판정 규칙:
- current desktop, 390x844, keyboard focus, contrast, 링크와 route, build, push, Actions, 실제 Pages, Pages asset/link 확인이 모두 통과하고 commit hash가 있을 때만 `done`
- 실패, 진행 중, 확인 불가, no-deploy가 남으면 `blocked`
- 값이 없는 URL, 경로, commit hash를 추측하지 마

미리 보여줄 변경:
- D-001의 Status
- Result의 Summary, before/after, 실제 변경 파일, commit hash, Pages URL
- Verification의 각 항목별 PASS / FAIL / 확인 불가
- blocked라면 실패 지점, 다음 행동, no-deploy 여부
- `docs/design-backlog/README.md` D-001 행의 같은 Status

조건:
- AGENTS.md는 수정하지 마.
- 구현 파일은 수정하지 마.
- D-002를 자동 생성하지 마.
- 아직 파일을 수정하지 말고 두 파일의 변경 문안과 Status 판정 근거만 보여줘.
```

## 2단계. 승인 후 실제 갱신

```text
좋아. 방금 보여준 문안대로 아래 두 파일만 실제로 수정해줘.

- `docs/design-backlog/D-001.md`
- `docs/design-backlog/README.md`

조건:
- 두 파일의 D-001 Status를 동일하게 유지해.
- done 또는 blocked 중 실제 검증에 맞는 상태를 사용해.
- before/after evidence 경로 또는 handle, 실제 변경 파일, commit hash, Pages URL을 사실대로 기록해.
- Verification은 항목별 PASS / FAIL / 확인 불가를 유지해.
- 실패나 확인 불가를 숨기지 마.
- AGENTS.md, 구현 파일, D-002는 수정하지 마.
- 수정 후 두 파일의 diff와 `git status --short`를 보여줘.
```

## blocked일 때 남길 내용

[막혔을 때 질문 템플릿](../templates/stuck-question-template.md)을 함께 사용합니다.

```text
Status: blocked
막힌 단계:
실패한 URL 또는 명령:
viewport:
오류 또는 화면 증거:
이미 시도한 것:
현재 git status:
commit / push / deploy 여부:
다음 한 단계:
다음 질문:
```

## 다음 세션용 요약 요청

```text
다음 세션에서 이어갈 수 있게 현재 상태를 사실 기준으로 요약해줘.

포함할 것:
1. 현재 사이트 route와 데이터 구조
2. D-001 Target과 실제 변경 파일
3. before/after evidence 경로 또는 handle
4. desktop, 390x844, keyboard, contrast, 링크 검증 결과
5. build, commit, push, Actions, Pages 상태
6. `docs/design-backlog/`의 D-001 상태
7. 남은 문제와 다음 한 단계
8. 다음에 Codex에게 보낼 프롬프트

과장하지 말고 확인하지 않은 값은 `확인하지 않음`으로 써줘.
```

## 4회차 준비: Notion DB 숙제

4회차의 목표는 Notion을 Posts 콘텐츠 관리 도구처럼 연결하는 것입니다.
이번 숙제에서는 Integration token을 만들거나 코드에 연결하지 않고, 현재 Posts 구조와 Notion DB 속성의 대응만 준비합니다.

### 1. 현재 Posts 구조 기록

```text
현재 Posts URL:
Posts page 파일:
Posts Component 파일 또는 없음:
Posts data 파일 또는 없음:
현재 field 이름:
현재 slug와 route 방식:
```

개인 레포의 실제 파일을 확인해 적고 `src/data/posts.json`이라고 추측하지 않습니다.

### 2. Notion DB 속성 준비

현재 field와 맞춰 아래를 기본 후보로 사용합니다.

| Notion 속성 | 권장 타입 | 기존 Posts field |
|---|---|---|
| Title | Title | 실제 제목 field |
| Slug | Rich text | 실제 slug field |
| Summary | Rich text | 실제 요약 field |
| Publish date | Date | 실제 날짜 field |
| Tags | Multi-select | 실제 태그 field |
| Published | Checkbox | 공개 여부를 새로 관리할 때만 사용 |

- [ ] 개인 Notion workspace에 연습용 Posts database를 준비했다.
- [ ] 실제 Posts field와 Notion 속성 대응표를 작성했다.
- [ ] 공개해도 되는 샘플 글 2~3개를 입력했다.
- [ ] 동일한 Slug가 중복되지 않는지 확인했다.
- [ ] 비공개 메모, 개인 정보, API key, token을 DB에 넣지 않았다.
- [ ] Database 페이지 URL은 개인 메모에만 보관하고 공개 레포에는 적지 않았다.

### 3. 민감정보 규칙

```text
Integration token / API key / password
→ Markdown, AGENTS.md, git diff, chat, screenshot, Notion 콘텐츠에 쓰지 않는다.

다음 세션에서 연결할 때
→ 로컬 환경 변수에 저장한다.
→ .env 파일이 .gitignore에 포함됐는지 먼저 확인한다.
→ 값 자체는 화면 공유나 결과 보고에 출력하지 않는다.
```

Integration 생성이나 database 공유 설정은 4회차 안내와 함께 진행합니다.
미리 token을 만들어 공개 메모에 보관할 필요가 없습니다.

## 체크박스

- [ ] 결과 기록 폼의 확인 가능한 값을 모두 채웠다.
- [ ] D-001과 README 인덱스의 Status가 같다.
- [ ] done 또는 blocked가 실제 검증 결과와 일치한다.
- [ ] before/after evidence 경로 또는 handle을 기록했다.
- [ ] 실제 변경 파일, commit hash, Pages URL을 사실대로 기록했다.
- [ ] Verification에 PASS / FAIL / 확인 불가가 남아 있다.
- [ ] 다음 질문을 저장했다.
- [ ] 4회차용 현재 Posts 구조와 Notion 속성 대응표를 준비했다.
- [ ] 민감정보를 레포, 채팅, screenshot, Notion 콘텐츠에 저장하지 않았다.

## Ready Gate

### done으로 마무리

- D-001과 README 인덱스가 모두 `done`입니다.
- 필수 검증, build, Actions, 실제 Pages 확인이 PASS입니다.
- evidence, commit hash, Pages URL이 기록돼 있습니다.

### blocked로 마무리

- D-001과 README 인덱스가 모두 `blocked`입니다.
- 실패 또는 확인 불가 증거와 다음 행동이 있습니다.
- 성공하지 않은 배포를 성공으로 표시하지 않았습니다.

두 경우 모두 4회차용 Posts 구조와 Notion 속성 대응표가 있으면 다음 세션을 시작할 수 있습니다.

## 힌트

<details>
<summary>Hint 1. commit hash를 모르겠다면?</summary>

추측하지 말고 15단계 결과나 `git log -1`에서 실제 값을 확인합니다.
commit하지 않았다면 `없음`이라고 기록합니다.

</details>

<details>
<summary>Hint 2. Pages가 아직 배포 중이라면?</summary>

Status를 done으로 앞당기지 않습니다.
`blocked` 또는 `진행 중이라 확인 불가`로 남기고 Actions URL과 다음 확인 시점을 적습니다.

</details>

<details>
<summary>Hint 3. Notion 속성이 현재 JSON과 다르면?</summary>

현재 사이트가 쓰는 field를 먼저 보존합니다.
4회차에는 Notion 응답을 화면에서 쓰는 기존 구조로 변환할 수 있으므로, 이번 숙제에서 코드 field를 바꾸지 않습니다.

</details>

## 퀴즈

### 질문

Actions가 성공했지만 실제 Pages URL의 CSS asset이 404입니다. D-001 상태는?

- A. commit이 있으므로 done
- B. Actions가 성공했으므로 done
- C. 실제 배포 검증이 실패했으므로 blocked
- D. URL을 기록하지 않고 done

<details>
<summary>정답 보기</summary>

**정답: C**

</details>

## 다음 단계에서 참고할 내용

2단계 승인 후 두 백로그 파일이 실제로 수정됐는지 diff로 확인합니다.
기록 변경도 GitHub에 남기려면 15단계의 preflight를 다시 사용해 **이 두 문서만** 별도의 docs commit 후보로 확인하고, 사용자 승인 후 commit/push합니다.

## 다음 단계

- `done`이면 위의 Posts 구조와 Notion 속성 대응표를 가지고 4회차를 시작합니다.
- `blocked`이면 기록한 다음 행동을 먼저 해결하고, 실제 Pages 검증 전에는 4회차 데이터 연동으로 넘어가지 않습니다.

[워크북 처음으로 돌아가기](./README.md)
