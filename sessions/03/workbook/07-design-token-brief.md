# 07. GPT에게 디자인 토큰 설명시키기

## 목표

레퍼런스의 느낌을 Codex가 실행 가능한 디자인 토큰으로 바꿉니다.

## 디자인 토큰은 이렇게 봅니다

```text
Color: 배경, 본문, 보조 텍스트, 강조색, 테두리
Typography: 제목 크기, 본문 크기, 굵기, 줄간격
Spacing: 섹션 여백, 카드 gap, padding
Shape: radius, border
Elevation: shadow
Layout: max-width, grid, 모바일 전환점
```

## GPT에게 보낼 프롬프트

```text
아래 레퍼런스 홈페이지를 분석해서 디자인 토큰으로 설명해줘.

Reference URL: [붙여넣기]
내 홈페이지 적용 위치: [예: /projects 카드 목록]
선택한 요소: [예: card framing]

조건:
- 레퍼런스 전체를 복제하지 마.
- 선택한 요소 하나만 분석해.
- Color, Typography, Spacing, Shape, Elevation, Layout으로 나눠줘.
- 내 Astro 개인 홈페이지에 적용할 수 있는 CSS 변수 또는 기존 global.css 규칙으로 번역해줘.
- 가져올 것과 가져오지 않을 것을 분리해줘.
```

## 결과물

```text
Selected element:
Bring:
Avoid:
Token brief:
내 홈페이지 적용 지시:
검증 방법:
```

## 다음 단계

[08. 원하는 요소만 하나 선택하기 →](./08-selective-element.md)
