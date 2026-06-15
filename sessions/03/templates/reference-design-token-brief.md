# 레퍼런스 디자인 토큰 브리프 템플릿

다른 홈페이지나 DESIGN.md 레퍼런스를 그대로 베끼지 않고, 내 홈페이지에 적용 가능한 토큰으로 번역하기 위한 템플릿입니다.

## 1. 레퍼런스

```text
Reference source: getdesign.md / Refero Styles / designmd.app / 직접 찾은 사이트
Reference URL:
Reference screenshot path 또는 파일명:
분석한 페이지 또는 style:
마음에 든 이유 한 문장:
내 홈페이지 적용 후보 영역:
```

## 2. 이번에 가져올 요소 하나

```text
선택한 요소:
- [ ] Hero title scale
- [ ] Navigation treatment
- [ ] Project card framing
- [ ] Posts list density
- [ ] Color role
- [ ] Layout rhythm

선택 이유:
적용할 URL:
적용할 Target:
가져오지 않을 요소:
```

## 3. GPT가 설명한 디자인 토큰

```text
Color:
- background:
- surface:
- text:
- muted:
- border:
- accent:

Typography:
- hero title:
- section title:
- body:
- line-height:
- weight:

Spacing:
- section padding:
- content max width:
- card/list gap:
- card/list padding:
- text gap:

Shape / elevation:
- radius:
- border:
- shadow:

Layout:
- desktop:
- tablet:
- mobile:

Component:
- selected component:
- interaction state:
- density:
```

## 4. 내 홈페이지에 가져올 것

```text
1.
2.
3.
```

## 5. 내 홈페이지에 가져오지 않을 것

```text
1.
2.
3.
```

## 6. CSS custom property 후보

기존 프로젝트에 이미 비슷한 변수가 있다면 새 이름을 만들기보다 기존 변수를 우선 사용합니다.

```css
:root {
  --color-bg: ;
  --color-surface: ;
  --color-text: ;
  --color-muted: ;
  --color-border: ;
  --color-accent: ;

  --font-size-hero: ;
  --font-size-section-title: ;
  --font-size-body: ;
  --line-height-tight: ;
  --line-height-body: ;

  --space-section: ;
  --space-card-gap: ;
  --space-card-padding: ;

  --radius-card: ;
  --shadow-card: ;
  --layout-max-width: ;
}
```

## 7. Codex 적용 브리프

```text
적용할 영역:

이번에 가져올 요소:

수정 방향:

사용할 토큰:

유지할 것:

하지 않을 것:

검증 기준:
- desktop:
- 390px mobile:
- npm run build:
```

## 8. Before / After 기록

```text
Before 문제:
After 변화:
아직 남은 문제:
다음 수정 후보:
```
