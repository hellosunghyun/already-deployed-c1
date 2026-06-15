# 3회차 웹 리서치 노트

3회차는 **디자인 수정 요청을 더 정확히 하는 법**을 다룹니다. 기준은 Codex 앱의 in-app browser와 Browser use입니다.

## 확인한 핵심 근거

- Codex in-app browser는 Codex와 사용자가 같은 렌더링 화면을 보며 웹앱을 preview하고, 화면 위에 visual comments를 남길 수 있는 기능입니다. 로컬 개발 서버, 파일 기반 preview, 로그인 없는 공개 페이지에 적합합니다.  
  참고: [OpenAI Developers — In-app browser](https://developers.openai.com/codex/app/browser)

- Codex Browser use는 in-app browser를 직접 조작하면서 클릭, 입력, 렌더링 상태 검사, 스크린샷, 페이지 자산 다운로드, read-only JavaScript 기반 페이지 점검, 수정 검증에 사용할 수 있습니다.  
  참고: [OpenAI Developers — In-app browser / Browser use](https://developers.openai.com/codex/app/browser)

- Codex in-app browser는 로그인 흐름, 사용자의 일반 브라우저 프로필, 쿠키, 확장 프로그램, 기존 탭을 지원하지 않습니다. 로그인 상태가 필요한 웹사이트는 Codex Chrome extension을 사용합니다.  
  참고: [OpenAI Developers — Codex Chrome extension](https://developers.openai.com/codex/app/chrome-extension)

- Codex Developer mode의 full CDP access는 콘솔 출력, 네트워크 트래픽, 페이지 상태, JavaScript 성능 같은 더 깊은 브라우저 디버깅에 쓰입니다. 민감한 브라우저 내부에 접근할 수 있으므로 명시적 승인과 좁은 범위가 필요합니다.  
  참고: [OpenAI Help — Using Codex with your ChatGPT plan](https://help.openai.com/en/articles/11369540-using-codex-with-your-chatgpt-plan)

- Chrome DevTools Device Mode는 모바일 viewport, CPU/network throttling, orientation 같은 모바일 환경을 시뮬레이션하지만 실제 모바일 기기 실행을 완전히 대체하지 않습니다. 의심스러우면 실제 기기 확인이 더 좋습니다.  
  참고: [Chrome DevTools — Simulate mobile devices with device mode](https://developer.chrome.com/docs/devtools/device-mode)

- Chrome DevTools는 우클릭 Inspect로 DOM과 CSS를 확인할 수 있고, Elements panel에서 선택된 요소에 적용된 CSS rules를 볼 수 있습니다.  
  참고: [Chrome DevTools — Open DevTools](https://developer.chrome.com/docs/devtools/open)

- 반응형 웹 디자인은 모든 화면 크기와 해상도에서 잘 렌더링되고 usable해야 한다는 접근입니다. media query, flexible layout, viewport meta tag 등이 핵심입니다.  
  참고: [MDN — Responsive web design](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/CSS_layout/Responsive_Design)

- CSS `clamp()`는 최소값, 선호값, 최대값 사이에서 값을 제한하는 함수입니다. 제목 크기와 여백을 유동적으로 조정할 때 3회차 챌린지에 적합합니다.  
  참고: [MDN — clamp()](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference/Values/clamp)

- Lighthouse는 Chrome DevTools, CLI, Node module에서 실행할 수 있는 웹 품질 자동 점검 도구이며 performance, accessibility, SEO 등을 점검합니다.  
  참고: [Chrome for Developers — Lighthouse overview](https://developer.chrome.com/docs/lighthouse/overview)

- WCAG 2.2는 웹 콘텐츠 접근성 표준입니다. 디자인 수정 수업에서는 특히 색 대비, focus visible, target size, 모바일 usability를 최소 기준으로 다룹니다.  
  참고: [W3C — WCAG 2.2](https://www.w3.org/TR/WCAG22/)

- WCAG contrast minimum은 일반 텍스트 4.5:1, 큰 텍스트 3:1 대비를 기준으로 삼습니다.  
  참고: [W3C WAI — Understanding Contrast Minimum](https://www.w3.org/WAI/WCAG21/Understanding/contrast-minimum.html)


- Design Tokens Format Module 2025.10은 서로 다른 도구 간 디자인 토큰 데이터를 교환하기 위한 파일 포맷 기술 명세입니다. 이 명세는 2025년 10월 28일 DTCG의 Final Community Group Report로 발행되었고, 토큰을 최소한 name/value pair로 설명합니다. 3회차에서는 정식 포맷 전체를 구현하지 않고, color / typography / spacing / radius / shadow / layout을 설명하는 교육용 브리프로 사용합니다.  
  참고: [Design Tokens Format Module 2025.10](https://www.designtokens.org/TR/2025.10/format/)

- Chrome DevTools CSS Overview는 페이지의 색, 폰트 정보, unused declarations, media queries 등을 보고서로 보여주며 low contrast 이슈도 확인할 수 있습니다. 레퍼런스 사이트나 본인 사이트의 토큰을 추정할 때 보조 도구로 사용할 수 있습니다.  
  참고: [Chrome DevTools — CSS Overview](https://developer.chrome.com/docs/devtools/css-overview)

## 3회차 설계에 반영한 원칙

```text
스크린샷은 증거다.
브라우저 주석은 위치다.
레퍼런스는 토큰 재료다.
프롬프트는 요구사항이다.
Codex 수정은 가설이다.
검증은 브라우저와 build로 한다.
```

## 수업에서 쓰는 6좌표 피드백

디자인 요청은 아래 6가지를 채우면 정확해집니다.

```text
1. URL: 어느 페이지인가
2. Viewport: 어떤 화면 크기인가
3. Target: 어느 요소/영역인가
4. Problem: 무엇이 문제인가
5. Direction: 어떤 방향으로 바꿀 것인가
6. Constraint: 유지할 것과 하지 말아야 할 것
```


## 레퍼런스 토큰 브리프 항목

```text
Reference URL:
Reference summary:
Color tokens:
Typography tokens:
Spacing tokens:
Radius / shadow tokens:
Layout tokens:
Bring:
Avoid:
Apply to my site:
Verification:
```

이 항목은 DTCG 포맷을 엄격히 따르는 산출물이 아니라, 초보자가 Codex에게 디자인 요구사항을 정확히 전달하기 위한 교육용 중간 산출물입니다.


## DESIGN.md 레퍼런스 라이브러리 리서치 추가

3회차 레퍼런스 실습에는 일반 홈페이지 URL뿐 아니라 DESIGN.md 레퍼런스 라이브러리를 함께 사용합니다. 이유는 참가자가 "예쁜 사이트"를 막연히 고르는 대신, AI가 읽기 쉬운 디자인 토큰과 규칙 형태로 레퍼런스를 가져올 수 있기 때문입니다.

### 확인한 레퍼런스 사이트

- [getdesign.md](https://getdesign.md/)  
  DESIGN.md collection입니다. 실제 브랜드/제품 스타일을 `patterns`, `tokens`, `rules` 관점으로 분석해 AI coding agent의 inspiration으로 쓰는 것을 목표로 설명합니다. 2026-06-15 기준 메인 화면에는 75개의 DESIGN.md 파일과 AI/LLM, developer tools, SaaS, fintech, media, automotive 같은 카테고리가 보입니다.

- [Refero Styles](https://styles.refero.design/)  
  AI agent용 DESIGN.md example 라이브러리입니다. 사이트 설명 기준으로 2,000개 이상의 AI-readable design systems를 탐색할 수 있고, 각 style은 colors, typography, spacing, components, DESIGN.md를 포함합니다. Cursor, Claude Code, Codex, v0, Lovable 같은 AI coding tool에 붙여 넣을 수 있는 예시로 안내됩니다.

- [designmd.app](https://designmd.app/)  
  DESIGN.md 라이브러리와 format 설명을 제공합니다. 사이트 설명 기준으로 454개의 documented DESIGN.md를 제공하며, DESIGN.md를 프로젝트 루트에 두는 Markdown 파일로 설명합니다. 이 파일은 AI agent에게 colors, typography, visual patterns를 알려주는 용도입니다.

- [Google Labs Code design.md specification](https://github.com/google-labs-code/design.md)  
  DESIGN.md는 AI coding agent에게 visual identity를 설명하기 위한 open format입니다. 구조는 YAML front matter의 machine-readable design tokens와 Markdown prose의 human-readable design rationale를 결합합니다. 토큰은 정확한 값, prose는 그 값을 왜 어떻게 쓰는지 설명합니다.

### 3회차에 반영한 운영 원칙

```text
레퍼런스 사이트를 고른다.
→ 전체를 따라 하지 않는다.
→ 원하는 요소 1개만 고른다.
→ color / typography / spacing / radius / shadow / layout 토큰으로 설명한다.
→ 내 홈페이지의 특정 영역에만 적용한다.
→ Codex Browser에서 before/after와 모바일 폭으로 검증한다.
```

### 수업에서 강조할 금지선

```text
하지 않을 것:
- 브랜드 로고, 고유 이미지, 고유 그래픽 복제
- 레퍼런스 전체 색상/레이아웃 일괄 복제
- 외부 폰트와 무거운 애니메이션 무단 추가
- 홈페이지의 콘텐츠 구조나 JSON 데이터 구조 변경
- "이 사이트처럼 다 바꿔줘" 요청

할 것:
- hero title scale만 가져오기
- card gap과 padding 리듬만 가져오기
- muted text 역할만 가져오기
- border/radius/shadow 강도만 가져오기
- mobile breakpoint 감각만 가져오기
```
