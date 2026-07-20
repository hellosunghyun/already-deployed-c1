# 배포했는데요? 1기 — 3회차 자료

3회차는 **2회차에서 만든 Astro 개인 홈페이지를 이어서 디자인 수정 하나를 완료하는 회차**입니다.
새 홈페이지를 만들지 않습니다. 기준은 기존 레포와 실행 가능한 로컬 화면이며, 가능하면 같은 Codex 프로젝트와 채팅에서 이어갑니다.

## 오늘의 목표

스크린샷, 브라우저 주석, 레퍼런스 토큰, 모바일 확인 결과를 이용해 Codex에게 디자인 수정 요구사항을 정확히 전달합니다.

```text
2회차 출발 상태 확인
→ Browser 또는 스크린샷으로 baseline 기록
→ 레퍼런스 토큰 분석
→ Home / Navigation / Projects·Posts 중 하나 선택
→ 증거를 반영한 최종 Plan
→ 프로젝트 루트 DESIGN.md + AGENTS.md 규칙 + docs/design-backlog/D-001.md
→ D-001 하나 실행
→ 모바일 / build / 배포 검증
```

## 출발 경로 A / B / C

| 경로 | 현재 상태 | 3회차 진행 방법 |
|---|---|---|
| A | Home / About / Projects / Posts와 build 결과가 있음 | 기존 레포와 가능하면 기존 채팅에서 전체 실습 진행 |
| B | 기존 레포에서 한 개 이상의 페이지가 로컬로 열림 | 열리는 페이지 하나를 D-001 Target으로 선택하고, Pages와 미완료 페이지는 별도로 기록 |
| C | 2회차 레포가 없거나 실행 가능한 페이지가 없음 | [2회차 출발 점검](../02/workbook/01-session-01-check.md)으로 돌아가 복구하거나 [2회차 완료 예제](../02/example-homepage/)를 개인 작업 폴더로 복사하고 Git 기준점을 준비해 시작 |

완료 예제 원본은 직접 수정하지 않습니다. 개인 폴더로 복사한 뒤 새 로컬 프로젝트로 열어 사용합니다. 복사본에는 `.git`이 없으므로 배포까지 진행하려면 [01단계의 경로 C Git 기준점](./workbook/01-existing-repo-check.md#경로-c의-git-기준점-만들기)을 디자인 수정 전에 완료합니다. 로컬 전용으로 진행하면 15~16단계의 배포 항목은 `not run`, 최종 상태는 `blocked`입니다.

2회차 숙제로 준비한 아래 자료를 먼저 꺼냅니다.

- 현재 홈페이지 스크린샷 1장
- 레퍼런스 링크 2~5개
- 고치고 싶은 부분 3개
- 모바일에서 이상한 부분 1개
- 유지하고 싶은 부분 1개

## Browser 경로와 스크린샷 대체 경로

로컬 화면을 함께 조작하는 기본 경로는 다음과 같습니다.

```text
ChatGPT 데스크톱 앱에서 Codex 선택
→ Plugins Directory에서 Browser 설치
→ 개발 서버 실행 후 터미널에 표시된 실제 Local URL 열기
→ @Browser로 해당 URL 확인
→ Annotation mode 켜기
→ 요소 클릭 또는 영역 드래그
→ 주석 작성·저장
→ 채팅에서 주석 반영 요청
```

Browser 권한 기본 선택은 `나 대신 승인`입니다. 화면의 메뉴명은 앱 버전이나 워크스페이스 설정에 따라 다를 수 있습니다.

Browser가 보이지 않거나 사용할 수 없는 환경에서는 실습을 중단하지 않습니다. 일반 브라우저에서 화면을 연 뒤 스크린샷을 첨부하고 아래 6좌표를 함께 적습니다.

```text
Where (URL + Viewport):
Target:
Evidence:
Problem:
Direction:
Constraint:
```

Codex CLI·IDE, Claude Code, Antigravity에서도 이 스크린샷 경로를 공통 대체 경로로 사용합니다.

## 워크북 진행 순서

파일 번호는 기존 이름을 유지하지만, 실제 진행 순서는 아래와 같습니다.

```text
00 워크북 사용법
→ 01 출발 상태 확인
→ 03 Browser 또는 스크린샷 경로 준비
→ 04 baseline
→ 05 화면 피드백 6좌표
→ 06 레퍼런스 선택
→ 07 토큰 브리프
→ 08 적용 요소 확정
→ 11 / 12 / 13 중 하나 선택
→ 02 증거 기반 최종 Plan
→ 09 DESIGN.md·AGENTS.md·백로그 README·D-001 실제 생성/갱신
→ 10 D-001 실행
→ 14 모바일 수정·재검증
→ 15 build·commit·push·Pages 확인
→ 16 결과 기록과 4회차 준비
```

## 참고 레퍼런스 사이트

| 사이트 | 수업에서의 역할 |
|---|---|
| [getdesign.md](https://getdesign.md/) | DESIGN.md 분석을 보고 스타일 방향 고르기 |
| [Refero Styles](https://styles.refero.design/) | colors, typography, spacing, components 예시 고르기 |
| [designmd.app](https://designmd.app/) | DESIGN.md 형식과 ready-to-use style 참고 |

## 전체 120분 운영안

앞의 30분은 발표와 데모, 뒤의 90분은 워크북 실습입니다. 워크북의 `W0:00`은 전체 수업 기준 `0:30`에 해당합니다.

| 시간 | 구간 | 목표 |
|---|---|---|
| 0:00-0:30 | 발표·데모 | 결과물, Browser·스크린샷 경로, 6좌표와 D-001 흐름 이해 |
| 0:30-0:38 | 출발·Browser | A/B/C 결정, 실제 Local URL, Browser 또는 스크린샷 경로 |
| 0:38-0:48 | 화면 증거 | baseline, 6좌표, Annotation 또는 스크린샷 |
| 0:48-1:00 | 레퍼런스·선택 | 레퍼런스 하나, 7개 토큰, 챌린지 하나 |
| 1:00-1:10 | 최종 Plan·백로그 | 증거 기반 Plan, AGENTS.md 규칙, D-001 생성 |
| 1:10-1:30 | 실행 | 선택한 D-001 한 건의 실제 수정 |
| 1:30-1:42 | 모바일 | 현재 desktop과 390x844 수정·재검증 |
| 1:42-1:54 | build·배포 | build, 승인 후 commit·push, Actions / Pages 확인 |
| 1:54-2:00 | 기록 | before/after, D-001 상태, 4회차 준비 |

## 성공 기준

상위 단계는 이전 단계의 조건을 모두 포함합니다.

### 최소

- A / B / C 출발 경로가 정해졌다.
- 수정 전 화면과 6좌표가 기록됐다.
- Home / Navigation / Projects·Posts 중 실행할 영역 하나가 정해졌다.

### 표준

- 최소 기준을 모두 충족했다.
- 레퍼런스에서 선택한 요소 하나를 7개 토큰으로 정리했다.
- 프로젝트 루트 `DESIGN.md`에 승인한 디자인 규칙이 있다.
- 증거 기반 최종 Plan과 `docs/design-backlog/D-001.md`가 있다.
- D-001에 해당하는 작은 수정 하나를 실행했다.
- desktop과 390x844 모바일 결과를 확인했다.

### 완료

- 표준 기준을 모두 충족했다.
- `npm run build`가 성공했다. 실패했다면 로그와 차단 상태를 남겼다.
- `doing` 상태에서 승인 후 commit과 push를 진행하고 GitHub Actions / 실제 Pages 결과를 확인했다. 모두 통과하면 16단계에서 `done`, 실패하거나 확인하지 못하면 `blocked`로 확정하고 미실행 단계는 `not run`으로 기록했다.
- 브라우저 주석 또는 스크린샷으로 Target을 정확히 지정했다.
- before/after, 실제 변경 파일, 검증 결과가 기록되고 D-001 상태가 `done` 또는 `blocked`로 갱신됐다.

## 자료 구조

- [발표자료 인덱스](./presentation/README.md)
- [워크북 인덱스](./workbook/README.md)
- [템플릿 인덱스](./templates/README.md)
- [브라우저 설정 스크린샷](./assets/codex-browser-settings.png)
- [웹 리서치 노트](./research-notes.md)

## 오늘의 핵심 문장

> 레퍼런스는 복사 대상이 아니라 요구사항 재료입니다.
> Plan mode는 바로 고치기 전에 수정 계약서를 만드는 단계입니다.

## 4회차 연결

4회차에서는 Notion을 콘텐츠 관리 도구처럼 연결합니다. 3회차 종료 전에 아래만 준비하고, Integration secret이나 token은 저장소와 채팅에 붙여넣지 않습니다.

- 로그인 가능한 Notion 계정과 사용할 workspace
- Posts로 옮길 글 후보 3개
- 각 글의 제목, 날짜, 태그, 요약, 공개 상태 초안
- 3회차 GitHub Pages URL과 남은 D-001 / D-002 상태
