# 3회차 워크북 인덱스

이 워크북은 **2회차에서 만든 Astro 개인 홈페이지를 화면 기반으로 개선하는 실습 문서**입니다.

프롬프트는 Codex 기준으로 작성했습니다. 특히 Codex in-app browser, Browser use, browser comments를 기본 흐름으로 다룹니다. 다른 도구를 쓰는 경우에도 원칙은 같습니다. 화면 캡처와 선택 영역을 기준으로 요구사항을 구체화하면 됩니다.

## 진행 순서

0. [워크북 사용법](./00-how-to-use.md)
1. [2회차 결과와 현재 화면 확인](./01-session-02-check.md)
2. [디자인 baseline 기록하기](./02-visual-baseline-audit.md)
3. [스크린샷 기반 피드백 작성](./03-screenshot-feedback.md)
4. [Codex Browser comments로 영역 선택하기](./04-codex-browser-comments.md)
5. [레퍼런스 홈페이지와 디자인 토큰 브리프 만들기](./05-reference-analysis.md)
6. [디자인 수정 backlog 만들기](./06-design-change-backlog.md)
7. [Home hero 디자인 챌린지](./07-home-hero-design.md)
8. [Navigation과 레이아웃 밀도 조정](./08-navigation-layout-polish.md)
9. [Projects 카드와 Posts 목록 시각 위계 개선](./09-projects-posts-visual-hierarchy.md)
10. [모바일 화면 확인과 반응형 수정](./10-mobile-responsive-check.md)
11. [접근성 polish: 대비, focus, 터치 영역](./11-accessibility-polish.md)
12. [브라우저와 build로 최종 검증](./12-browser-build-review.md)
13. [commit / push / deploy 확인](./13-commit-push-deploy.md)
14. [결과 기록과 4회차 준비](./14-record-result-homework.md)

## 90분 실습 시간표

| 시간 | 단계 | 꼭 남겨야 할 결과 | 시간이 부족하면 |
|---|---|---|---|
| 0:00-0:10 | 00-01 | 현재 URL, 로컬 실행, 2회차 구조 상태 | 열린 URL과 안 열린 URL만 기록 |
| 0:10-0:25 | 02-03 | baseline 스크린샷과 문제 3개 | 문제 1개만 정확히 작성 |
| 0:25-0:40 | 04-06 | Browser comment, 레퍼런스 토큰 브리프, 수정 backlog | Browser comment 없이 토큰 브리프와 6좌표만 작성 |
| 0:40-1:05 | 07-09 | Home / Navigation / Projects / Posts 중 1~2개 영역 개선 | 한 영역만 작은 CSS 수정 |
| 1:05-1:25 | 10-11 | 모바일과 접근성 확인 | 390px 모바일만 확인 |
| 1:25-1:35 | 12 | Browser 확인과 `npm run build` | build 실패 로그 기록 |
| 1:35-1:45 | 13 | commit / push / deploy | git status와 다음 질문 기록 |
| 1:45-2:00 | 14 | before/after와 다음 숙제 | 수정 요청 프롬프트 하나 기록 |

## 오늘 계속 지킬 원칙

```text
화면 전체를 막연히 바꾸지 않습니다.
레퍼런스는 복제하지 않고 디자인 토큰으로 분해합니다.
getdesign.md, Refero Styles, designmd.app 같은 DESIGN.md 레퍼런스도 참고합니다.
원하는 요소만 하나 골라 선택한 한 영역을 작은 단위로 고칩니다.
수정 전에는 원인 후보와 계획을 먼저 받습니다.
수정 후에는 Codex Browser와 모바일 폭으로 확인합니다.
마지막에는 build와 기록을 남깁니다.
```


## DESIGN.md 레퍼런스 사이트

3회차에서 참고할 수 있는 사이트입니다.
링크를 많이 고르는 것이 목표가 아니라, **한 사이트에서 원하는 요소 하나만 고르는 것**이 목표입니다.

| 사이트 | 사용할 때 |
|---|---|
| [getdesign.md](https://getdesign.md/) | 브랜드/제품별 DESIGN.md 분석에서 스타일 방향을 빠르게 고를 때 |
| [Refero Styles](https://styles.refero.design/) | 실제 제품 화면 기반 style과 DESIGN.md 예시를 고를 때 |
| [designmd.app](https://designmd.app/) | DESIGN.md 형식과 ready-to-use style을 함께 볼 때 |

선택 예시는 아래처럼 씁니다.

```text
Reference: Refero Styles의 Linear 계열 dark command deck
가져올 요소: 카드 gap과 muted text 위계만
적용 위치: /projects 카드 목록
가져오지 않을 것: dark background 전체, logo, animation, 외부 폰트
```

## 레퍼런스 → 디자인 토큰 → Codex 적용 흐름

3회차의 챌린지 흐름은 아래입니다.

```text
레퍼런스 URL 또는 스크린샷
→ GPT에게 디자인 토큰 설명 요청
→ token brief 작성
→ 내 홈페이지의 적용 영역 선택
→ Codex에게 CSS 변수 / 기존 스타일에 매핑 요청
→ Browser comment와 모바일 폭으로 검증
```

디자인 토큰은 어려운 디자인 시스템 용어로 외우지 않습니다. 오늘은 아래처럼 **반복해서 쓰는 시각 규칙의 이름표**로 이해합니다.

```text
Color: 배경, 표면, 본문, 보조 텍스트, 테두리, 강조색
Typography: 제목 크기, 본문 크기, 줄간격, 굵기
Spacing: 섹션 여백, 카드 gap, 카드 내부 padding
Shape: radius, border
Elevation: shadow 사용 여부와 강도
Layout: max-width, grid column, 모바일 전환 지점
```

레퍼런스에서 본 정확한 색상이나 폰트를 그대로 복사하는 것이 목표가 아닙니다. 내 홈페이지의 목적과 콘텐츠에 맞는 토큰만 가져와서 작은 수정으로 검증합니다.

## 좋은 디자인 요청의 6좌표

```text
URL:
Viewport:
Target:
Problem:
Direction:
Constraint:
```

이 6개가 있으면 디자인 요청이 훨씬 정확해집니다.

## 저장 체크포인트

3회차 권장 commit 메시지는 아래처럼 작게 나눕니다.

```text
feat: 홈 히어로 시각 위계 개선
feat: 프로젝트 카드 디자인 정리
fix: 모바일 내비게이션 줄바꿈 개선
fix: 접근성 focus 스타일 보강
docs: 3회차 디자인 수정 기록 추가
```

실제 commit은 변경사항을 확인한 뒤, 13단계에서 push까지 정리하거나 사용자가 명시적으로 승인했을 때 진행합니다.

[시작하기 →](./00-how-to-use.md)
