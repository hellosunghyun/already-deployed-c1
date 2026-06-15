# 05. 레퍼런스 홈페이지와 디자인 토큰 브리프 만들기

## 목표

마음에 드는 다른 홈페이지나 DESIGN.md 레퍼런스 라이브러리에서 **원하는 요소만** 골라, GPT에게 디자인 토큰으로 설명하게 한 뒤, Codex가 실행할 수 있는 작은 수정 지시로 바꿉니다.

## 왜 하는가

레퍼런스를 "이 사이트처럼 해줘"라고 요청하면 AI가 색, 레이아웃, 애니메이션, 이미지, 브랜드 분위기를 과하게 따라 할 수 있습니다.
3회차의 목표는 복제가 아니라 **번역**입니다.

```text
레퍼런스 화면 또는 DESIGN.md
→ 원하는 요소 1개 선택
→ 디자인 토큰 설명
→ 내 홈페이지용 요구사항
→ Codex 수정
→ Browser 검증
```

## 오늘의 핵심 규칙

```text
레퍼런스 전체를 가져오지 않습니다.
원하는 요소만 하나 고릅니다.
그 요소를 토큰으로 설명합니다.
내 홈페이지의 한 영역에만 적용합니다.
```

예:

```text
나쁜 요청:
이 사이트처럼 만들어줘.

좋은 요청:
이 레퍼런스의 hero title 크기 리듬과 subtitle 간격만 가져와서,
내 Home hero의 제목과 소개 문장 사이 위계를 개선해줘.
색상, 로고, 이미지, 애니메이션은 따라 하지 마.
```

## 디자인 토큰을 쉽게 이해하기

디자인 토큰은 반복해서 쓰는 시각 규칙에 붙인 이름표입니다.
오늘은 복잡한 디자인 시스템 표준을 외우지 않고, 아래 정도로만 사용합니다.

```text
color      = 배경, 본문, 보조 텍스트, 강조색, 테두리
font       = 제목 크기, 본문 크기, 굵기, 줄간격
spacing    = 섹션 여백, 카드 간격, 내부 padding
radius     = 모서리 둥글기
shadow     = 그림자 강도
layout     = 최대 너비, grid 열 수, 모바일 전환 기준
component  = 버튼, 카드, 링크, 태그 같은 반복 요소의 규칙
```

예를 들어 레퍼런스에서 본 것을 이렇게 바꿉니다.

```text
레퍼런스 감상:
깔끔하고 전문적으로 보여요.

토큰 설명:
흰 배경, 낮은 채도의 보조 텍스트, 큰 제목, 넓은 섹션 여백, 얇은 border, 약한 shadow.

내 홈페이지 요구사항:
Home hero의 제목 크기를 clamp로 정리하고,
Projects 카드는 강한 shadow 대신 얇은 border와 넓은 gap을 사용한다.
```

## 0단계. 참고할 수 있는 사이트

레퍼런스는 직접 찾은 홈페이지 URL을 써도 되고, 아래처럼 DESIGN.md나 AI-readable design system을 모아둔 사이트를 써도 됩니다.

| 사이트 | 수업에서 쓰는 방식 | 좋은 사용 예 |
|---|---|---|
| [getdesign.md](https://getdesign.md/) | 브랜드/제품별 DESIGN.md 분석을 둘러보고 스타일 방향을 고릅니다. | Apple의 여백감, Linear의 어두운 UI 밀도, Notion의 warm minimal 톤처럼 큰 방향을 잡을 때 |
| [Refero Styles](https://styles.refero.design/) | 실제 제품 화면 기반의 AI-readable style을 탐색합니다. | Hero, dashboard, card, onboarding, docs 같은 화면 유형별 레퍼런스를 찾을 때 |
| [designmd.app](https://designmd.app/) | ready-to-use DESIGN.md와 format 설명을 참고합니다. | 디자인 토큰을 `colors`, `typography`, `spacing`, `components`처럼 구조화하는 연습을 할 때 |
| 직접 찾은 홈페이지 | 원본 화면을 보고 GPT에게 토큰 추출을 시킵니다. | 마음에 드는 개인 홈페이지, 포트폴리오, 작은 SaaS 랜딩 페이지가 있을 때 |

## 0.5단계. 원하는 요소만 따오기 연습

레퍼런스를 고르면 먼저 아래 중 **하나만** 선택합니다.

```text
A. Hero title scale: 첫 화면 제목 크기, 줄간격, subtitle 간격
B. Navigation treatment: 로고/메뉴 간격, 링크 hover/focus, 모바일 줄바꿈
C. Project card framing: 카드 border, radius, padding, gap, shadow 강도
D. Posts list density: 날짜/태그/제목/요약의 크기 차이와 목록 간격
E. Color role: background, surface, muted text, accent의 역할 분리
F. Layout rhythm: max-width, section padding, grid column, breakpoint
```

한 번에 두 개 이상 가져오고 싶어도, 첫 수정은 하나만 고릅니다.

```text
이번에 가져올 요소:
가져올 이유:
내 홈페이지 적용 위치:
가져오지 않을 요소:
```

예:

```text
이번에 가져올 요소: Project card framing
가져올 이유: 내 Projects 카드가 정보는 있지만 덩어리감이 약함
내 홈페이지 적용 위치: /projects 카드 목록
가져오지 않을 요소: 레퍼런스의 어두운 배경, 로고, hover animation, 외부 폰트
```

## 1단계. 레퍼런스 하나 선택하기

레퍼런스는 개인 홈페이지, 포트폴리오, 작은 서비스 랜딩 페이지, DESIGN.md 예시 중 하나를 고릅니다.
너무 화려한 사이트보다, 내 홈페이지에 바로 적용할 수 있는 구조가 보이는 사이트가 좋습니다.

기록할 것:

```text
Reference source: getdesign.md / Refero Styles / designmd.app / 직접 찾은 사이트
Reference URL:
어떤 페이지 또는 style인지:
마음에 든 이유:
이번에 가져올 요소 1개:
내 홈페이지에서 적용하고 싶은 URL/영역:
절대 따라하지 않을 점:
```

## 2단계. GPT에게 디자인 토큰 설명시키기

레퍼런스 URL만 던지고 끝내지 않습니다. GPT가 무엇을 봐야 하는지 지정합니다.

```text
아래 홈페이지 또는 DESIGN.md 레퍼런스를 개인 홈페이지 디자인 레퍼런스로 분석해줘.

Reference source:
[getdesign.md / Refero Styles / designmd.app / 직접 찾은 사이트]

Reference URL:
[여기에 입력]

분석 목적:
이 사이트를 그대로 복제하려는 것이 아니라,
내 Astro 개인 홈페이지에 적용할 수 있는 디자인 토큰과 레이아웃 규칙을 추출하려고 해.

이번에 가져올 요소는 하나만 고를 거야.
후보 요소:
- hero title scale
- navigation treatment
- project card framing
- posts list density
- color role
- layout rhythm

분석해줘야 할 항목:
1. 전체 인상은 한 문장으로만 설명
2. 이번에 가져올 요소 추천 1개와 이유
3. color token 후보
   - background
   - surface
   - text
   - muted text
   - border
   - accent
4. typography token 후보
   - hero title size
   - section title size
   - body size
   - line-height
   - font-weight 대비
5. spacing token 후보
   - section padding
   - card/list gap
   - card/list padding
   - title과 설명 사이 간격
6. shape/elevation token 후보
   - border radius
   - border 사용 방식
   - shadow 사용 여부
7. layout token 후보
   - max-width
   - grid column
   - mobile 전환 방식
8. 내 홈페이지에 가져오면 좋은 점 3개
9. 가져오면 안 되는 점 3개

제약:
- 정확한 브랜드 복제나 로고/이미지 복제는 제안하지 마.
- 색상 HEX가 보이지 않으면 추정이라고 표시해줘.
- 외부 폰트 추가, 무거운 애니메이션, 새 라이브러리 추가는 기본적으로 제외해줘.
- 결과는 아래 형식의 token brief로 정리해줘.

출력 형식:
Reference summary:
Selected element:
Token brief:
- color:
- typography:
- spacing:
- radius:
- shadow:
- layout:
Bring:
Avoid:
Apply to my site:
```

## 3단계. DESIGN.md가 있는 경우 GPT에게 설명시키기

getdesign.md, Refero Styles, designmd.app에서 DESIGN.md 내용을 볼 수 있거나 복사할 수 있다면, URL만 주는 것보다 DESIGN.md 일부를 함께 붙여 넣는 편이 좋습니다.

```text
아래는 레퍼런스의 DESIGN.md 또는 디자인 시스템 설명이야.
그대로 적용하지 말고, 내 Astro 개인 홈페이지에서 쓸 수 있는 작은 token brief로 줄여줘.

DESIGN.md excerpt:
[여기에 붙여넣기]

내 홈페이지 현재 상태:
- Astro 개인 홈페이지
- Home / About / Projects / Posts 구조
- CSS 변수는 global.css의 :root에 있을 수 있음
- 새 라이브러리와 외부 폰트 추가 금지

이번에 가져올 요소:
[hero title scale / navigation treatment / project card framing / posts list density / color role / layout rhythm 중 하나]

요청:
1. 이 DESIGN.md에서 이번 요소와 관련 있는 토큰만 골라줘.
2. 내 사이트에 맞지 않는 브랜드 고유 토큰은 버려줘.
3. 색상은 exact copy가 아니라 role 중심으로 바꿔줘.
4. CSS custom property 후보를 제안해줘.
5. Codex에게 줄 수 있는 적용 지시로 줄여줘.
6. 아직 코드는 작성하지 마.

출력 형식:
- 적용할 영역:
- 가져올 토큰:
- 유지할 기존 톤:
- 버릴 토큰:
- CSS variable 후보:
- Codex에게 보낼 수정 지시:
- Browser 검증 기준:
```

## 4단계. 레퍼런스 토큰을 내 홈페이지용으로 줄이기

GPT가 뽑은 토큰을 전부 쓰지 않습니다. 오늘은 1개 영역에 적용할 토큰만 고릅니다.

```text
방금 분석한 token brief를 내 홈페이지에 적용 가능한 작은 수정으로 줄여줘.

내 홈페이지 현재 상태:
- Astro 개인 홈페이지
- Home / About / Projects / Posts 구조
- 기존 global.css에 CSS 변수가 있을 수 있음
- 새 라이브러리 추가 금지

오늘 적용할 후보 영역:
- Home hero
- Projects card
- Posts list
- Navigation

요청:
1. 오늘 90분 안에 적용 가능한 토큰만 골라줘.
2. 적용 우선순위를 P1 / P2로 나눠줘.
3. 각 토큰을 CSS custom property 이름으로 바꿔줘.
4. 기존 CSS 변수와 충돌하지 않게 제안해줘.
5. 정확한 색상 복제보다 역할 중심으로 제안해줘.
6. 아직 코드는 수정하지 말고, 적용 브리프만 만들어줘.

출력 형식:
- 적용할 영역:
- 가져올 토큰:
- 유지할 기존 톤:
- 버릴 토큰:
- CSS variable 후보:
- Codex에게 보낼 수정 지시:
- Browser 검증 기준:
```

## 5단계. Codex에게 적용시키기

이 단계에서 Codex에게 바로 전체 리디자인을 맡기지 않습니다.
반드시 적용 영역, 토큰, 제약, 검증 기준을 함께 줍니다.

```text
@Browser http://localhost:4321/ 을 열어 현재 화면을 먼저 확인해줘.

아래는 GPT가 레퍼런스 홈페이지 또는 DESIGN.md에서 추출한 디자인 토큰 브리프야.
이 레퍼런스를 그대로 복제하지 말고, 내 홈페이지의 [적용 영역]에만 작은 단위로 반영하고 싶어.

Reference token brief:
[여기에 GPT가 정리한 token brief 붙여넣기]

적용할 영역:
[예: Home hero / Projects card / Posts list / Navigation]

이번에 가져올 요소:
[예: project card framing만 / hero title scale만]

적용 방향:
- color는 기존 톤을 유지하되 역할을 더 분명하게
- typography는 제목과 설명의 위계를 더 분명하게
- spacing은 섹션과 카드 사이 리듬을 정리
- radius/shadow는 과하지 않게

제약:
- 새 라이브러리 추가 금지
- 외부 폰트 추가 금지
- 브랜드 로고, 이미지, 고유 그래픽 복제 금지
- 기존 데이터 구조 변경 금지
- 관련 없는 페이지 대규모 수정 금지
- 전체 리디자인 금지
- 먼저 원인 후보와 최소 수정 계획만 설명

검증:
- Codex Browser에서 desktop과 390px 모바일 확인
- 변경 전/후 차이 설명
- npm run build 실행

아직 파일을 수정하지 말고,
1. 현재 CSS 구조에서 토큰을 어디에 매핑할지
2. 수정할 파일 목록
3. 가장 작은 수정 계획
을 먼저 제안해줘.
```

승인 후에는 이렇게 말합니다.

```text
좋아. 방금 계획대로 진행해줘.
단, 한 번에 전체 디자인을 바꾸지 말고 [적용 영역]만 수정해줘.
수정 후 Codex Browser에서 desktop과 390px 모바일을 확인하고, 변경 파일과 이유를 설명해줘.
```

## 선택 실습 A. Hero title scale만 가져오기

```text
Reference에서 hero title scale만 가져오고 싶어.
색상, 이미지, 레이아웃 전체는 따라 하지 마.

내 사이트 적용 위치:
- URL: /
- Target: Home hero h1과 intro

Codex에게 적용할 방향:
- h1은 clamp로 desktop/mobile에서 자연스럽게 조절
- intro는 max-width와 line-height 조정
- 제목과 intro 사이 간격만 정리
- 기존 색상은 유지
```

## 선택 실습 B. Project card framing만 가져오기

```text
Reference에서 project card framing만 가져오고 싶어.
어두운 배경, 브랜드 색, 애니메이션은 따라 하지 마.

내 사이트 적용 위치:
- URL: /projects
- Target: project card list

Codex에게 적용할 방향:
- card gap과 padding 정리
- border/radius/shadow 강도만 조정
- 제목/설명/태그의 위계 정리
- projects.json 데이터 구조는 유지
```

## 좋은 결과 예시

```text
Reference token:
- typography: 큰 hero title, 짧은 subtitle, 강한 font-weight 대비
- spacing: section padding이 넓고 card gap이 여유 있음
- surface: 흰 배경 위에 연한 회색 카드

내 홈페이지 적용:
- Home hero h1에 clamp(44px, 8vw, 72px) 적용
- .intro max-width를 680px로 제한
- Projects grid gap을 24px에서 32px로 조정
- 카드 shadow는 추가하지 않고 border와 background만 정리

하지 않을 것:
- 레퍼런스의 어두운 배경 전체 복제
- 외부 폰트 추가
- 스크롤 애니메이션 추가
```

## 체크박스

- [ ] 레퍼런스 URL 또는 DESIGN.md 예시를 1개 이상 준비했다.
- [ ] getdesign.md / Refero Styles / designmd.app 중 하나를 참고해봤다.
- [ ] 가져올 요소를 1개로 좁혔다.
- [ ] GPT에게 디자인 토큰 설명을 요청했다.
- [ ] color / typography / spacing / radius / shadow / layout으로 분해했다.
- [ ] 가져올 토큰과 버릴 토큰을 나눴다.
- [ ] 내 홈페이지의 적용 영역을 1개로 좁혔다.
- [ ] Codex에게 보낼 적용 브리프를 만들었다.
- [ ] 전체 복제를 요청하지 않았다.

## Ready Gate

다음 단계로 넘어가기 전에 아래가 되어 있어야 합니다.

- 레퍼런스에서 가져올 디자인 토큰이 구체적입니다.
- 가져올 요소가 1개로 좁혀졌습니다.
- 내 홈페이지에서 적용할 위치가 정해졌습니다.
- 따라하지 않을 점이 분명합니다.
- Codex가 바로 수정하기 전에 계획을 먼저 제안하게 하는 프롬프트가 있습니다.

## 템플릿

- [레퍼런스 분석 템플릿](../templates/reference-analysis-template.md)
- [레퍼런스 디자인 토큰 브리프 템플릿](../templates/reference-design-token-brief.md)
- [레퍼런스 토큰 적용 프롬프트 템플릿](../templates/reference-token-application-prompt.md)
- [원하는 요소만 따오기 템플릿](../templates/selective-reference-element-brief.md)

## 다음 단계

[06. 디자인 수정 backlog 만들기 →](./06-design-change-backlog.md)
