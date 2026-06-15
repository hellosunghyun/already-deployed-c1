# 레퍼런스 분석 템플릿

레퍼런스를 그대로 베끼지 않고 내 홈페이지 요구사항과 디자인 토큰 브리프로 바꾸기 위한 템플릿입니다.

## 참고 가능한 사이트

| 사이트 | 메모 |
|---|---|
| [getdesign.md](https://getdesign.md/) | 브랜드/제품별 DESIGN.md 분석을 둘러볼 때 |
| [Refero Styles](https://styles.refero.design/) | 실제 제품 화면 기반 AI-readable style을 볼 때 |
| [designmd.app](https://designmd.app/) | DESIGN.md 형식과 ready-to-use style을 볼 때 |
| 직접 찾은 홈페이지 | 원본 화면을 보고 GPT에게 토큰 추출을 시킬 때 |

## 레퍼런스 기본 정보

```text
Reference source: getdesign.md / Refero Styles / designmd.app / 직접 찾은 사이트
Reference URL:
어떤 페이지 또는 style인지:
마음에 든 이유:
내 홈페이지에 적용하고 싶은 페이지/영역:
절대 따라하지 않을 점:
```

## 원하는 요소만 선택하기

아래 중 이번 수정에 가져올 요소를 **하나만** 고릅니다.

```text
선택한 요소:
- [ ] Hero title scale
- [ ] Navigation treatment
- [ ] Project card framing
- [ ] Posts list density
- [ ] Color role
- [ ] Layout rhythm

가져올 이유:
내 홈페이지 적용 위치:
가져오지 않을 요소:
```

## GPT에게 분석시킬 질문

```text
이 홈페이지 또는 DESIGN.md 레퍼런스를 디자인 토큰 관점으로 분석해줘.
전체 복제가 아니라 내 개인 홈페이지에 적용 가능한 시각 규칙만 뽑고 싶어.

Reference source:
[입력]

Reference URL 또는 DESIGN.md excerpt:
[입력]

이번에 가져올 요소:
[Hero title scale / Navigation treatment / Project card framing / Posts list density / Color role / Layout rhythm 중 하나]

분석 항목:
- color: background, surface, text, muted, border, accent
- typography: hero title, section title, body, line-height, weight
- spacing: section padding, card/list gap, card/list padding, title/description gap
- radius: card/button radius
- shadow: shadow 사용 여부와 강도
- layout: max-width, grid column, mobile breakpoint
- component: 이번에 가져올 요소와 관련된 반복 UI 규칙

각 항목은 추정이면 추정이라고 표시해줘.
브랜드 고유 이미지, 로고, 복잡한 애니메이션, 외부 폰트 복제는 제외해줘.
가져올 것 3개와 가져오지 않을 것 3개를 나눠줘.
```

## Token brief

```text
Reference summary:
Selected element:

Color tokens:
- background:
- surface:
- text:
- muted:
- border:
- accent:

Typography tokens:
- hero title:
- section title:
- body:
- line-height:
- weight contrast:

Spacing tokens:
- section padding:
- card/list gap:
- card/list padding:
- title/description gap:

Shape / elevation:
- radius:
- border:
- shadow:

Layout tokens:
- max-width:
- grid:
- mobile:

Component rule:
- selected component:
- what to bring:
- what to avoid:
```

## 가져올 점

```text
1.
2.
3.
```

예:

```text
1. 첫 화면에서 제목과 설명의 크기 차이가 분명함
2. 카드 사이 간격이 넓어서 읽기 편함
3. 모바일에서 제목 크기가 자연스럽게 줄어듦
```

## 따라하지 않을 점

```text
1.
2.
3.
```

예:

```text
1. 무거운 스크롤 애니메이션
2. 내 콘텐츠와 맞지 않는 어두운 배경 전체 적용
3. 브랜드 고유 이미지와 로고 스타일
```

## 요구사항으로 변환

| 레퍼런스에서 본 것 | 토큰 | 내 홈페이지 적용 위치 | 실제 요구사항 |
|---|---|---|---|
| 제목이 크지만 모바일에서 자연스럽게 줄어듦 | typography.hero | Home hero | 제목에 clamp 또는 모바일 media query 적용 |
| 카드 간격이 넓음 | spacing.card-gap | Projects | grid gap 조정 |
| 보조 정보가 옅음 | color.muted | Posts | 날짜와 태그 색상/크기 낮추기 |

## Codex에게 보낼 문장

```text
아래 token brief를 기준으로 내 홈페이지의 [영역]만 수정해줘.
레퍼런스를 그대로 복제하지 말고, 선택한 디자인 토큰만 반영해줘.

Token brief:
[붙여넣기]

적용할 영역:
[입력]

이번에 가져올 요소:
[입력]

제약:
- 새 라이브러리 추가 금지
- 외부 폰트 추가 금지
- 브랜드 고유 이미지/로고/애니메이션 복제 금지
- 전체 색상 톤은 유지
- 기존 데이터 구조 유지
- 전체 리디자인 금지

아직 파일을 수정하지 말고 적용 가능한 작은 수정 계획만 제안해줘.
```
