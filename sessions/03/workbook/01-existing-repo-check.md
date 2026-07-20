# 01. 기존 레포와 Codex 채팅 확인

## 목표

2회차 결과와 숙제를 회수하고, 디자인 작업을 시작해도 되는 프로젝트 상태와 정확한 Local URL을 확보합니다.

## 왜 하는가

참가자마다 2회차 완성도와 로컬 폴더 상태가 다릅니다. 잘못된 폴더나 기존 변경사항이 남은 상태에서 디자인 수정을 시작하면 다른 작업을 덮어쓸 수 있습니다.

`http://localhost:4321/`도 항상 맞는 주소가 아닙니다. 포트가 달라지거나 GitHub Pages용 base 경로가 붙을 수 있으므로 터미널이 실제로 출력한 URL을 기록해야 합니다.

## 쉬운 설명

오늘은 세 가지 출발 경로가 있습니다.

| 경로 | 현재 상태 | 3회차 진행 방법 |
|---|---|---|
| A. 완주 | Home / About / Projects / Posts와 build 결과가 있음 | 기존 레포와 가능하면 기존 채팅에서 바로 시작 |
| B. 부분 완주 | 기존 레포에서 한 개 이상의 페이지가 로컬로 열림 | 열리는 페이지 하나만 D-001 Target으로 선택하고 미완료 항목은 별도 기록 |
| C. 복구 | 2회차 레포가 없거나 실행 가능한 페이지가 없음 | 제공된 [2회차 완료 예제](../../02/example-homepage/)를 개인 폴더에 복사해 시작 |

경로 C에서는 [`sessions/02/example-homepage`](../../02/example-homepage/) 원본을 직접 수정하지 않습니다. Finder의 복제 기능이나 안전한 복사 명령으로 개인 실습 폴더에 복사한 뒤, **복사본**을 Codex 프로젝트로 엽니다. 기존 개인 폴더를 덮어쓰거나 삭제하지 않습니다.

```text
나는 2회차를 완료하지 못해서 제공된 완료 예제로 3회차를 시작하려고 해.

원본 예제:
sessions/02/example-homepage

안전 규칙:
- 원본 예제 폴더는 수정하지 마.
- 내 기존 프로젝트를 덮어쓰거나 삭제하지 마.
- 먼저 복사할 개인 폴더의 정확한 경로와 복사 방법을 제안해줘.
- 내가 승인하면 복사만 하고, 복사본의 package.json과 git 상태를 확인해줘.
- 새 Astro 프로젝트를 생성하지 마.
```

## 경로 C의 Git 기준점 만들기

완료 예제 복사본은 소스 파일만 담고 있어 독립된 Git 레포가 아닙니다. 복사 직후 `git status`가 실패하는 것은 정상이며, 이 상태로는 15단계의 commit·push·Pages 배포를 완료할 수 없습니다.

디자인을 수정하기 전에 아래 중 하나를 선택합니다.

- **배포까지 진행:** 빈 GitHub 저장소를 준비하고 복사본을 새 Git 레포로 연결한 뒤, 수정 전 예제 상태를 baseline commit으로 먼저 push합니다.
- **로컬만 진행:** 14단계까지 실습하고, 15~16단계에서는 remote·push·Actions·Pages를 `not run`, 최종 상태를 `blocked`로 기록합니다.

GitHub 저장소가 없다면 [1회차 GitHub 저장소 만들기](../../01/workbook/10-create-github-repo.md)를 먼저 진행합니다. 이미 같은 이름의 저장소나 remote가 있으면 덮어쓰거나 삭제하지 않습니다.

먼저 아래 프롬프트로 **계획만** 확인합니다.

```text
2회차 완료 예제의 개인 복사본을 3회차용 Git 기준점으로 준비하려고 해.

먼저 읽기 전용으로 확인해줘.
1. 현재 폴더와 package.json
2. git 레포인지 여부
3. 기존 remote와 branch가 있는지
4. 연결할 빈 GitHub 저장소 URL
5. astro.config.mjs의 site와 base가 그 저장소 주소에 맞는지
6. .github/workflows/deploy.yml의 배포 branch

그다음 아래 순서의 실행 계획과 정확한 예상 변경만 보여줘.
- 필요할 때만 현재 복사본에서 Git 초기화
- 기본 branch를 main으로 준비
- 기존 remote가 없을 때만 승인한 GitHub 저장소를 origin으로 연결
- 승인한 Pages 주소에 맞춰 site와 base 확인
- npm ci와 npm run build
- 수정 전 예제 상태만 baseline commit 후보로 제시
- 사용자 승인 후에만 commit과 첫 push

안전 규칙:
- 원본 sessions/02/example-homepage는 수정하지 마.
- 기존 폴더, Git 기록, remote를 삭제하거나 덮어쓰지 마.
- remote 저장소가 비어 있지 않으면 멈춰서 알려줘.
- 아직 git init, 파일 수정, stage, commit, push를 실행하지 마.
```

계획과 대상 URL을 확인한 뒤 승인합니다. baseline push가 끝나면 [1회차 GitHub에 코드 올리기](../../01/workbook/11-push-to-github.md)와 [GitHub Pages 배포](../../01/workbook/12-deploy-github-pages.md)의 Ready Gate를 기준으로 실제 GitHub 파일과 Pages 설정을 확인합니다.

계획을 승인했다면 아래 프롬프트로 **개인 복사본의 Git 설정과 baseline 후보 확인까지만** 실행합니다.

```text
좋아. 방금 확인한 계획대로 원본이 아닌 개인 복사본만 Git 기준점으로 준비해줘.

승인한 값:
- 개인 복사본 절대 경로: [입력]
- 비어 있는 GitHub 저장소 URL: [입력]
- Pages 유형: 사용자 사이트 / 프로젝트 사이트
- 승인한 site와 base: [입력]

실행 순서:
1. 현재 경로가 개인 복사본과 정확히 같은지 다시 확인해.
2. Git 레포가 아니면 `git init -b main`으로 초기화해. 이미 레포라면 새로 초기화하지 마.
3. 기존 remote가 없을 때만 승인한 URL을 `origin`으로 추가해. 다른 remote가 있으면 수정하지 말고 멈춰.
4. `git ls-remote --heads origin`으로 원격 branch를 확인해. 원격이 비어 있지 않거나 확인에 실패하면 멈춰.
5. 승인한 값과 다를 때만 astro.config.mjs의 site와 base를 수정해.
6. npm ci와 npm run build를 실행해.
7. git status, branch, remote, baseline commit 후보 파일, 민감정보 검사 결과를 보여줘.

아직 stage, commit, push는 하지 마.
원본 예제와 기존 폴더·Git 기록·remote를 삭제하거나 덮어쓰지 마.
```

출력된 후보 파일과 build 결과를 확인한 뒤 baseline commit과 첫 push를 별도로 승인합니다.

```text
방금 보여준 개인 복사본의 baseline 후보 파일만 승인해.

다시 확인할 것:
- 현재 경로가 승인한 개인 복사본인지
- origin이 승인한 빈 GitHub 저장소인지
- branch가 main인지
- node_modules, dist, .astro, secret, token, password가 포함되지 않는지
- npm run build가 성공했는지

모두 맞으면 승인한 후보 파일만 stage하고
`chore: 2회차 완료 예제 기준점 추가`로 commit한 뒤 origin main에 첫 push해줘.
하나라도 다르면 stage·commit·push하지 말고 멈춰.

완료 후 아래를 실제 값으로 알려줘.
- git status --short --branch
- origin URL
- commit hash와 메시지
- push한 branch
- GitHub 저장소 URL
- Actions 실행 URL 또는 확인 위치
- Pages 설정에서 Source를 GitHub Actions로 확인할 위치
```

GitHub 저장소에서 baseline 파일과 첫 push를 확인한 뒤에만 3회차 디자인 수정을 시작합니다.

## 2회차 숙제 회수

[2회차 결과 기록과 다음 숙제](../../02/workbook/11-record-result-homework.md)에서 준비한 값을 옮깁니다. 준비하지 못한 항목은 `없음`이라고 적고 현재 화면에서 다시 확인합니다.

```text
2회차 결과 요약 또는 기존 채팅:
현재 홈페이지 스크린샷 1장:
레퍼런스 링크 2~5개:
고치고 싶은 부분 3개:
모바일에서 이상한 부분 1개:
유지하고 싶은 부분 1개:
마지막 build 결과 또는 실패 로그:
```

## 시작 정보 기록

```text
내 개인 레포 URL:
GitHub Pages URL 또는 없음:
로컬 프로젝트 폴더:
Codex 프로젝트에 연결된 폴더:
기존 Codex 채팅 또는 없음:
현재 branch:
2회차에서 만든 페이지: /, /about, /projects, /posts
AGENTS.md 위치 또는 없음:
오늘 출발 경로: A / B / C
```

## Codex에게 보낼 점검 프롬프트

```text
3회차 디자인 수정 작업을 시작하려고 해.
새 프로젝트를 만들지 말고, 현재 Codex에 열린 기존 2회차 Astro 개인 홈페이지 레포에서 이어서 진행해줘.

먼저 아래 상태를 읽기 전용 명령으로 확인해줘.
1. 현재 작업 폴더와 package.json 위치
2. package.json의 scripts와 사용 중인 패키지 매니저
3. src/pages 구조와 /, /about, /projects, /posts 존재 여부
4. astro.config.mjs의 site와 base 설정
5. AGENTS.md 위치와 적용 범위
6. 현재 branch, 마지막 commit, git status
7. 기존 변경사항과 새로 생성된 파일의 의미
8. 의존성이 설치되어 있는지

안전 규칙:
- 아직 프로젝트 파일을 수정하지 마.
- 삭제, reset, checkout, clean, stash를 실행하지 마.
- git status에 내가 설명할 수 없는 변경이 있으면 즉시 멈춰.
- 먼저 확인 명령과 위험 요소를 설명해줘.
- 내가 승인하면 읽기 전용 확인만 실행해줘.

확인 후 아래를 알려줘.
- 출발 경로 A / B / C
- 디자인 작업을 시작해도 되는지
- 먼저 복구하거나 저장해야 하는 항목
- 로컬 실행에 사용할 명령
```

## 기존 변경사항이 있을 때 중단 조건

`git status`에 내가 만들지 않았거나 설명할 수 없는 변경이 하나라도 있으면 디자인 작업을 시작하지 않습니다.

```text
지금은 수정하지 마.
git status에 나온 각 변경이 어떤 파일인지 설명해줘.
내 작업을 지우는 reset, checkout, clean, stash는 실행하지 마.
안전한 저장 또는 분리 방법만 제안해줘.
```

내가 의도한 변경이라도 현재 상태를 기록하고, commit할지 그대로 유지할지 결정한 뒤 다음으로 넘어갑니다.

## 의존성 복구와 개발 서버 실행

`astro: command not found`처럼 패키지가 없다는 오류가 나오면 아래 순서로 복구합니다.

1. `package-lock.json`이 있으면 `npm ci`를 사용합니다.
2. `package-lock.json`이 없고 npm 프로젝트라면 `npm install`을 사용합니다.
3. 다른 패키지 매니저의 lock 파일이 있으면 임의로 npm으로 바꾸지 말고 기존 도구를 사용합니다.
4. 설치가 끝나면 `npm run dev`를 실행합니다.
5. 터미널의 `Local` 줄에 출력된 URL을 그대로 복사합니다.

승인 후 Codex에게 보낼 프롬프트:

```text
좋아. 기존 lock 파일과 package.json을 기준으로 의존성만 복구해줘.

규칙:
- package-lock.json이 있으면 npm ci를 사용해.
- package-lock.json이 없고 npm 프로젝트면 npm install을 사용해.
- 패키지 매니저나 lock 파일을 임의로 바꾸지 마.
- 새 라이브러리를 추가하지 마.
- 설치 뒤 npm run dev를 실행해.
- 터미널이 출력한 Local URL, 포트, base 경로를 정확히 알려줘.
- 오류가 나면 숨기지 말고 마지막 오류와 다음 확인 한 단계만 알려줘.
```

개발 서버는 03~05단계를 진행하는 동안 종료하지 않습니다.

## 정확한 URL 기록

하드코딩한 `localhost:4321` 대신 실제 출력과 설정을 기준으로 적습니다.

```text
터미널이 출력한 Local URL:
포트:
base 경로 또는 없음:
Home 전체 URL:
About 전체 URL 또는 없음:
Projects 전체 URL 또는 없음:
Posts 전체 URL 또는 없음:
```

## 체크박스

- [ ] 출발 경로 A / B / C를 정했다.
- [ ] 2회차 숙제와 마지막 build 결과를 회수했다.
- [ ] 현재 폴더, branch, 마지막 commit을 확인했다.
- [ ] 경로 C라면 Git 레포·remote·branch를 준비하고 수정 전 baseline commit을 확인했거나, 로컬 전용 `blocked` 경로를 선택했다.
- [ ] `git status`의 모든 변경을 내가 설명할 수 있다.
- [ ] `AGENTS.md`, package manager, lock 파일을 확인했다.
- [ ] 필요한 경우 기존 lock 파일에 맞춰 의존성을 복구했다.
- [ ] `npm run dev`가 실행 중이다.
- [ ] 터미널이 출력한 정확한 Local URL과 base 경로를 기록했다.

## Ready Gate

- 경로 A 또는 B이며, 선택할 수 있는 기존 페이지가 하나 이상 로컬에서 열립니다.
- 경로 C라면 2회차 완료 예제를 개인 폴더에 복사했고 원본은 수정하지 않았습니다.
- 경로 C에서 배포까지 진행한다면 복사본의 Git 레포, `main` branch, 승인한 `origin`, 수정 전 baseline commit이 준비됐습니다. 로컬 전용이면 15~16단계가 `blocked`라는 것을 기록했습니다.
- 설명할 수 없는 기존 변경사항이 없습니다.
- 개발 서버가 실행 중이고 정확한 Local URL을 알고 있습니다.
- 아직 디자인 파일을 수정하지 않았습니다.

## 힌트

<details>
<summary>Hint 1</summary>

`package.json`이 보이지 않으면 프로젝트 루트가 아닐 가능성이 큽니다. 폴더를 새로 만들지 말고 기존 레포 위치를 다시 확인하세요.

</details>

<details>
<summary>Hint 2</summary>

`npm run dev`가 4321이 아닌 다른 포트를 사용할 수 있습니다. 기억에 의존하지 말고 터미널의 `Local` 줄을 복사하세요.

</details>

<details>
<summary>Hint 3</summary>

Home URL에 저장소 이름 같은 base 경로가 붙어 있다면 다른 페이지도 같은 base 안에서 열어야 합니다. 직접 주소를 추측하기보다 Navigation 링크를 클릭해 전체 URL을 기록하세요.

</details>

## 퀴즈

### 질문

`git status`에 설명할 수 없는 변경이 있고 개발 서버 주소가 예상과 다를 때 가장 안전한 행동은?

- A. 변경을 전부 삭제하고 `localhost:4321`을 연다.
- B. 새 프로젝트를 만든다.
- C. 수정을 멈추고 변경의 의미를 확인한 뒤 터미널의 실제 Local URL을 사용한다.
- D. 배포 설정을 지운다.

<details>
<summary>정답 보기</summary>

**정답: C**

기존 작업은 지우지 않고 출발 상태와 실제 실행 주소부터 확인해야 합니다.

</details>

## 다음 단계에서 참고할 내용

현재 Codex 채팅이나 개인 노트에 아래 값을 남깁니다.

```text
3회차 출발 경로:
작업 폴더와 branch:
마지막 commit:
git status 판단:
정확한 Local URL:
열리는 페이지:
열리지 않는 페이지:
```

## 다음 단계

[03. Browser 설치와 연결 확인 →](./03-browser-setup.md)
