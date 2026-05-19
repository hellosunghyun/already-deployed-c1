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
- 반복되는 프로젝트 정보를 Component, 데이터, 상세 페이지로 다루는 법
- 글 중심 콘텐츠를 Posts로 분리하고, 외부 콘텐츠 소스나 MDX 같은 구조로 확장할 준비를 하는 법
- 수정 후 build / commit / push / deploy까지 다시 확인하는 법

을 함께 익히는 것입니다.

## 페이지 구성에 대한 전제

Home / About / Projects / Posts에 어떤 내용을 넣을지는 정답이 정해진 문제가 아닙니다.
이 자료의 구분은 **이번 수업을 진행하기 위한 현재 기준**입니다.

개인 홈페이지의 성격에 따라 About을 짧게 둘 수도 있고, Projects보다 Posts를 더 중요하게 둘 수도 있습니다.
2회차에서는 일단 방문자가 길을 잃지 않도록 기본 구조를 잡고, 이후 회차에서 각자의 기준에 맞게 바꿉니다.

## 2시간 운영안

2회차는 **발표 30분 + 실습 90분**을 기준으로 운영합니다.
처음부터 모든 개념을 완벽히 설명하려고 하기보다, 참가자가 실습 중에 다시 읽을 수 있는 기준 문장을 먼저 심어두는 방식이 좋습니다.

| 시간 | 구간 | 목표 |
|---|---|---|
| 0:00-0:05 | 시작과 출발 상태 확인 | 1회차 완료 여부가 달라도 참여 가능하다는 기준 맞추기 |
| 0:05-0:15 | 정보 구조 설명 | Home / About / Projects / Posts가 왜 나뉘는지 이해 |
| 0:15-0:23 | Astro 구조 설명 | `src/pages`, URL, Layout, Component를 쉬운 말로 연결 |
| 0:23-0:30 | 데모와 실습 전환 | AI에게 계획을 먼저 받는 흐름 확인 |
| 0:30-0:45 | 실습 01-02 | 프로젝트 상태 점검, 출발 경로 정리 |
| 0:45-1:10 | 실습 03-04 | 페이지 생성, Layout, Navigation 만들기 |
| 1:10-1:35 | 실습 05-08 | Home / About / Projects / Posts 내용 채우기, Projects 상세 연결 |
| 1:35-1:50 | 실습 09-10 | 브라우저 확인, build, commit / push |
| 1:50-2:00 | 실습 11 | 결과 기록, 3회차 디자인 수정 재료 정리 |

### 오늘의 범위와 성공 기준은 다릅니다

오늘 수업에서 다루는 범위는 넓습니다.

- Home / About / Projects / Posts 구조
- 공통 Layout과 Navigation
- Projects 카드와 상세 링크
- Posts 샘플 목록
- 브라우저 확인
- build
- commit / push / deploy 확인
- 결과 기록
- AGENTS.md 갱신 또는 갱신 프롬프트 기록
- 3회차 디자인 수정 재료 정리

하지만 모든 참가자가 수업 시간 안에 모든 항목을 같은 완성도로 끝내야 한다는 뜻은 아닙니다.

오늘의 최소 성공은 아래입니다.

```text
1. 작업할 프로젝트 폴더와 현재 상태를 안다.
2. /about, /projects, /posts 중 어디까지 열리는지 안다.
3. Navigation 또는 Layout 적용 상태를 안다.
4. build 결과 또는 실패 로그가 있다.
5. 다음 세션에서 이어갈 질문이나 수정 재료가 있다.
```

Projects와 Posts는 오늘 다루는 핵심 범위입니다.
다만 시간이 부족하면 카드 문장 완성도, 상세 페이지 완성도, Posts 문장 다듬기는 다음으로 미룰 수 있습니다.

AGENTS.md는 갱신까지 하면 가장 좋지만, 시간이 부족하면 갱신할 프롬프트를 기록하는 것으로 충분합니다.

### 시간이 부족할 때

- 반드시 남겨야 하는 것: 현재 상태, 열린 URL, 안 열린 URL, build 결과 또는 실패 로그
- 수업 범위에는 포함하지만 완성도를 낮춰도 되는 것: Projects 카드 문장, Posts 글 문장, 상세 페이지 문장
- 다음으로 미뤄도 되는 것: 카드 디자인 세부 조정, Posts 문장 다듬기, 프로젝트 문구 완성도
- 끝까지 못 가도 남겨야 하는 것: 현재 상태, 실패 로그, 다음 질문 프롬프트

### 시간이 남을 때

- Navigation 링크 문구를 더 자연스럽게 바꾸기
- Projects 카드 1개를 추가해보기
- 모바일 폭에서 텍스트가 깨지는지 확인하기
- 3회차에서 고치고 싶은 디자인 문제를 3개 적기
- 내 홈페이지에 참고하고 싶은 개인 홈페이지 주소 또는 레퍼런스 링크 2~5개 찾아오기
- 다양한 레퍼런스 중 지금 바로 적용하기 쉬운 요소 고르기
- 레퍼런스에서 가져오고 싶은 점과 따라하지 않을 점을 각각 적기

## 운영 멘트

### 시작할 때

```text
오늘은 범위가 넓습니다.
Home / About / Projects / Posts, Layout, Navigation, Projects 카드, Posts 샘플 목록까지 다룹니다.

하지만 오늘의 성공 기준은 모두가 같은 완성도로 끝내는 것이 아닙니다.
최소 성공은 현재 상태, 열린 URL, 막힌 지점, build 결과나 실패 로그, 다음 질문을 남기는 것입니다.

Projects와 Posts는 오늘 다룹니다.
다만 문장 완성도와 상세 디자인은 다음으로 미룰 수 있습니다.

발표자료는 실습 진도표가 아니라, 모두가 같은 단어를 쓰기 위한 개념 설명입니다.
실습은 각자 속도대로 워크북을 따라갑니다.
```

### 70분쯤

```text
지금부터 새 기능 욕심을 줄입니다.
아직 /about, /projects, /posts가 안 열리는 사람은 URL 확인을 먼저 합니다.
열리는 사람은 Projects / Posts를 진행합니다.
이미 Projects / Posts까지 한 사람은 build와 기록으로 갑니다.

오늘 끝까지 못 해도 괜찮습니다.
대신 어디까지 됐는지와 다음 질문은 반드시 남깁니다.
```

### 마지막 10분

```text
이제 구현을 멈추고 기록합니다.

1. 어떤 페이지가 열리는지
2. 어떤 페이지가 안 열리는지
3. build가 성공했는지 실패했는지
4. Projects / Posts는 어디까지 됐는지
5. 3회차에서 고치고 싶은 화면은 무엇인지
6. AGENTS.md는 갱신했는지, 아니면 갱신 프롬프트만 남겼는지

이 기록이 있으면 다음 세션에서 이어갈 수 있습니다.
```

## 친절함 점검 기준

2회차는 참가자가 "개발 개념이 갑자기 어려워졌다"고 느끼기 쉬운 회차입니다.
진행자는 아래 기준을 계속 확인합니다.

| 상황 | 진행자가 먼저 해줄 말 |
|---|---|
| 1회차를 끝내지 못함 | 예제 폴더에서 시작해도 됩니다. 오늘 배울 구조는 똑같습니다. |
| 페이지와 섹션을 헷갈림 | 주소가 따로 있으면 페이지, 한 화면 안의 구역이면 섹션입니다. |
| `Layout`이 어려움 | 모든 페이지가 같이 입는 공통 옷이라고 생각하면 됩니다. |
| `Component`와 `array`가 어려움 | 카드 양식 하나에 여러 내용을 바꿔 끼우는 구조입니다. |
| build나 deploy가 실패함 | 실패 로그를 남기면 오늘 수업의 최소 성공 기준은 확보한 것입니다. |
| 시간이 부족함 | 문장 완성도보다 구조, 검증, 기록을 우선합니다. |

### 진행자가 피할 말

- "이건 쉬운데요?"
- "아까 했잖아요."
- "일단 다 지우고 새로 만들죠."
- "시간 없으니까 그냥 넘어가요."

대신 이렇게 말합니다.

```text
지금은 어디까지 되었는지 확인하는 게 먼저입니다.
완성보다 현재 상태와 다음 질문을 남기는 것이 중요합니다.
```

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
- [Slide 06A. 페이지와 섹션 미니 연습](./presentation/slides/06a-page-section-exercise.md)
- [Slide 07. Astro 파일 기반 라우팅](./presentation/slides/07-astro-routing.md)
- [Slide 08. Layout과 Navigation](./presentation/slides/08-layout-navigation.md)
- [Slide 09. Component와 데이터](./presentation/slides/09-component-data.md)
- [Slide 09A. Component를 코드 없이 이해하기](./presentation/slides/09a-component-data-analogy.md)
- [Slide 10. Posts를 미리 만드는 이유](./presentation/slides/10-posts-before-notion.md)
- [Slide 11. Codex 데모 흐름](./presentation/slides/11-codex-demo.md)
- [Slide 11A. 데모를 볼 때 확인할 것](./presentation/slides/11a-demo-watch-points.md)
- [Slide 12. 워크북으로 이동](./presentation/slides/12-workbook.md)

### 워크북

워크북은 단계별로 작게 나누었습니다. 각 파일은 **목표**, **왜 하는가**, **프롬프트**, **Ready Gate**, **힌트**, **퀴즈**, **저장 체크포인트**를 포함합니다.

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
