# 2회차 워크북 인덱스

이 워크북은 **1회차에서 만든 Astro 개인 홈페이지를 읽히는 구조로 나누는 실습 문서**입니다.

프롬프트는 모두 한국어로 제공됩니다. 도구 기능이 크게 다르지 않은 단계에서는 [Codex](https://chatgpt.com/codex), [Claude Code](https://docs.claude.com/en/docs/claude-code), [Antigravity](https://codelabs.developers.google.com/getting-started-google-antigravity) 모두 같은 프롬프트를 사용합니다.

## 진행 순서

0. [워크북 사용법](./00-how-to-use.md)
1. [1회차 결과 확인](./01-session-01-check.md)
2. [현재 프로젝트 상태 점검](./02-project-state-audit.md)
3. [페이지 구조 만들기](./03-create-pages.md)
4. [공통 Layout과 Navigation 만들기](./04-layout-navigation.md)
5. [Home 페이지를 입구로 정리하기](./05-home-entry.md)
6. [About 페이지 초안 작성](./06-about-page.md)
7. [Projects 카드 만들기](./07-project-cards.md)
8. [Posts 기본 구조 만들기](./08-posts-list.md)
9. [브라우저와 build로 검증하기](./09-browser-build-review.md)
10. [commit / push / deploy 확인](./10-commit-push-deploy.md)
11. [결과 기록과 다음 숙제](./11-record-result-homework.md)

## 90분 실습 시간표

아래 시간표는 빠른 참가자와 느린 참가자가 같은 수업 안에서 길을 잃지 않게 하는 기준입니다.

| 시간 | 단계 | 꼭 남겨야 할 결과 |
|---|---|---|
| 0:00-0:15 | 00-02 | 출발 경로, 프로젝트 폴더, 현재 상태 |
| 0:15-0:40 | 03-04 | 페이지 생성, 공통 Layout, Navigation |
| 0:40-1:05 | 05-06 | Home 입구 정리, About 초안 |
| 1:05-1:20 | 07-08 | Projects 카드와 상세 링크, Posts 샘플 목록 |
| 1:20-1:28 | 09-10 | 브라우저 확인, build, commit / push 또는 실패 로그 |
| 1:28-1:30 | 11 | 결과 기록, AGENTS.md 갱신, 3회차 레퍼런스 준비 |

시간이 부족하면 07-08의 문장 완성도보다 09-10의 검증과 기록을 우선합니다.

## 막혔을 때 최소 산출물

모든 단계를 끝내지 못해도 아래 중 하나를 남기면 다음 세션에서 이어갈 수 있습니다.

| 막힌 위치 | 최소로 남길 것 |
|---|---|
| 01-02에서 막힘 | 작업 폴더 위치, GitHub URL, 현재 상태 요약 |
| 03에서 막힘 | 어떤 URL이 404인지, `src/pages` 구조 |
| 04에서 막힘 | Layout 파일 위치, Navigation이 보이는 페이지와 안 보이는 페이지 |
| 05-06에서 막힘 | Home / About에 넣을 임시 문장 3개 |
| 07에서 막힘 | 프로젝트 카드 데이터와 상세 설명 초안 |
| 08에서 막힘 | 글 샘플 데이터만이라도 기록 |
| 09-10에서 막힘 | build 실패 로그 또는 GitHub Actions 실패 화면 |

막힌 상태를 정확히 남기는 것도 수업 결과입니다.

## 다음 세션 전 레퍼런스 준비

3회차 전에는 내 홈페이지에 참고하고 싶은 개인 홈페이지 주소나 레퍼런스 링크를 2~5개 찾아옵니다.
직접 찾기 어렵다면 [Siteinspire](https://www.siteinspire.com/websites/category/personal), [Land-book](https://land-book.com/), [One Page Love](https://onepagelove.com/inspiration/), [Lapa Ninja](https://www.lapa.ninja/) 같은 레퍼런스 사이트에서 골라도 됩니다.
레퍼런스는 다양할수록 좋지만, 3회차에서는 그중 지금 내 홈페이지에 바로 적용하기 쉬운 요소부터 고릅니다.

링크만 가져오는 것보다 아래를 같이 적어오면 좋습니다.

- 가져오고 싶은 점
- 바로 적용하기 쉬운 점
- 따라하지 않을 점
- 내 홈페이지에서 바꾸고 싶은 위치

## 오늘의 최종 목표

```text
1회차 홈페이지
  ↓
Home / About / Projects / Posts
  ↓
Layout + Navigation
  ↓
Projects 카드
  ↓
Posts 샘플 목록
  ↓
build / commit / push / deploy 확인
  ↓
AGENTS.md 현재 구조 반영
```

## 오늘 계속 지킬 원칙

```text
현재 프로젝트를 유지하면서 필요한 구조만 추가합니다.
새 라이브러리는 승인 없이 추가하지 않습니다.
수정 전에는 계획을 먼저 받습니다.
수정 후에는 브라우저와 build로 확인합니다.
```

[시작하기 →](./00-how-to-use.md)
