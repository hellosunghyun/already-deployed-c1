# 2회차 완료 예제 코드베이스

이 폴더는 **2회차 워크북을 끝까지 진행했을 때의 예시 결과물**입니다.

2회차를 마치지 못했거나 Session 3에서 사용할 프로젝트가 없는 사람은 이 폴더를 개인 작업 폴더로 복사한 뒤 출발 상태로 사용할 수 있습니다.

## 완료된 내용

- Home / About / Projects / Posts 페이지
- 공통 `BaseLayout`, Header Navigation, Footer
- `ProjectCard.astro`로 반복되는 프로젝트 카드 구성
- `src/data/projects.json`의 프로젝트 3개
- 각 프로젝트 카드에서 열리는 상세 페이지
- `src/data/posts.json`의 샘플 글 2개와 Posts 목록
- GitHub Pages project site의 base 경로를 고려한 내부 링크와 favicon
- Session 3 디자인 수정 준비가 반영된 `AGENTS.md`

## 가장 쉬운 시작 방법

1. 이 폴더를 개인 작업 폴더로 복사합니다.
2. Codex 앱에서 복사한 폴더를 프로젝트로 엽니다.
3. 아래 문장을 Codex에게 보냅니다.

```text
이 폴더는 2회차 완료 예제야.
파일 구조를 먼저 확인하고, 필요한 패키지를 npm ci로 설치해줘.
그다음 로컬 미리보기 서버를 실행하고 터미널에 출력된 실제 Local URL을 알려줘.
Home / About / Projects / Posts와 프로젝트 상세 링크가 모두 열리는지도 확인해줘.
```

## Session 3에서 배포까지 이어갈 때

이 폴더를 복사하면 소스 파일은 생기지만 `.git` 기록은 복사되지 않습니다. 개인 복사본에서 배포까지 진행하려면 디자인 수정 전에 [Session 3 경로 C의 Git 기준점 만들기](../../03/workbook/01-existing-repo-check.md#경로-c의-git-기준점-만들기)를 완료합니다.

- 빈 GitHub 저장소와 승인한 remote를 준비합니다.
- 현재 `site`와 `base`를 내 Pages 주소에 맞춥니다.
- `npm run build` 성공 후 수정 전 상태를 baseline commit으로 먼저 남깁니다.
- 기존 remote나 Git 기록은 덮어쓰지 않습니다.

GitHub 연결 없이 로컬만 실습할 수도 있습니다. 이때 Session 3의 remote·push·Actions·Pages 결과는 `not run`, 최종 D-001 상태는 `blocked`로 기록합니다.

## 실행 방법

처음 한 번 의존성을 정확히 설치합니다.

```bash
npm ci
```

로컬 개발 서버를 실행합니다.

```bash
npm run dev
```

브라우저 주소를 미리 추측하지 말고, 터미널의 `Local` 줄에 출력된 URL을 그대로 복사합니다.
현재 예제 설정에서는 보통 아래처럼 project site의 base 경로가 포함됩니다.

```text
http://localhost:4321/already-deployed-c1/
```

포트가 이미 사용 중이면 `4322`처럼 다른 번호가 나올 수 있으므로 반드시 실제 출력값을 사용합니다.

## 확인할 화면

실제 Local URL 뒤에 아래 경로가 이어지는지 확인합니다.

```text
Home:     /already-deployed-c1/
About:    /already-deployed-c1/about/
Projects: /already-deployed-c1/projects/
Posts:    /already-deployed-c1/posts/
```

Projects의 `자세히 보기` 링크 세 개도 각각 실제 상세 페이지로 이동해야 합니다.

## build 확인

```bash
npm run build
```

오류 없이 끝나면 배포 가능한 정적 파일이 `dist` 폴더에 만들어집니다.

## 내 GitHub Pages 주소에 맞추기

개인 저장소로 복사했다면 `astro.config.mjs`의 `site`와 `base`를 자신의 주소에 맞게 확인합니다.

- 사용자 사이트 `username.github.io` 저장소: `base: "/"`
- 프로젝트 사이트 `username.github.io/my-homepage`: `base: "/my-homepage/"`

설정을 바꾼 뒤에는 다시 `npm run build`를 실행하고, 새로 출력된 실제 Local URL로 모든 링크를 확인합니다.

## 주요 파일 구조

```text
.
├── .github/workflows/deploy.yml
├── public/favicon.svg
├── src
│   ├── components
│   │   ├── ProjectCard.astro
│   │   ├── SiteFooter.astro
│   │   └── SiteHeader.astro
│   ├── data
│   │   ├── posts.json
│   │   └── projects.json
│   ├── layouts/BaseLayout.astro
│   ├── pages
│   │   ├── projects/[slug].astro
│   │   ├── about.astro
│   │   ├── index.astro
│   │   ├── posts.astro
│   │   └── projects.astro
│   └── styles/global.css
├── AGENTS.md
├── astro.config.mjs
├── package.json
└── tsconfig.json
```

## 내 내용으로 바꿀 곳

- 이름과 소개: `src/pages/index.astro`, `src/pages/about.astro`
- 프로젝트 내용: `src/data/projects.json`
- 글 목록: `src/data/posts.json`
- 공통 사이트 이름: `src/components/SiteHeader.astro`

프로젝트를 추가할 때는 기존 카드 코드를 복사하지 않고 `projects.json`에 같은 구조의 항목을 추가합니다.

## Session 3 시작 전 확인

- 터미널에 출력된 실제 Local URL을 기록합니다.
- 현재 화면 스크린샷 1장을 준비합니다.
- 참고 홈페이지 또는 레퍼런스 링크 2~5개를 준비합니다.
- 고치고 싶은 부분 3개, 모바일 문제 1개, 유지할 부분 1개를 기록합니다.
- Session 3에서는 이 중 디자인 문제 하나만 선택해 계획부터 확인합니다.
