# AGENTS.md

이 파일은 Codex 또는 Antigravity 같은 AI 코딩 에이전트가 이 프로젝트에서 지켜야 할 규칙입니다.

## 프로젝트 목표와 현재 상태

- 이 프로젝트는 Astro 기반 개인 홈페이지입니다.
- GitHub Pages의 project site 경로에서도 모든 링크와 자산이 열려야 합니다.
- 현재 사이트는 Home / About / Projects / Posts 구조를 가집니다.
- 공통 `BaseLayout`, Header Navigation, Footer를 모든 페이지가 공유합니다.
- Projects는 `src/data/projects.json`과 `ProjectCard.astro`를 사용하며, 각 카드의 상세 페이지가 열립니다.
- Posts는 `src/data/posts.json`의 샘플 글 목록을 사용합니다.
- 다음 작업은 Session 3에서 화면 증거를 바탕으로 디자인 수정 하나를 계획하고 검증하는 것입니다.

## 구조를 유지하는 규칙

- 내부 링크와 favicon 경로는 `import.meta.env.BASE_URL`을 사용합니다.
- 프로젝트 정보는 `src/data/projects.json`에서 관리하고 화면 문장을 여러 파일에 복사하지 않습니다.
- 글 정보는 `src/data/posts.json`에서 관리합니다.
- 외부 데이터가 생겨도 응답 원본을 화면에 바로 쓰지 않고 현재 JSON 구조로 변환합니다.
- 공통 Header, Navigation, Footer를 각 페이지에 복사하지 않습니다.

## 작업 원칙

- 새 라이브러리는 사용자 승인 없이 추가하지 않습니다.
- 관련 없는 파일은 수정하지 않습니다.
- secret, token, password, API key를 코드에 쓰지 않습니다.
- 삭제 명령은 실행 전에 반드시 사용자에게 물어봅니다.
- 디자인 수정 전에는 현재 화면과 관련 파일을 확인하고, 수정 계획과 대상 파일을 먼저 제안합니다.
- 한 번에 디자인 문제 하나를 선택하고, 허용된 파일 범위 안에서만 수정합니다.
- 수정 후 변경한 파일 목록과 변경 이유를 설명합니다.
- 데스크톱과 모바일 화면을 브라우저로 확인하고 `npm run build`를 실행합니다.
- 터미널에 출력된 실제 Local URL을 사용하며 포트나 base 경로를 추측하지 않습니다.

## Git / commit 규칙

변경사항이 생기면 작은 단위로 commit합니다.
단, commit과 push는 변경사항 요약을 먼저 보여주고 사용자 승인을 받은 뒤 진행합니다.

commit 메시지는 아래 형식을 사용합니다.

- `feat: 한국어설명`
- `fix: 한국어설명`
- `chore: 한국어설명`
- `docs: 한국어설명`

## 사용자가 초보자일 수 있음

사용자는 터미널, npm, Git, GitHub Pages를 처음 볼 수 있습니다.
명령어를 실행하기 전에 무엇을 하는 명령인지 짧게 설명하고, 실패하면 오류 원문과 다음 확인 항목을 함께 남깁니다.
