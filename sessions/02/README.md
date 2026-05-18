# 배포했는데요? 1기 — 2회차 자료

이 폴더는 **2회차 수업을 Markdown 문서만으로 진행하기 위한 자료 묶음**입니다.
1회차의 목표가 `github.io` 링크를 만드는 것이었다면, 2회차의 목표는 그 사이트를 방문자가 읽을 수 있는 구조로 나누는 것입니다.

## 오늘의 목표

**1회차에서 만든 Astro 개인 홈페이지를 Home / About / Projects / Posts 구조로 확장합니다.**

오늘의 진짜 목표는 페이지를 많이 만드는 것이 아닙니다.

- 홈페이지를 정보 구조로 바라보는 법
- 페이지와 섹션을 구분하는 법
- Astro의 파일 기반 라우팅을 이해하는 법
- 웹의 라우팅을 SwiftUI의 화면 이동과 비교해서 이해하는 법
- 공통 Layout과 Navigation을 만드는 이유
- 반복되는 정보를 Component와 데이터로 다루는 법
- Notion을 붙이기 전 Posts 구조를 미리 준비하는 법
- 수정 후 build / commit / push / deploy까지 다시 확인하는 법

을 함께 익히는 것입니다.

## 1회차 완료 상태별 진행 경로

2회차는 참가자마다 출발점이 다를 수 있습니다.

### A. GitHub Pages 링크가 이미 열리는 경우

가장 좋은 출발점입니다. 본인 프로젝트 폴더를 열고 2회차 워크북을 그대로 진행합니다.

### B. GitHub에는 올라갔지만 Pages가 아직 안 되는 경우

로컬에서 `npm run dev`와 `npm run build`가 되는지 먼저 확인합니다.
2회차 구조 작업은 진행하되, 마지막 배포 확인 단계에서 Pages 문제를 다시 점검합니다.

### C. 1회차를 끝내지 못한 경우

1회차 완료 예제인 [`sessions/01/example-homepage`](../01/example-homepage)를 기준 상태로 사용해도 됩니다.
이 경우 2회차 워크북의 첫 단계에서 예제 폴더를 현재 작업 폴더로 열어 시작합니다.

## 자료 구조

### 발표자료

발표자료는 슬라이드별 Markdown 파일로 나누었습니다.

- [발표자료 인덱스](./presentation/README.md)
- [Slide 01. 표지](./presentation/slides/01-title.md)
- [Slide 02. 오늘의 성공 기준](./presentation/slides/02-success.md)
- [Slide 03. 1회차 결과는 시작점](./presentation/slides/03-from-deploy-to-structure.md)
- [Slide 04. 홈페이지는 탐색 공간](./presentation/slides/04-homepage-as-navigation-space.md)
- [Slide 05. Home / About / Projects / Posts](./presentation/slides/05-four-page-roles.md)
- [Slide 06. 페이지와 섹션](./presentation/slides/06-page-vs-section.md)
- [Slide 07. Astro 파일 기반 라우팅](./presentation/slides/07-astro-routing.md)
- [Slide 08. Layout과 Navigation](./presentation/slides/08-layout-navigation.md)
- [Slide 09. Component와 데이터](./presentation/slides/09-component-data.md)
- [Slide 10. Posts를 미리 만드는 이유](./presentation/slides/10-posts-before-notion.md)
- [Slide 11. Codex 데모 흐름](./presentation/slides/11-codex-demo.md)
- [Slide 12. 워크북으로 이동](./presentation/slides/12-workbook.md)

### 워크북

워크북은 단계별로 작게 나누었습니다. 각 파일은 **목표**, **왜 하는가**, **프롬프트**, **Ready Gate**, **힌트**, **퀴즈**, **커밋 가이드**를 포함합니다.

- [워크북 인덱스](./workbook/README.md)
- [00. 워크북 사용법](./workbook/00-how-to-use.md)
- [01. 1회차 결과 확인](./workbook/01-session-01-check.md)
- [02. 현재 프로젝트 상태 점검](./workbook/02-project-state-audit.md)
- [03. 페이지 구조 만들기](./workbook/03-create-pages.md)
- [04. 공통 Layout과 Navigation 만들기](./workbook/04-layout-navigation.md)
- [05. Home 페이지를 입구로 정리하기](./workbook/05-home-entry.md)
- [06. About 페이지 초안 작성](./workbook/06-about-page.md)
- [07. Projects 카드 만들기](./workbook/07-project-cards.md)
- [08. Posts 기본 구조 만들기](./workbook/08-posts-list.md)
- [09. 브라우저와 build로 검증하기](./workbook/09-browser-build-review.md)
- [10. commit / push / deploy 확인](./workbook/10-commit-push-deploy.md)
- [11. 결과 기록과 다음 숙제](./workbook/11-record-result-homework.md)

### 템플릿

- [개인 정보 정리 템플릿](./templates/personal-intake.md)
- [프로젝트 카드 데이터 템플릿](./templates/project-card-data.md)
- [글 목록 샘플 데이터 템플릿](./templates/post-list-data.md)

## 진행 방식

1. 앞부분은 [발표자료](./presentation/README.md)를 보며 설명합니다.
2. 이후 참가자는 [워크북](./workbook/README.md)을 따라 각자 진행합니다.
3. 진행자는 중간중간 전체 체크만 합니다.
4. 막히면 먼저 해당 단계의 **힌트**를 봅니다.
5. 그래도 안 되면 AI에게 현재 단계, 에러, 원하는 결과를 함께 전달합니다.

## 오늘의 핵심 문장

> 첫 배포는 시작점입니다.  
> 오늘은 방문자가 길을 잃지 않도록 사이트의 구조를 만듭니다.
