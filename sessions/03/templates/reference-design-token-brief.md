# 레퍼런스 디자인 토큰 브리프

## 기록 양식

```text
Where (URL + Viewport): [적용할 내 페이지와 화면 크기]
Target: [입력]
Evidence: [현재 화면과 레퍼런스 스크린샷 경로 또는 첨부명]
Problem: [입력]
Direction: [입력]
Constraint: [입력]

Reference URL: [입력]
Selected element: [입력]
Bring: [입력]
Avoid: [입력]

Color: [입력]
Typography: [입력]
Spacing: [입력]
Radius: [입력]
Border: [입력]
Shadow: [입력]
Component: [입력]

Allowed files: [파일 경로 목록]
Verification: [현재 desktop, 390x844, npm run build]
```

## 토큰 분석 요청문

```text
아래 레퍼런스에서 선택한 요소 하나만 내 Astro 홈페이지에 적용할 수 있는 디자인 토큰으로 설명해줘.

Where (URL + Viewport): [입력]
Target: [입력]
Evidence: [현재 화면과 레퍼런스 스크린샷 경로 또는 첨부명]
Problem: [입력]
Direction: [입력]
Constraint: [입력]

Reference URL: [입력]
Selected element: [입력]

응답 형식:
- Bring
- Avoid
- Color
- Typography
- Spacing
- Radius
- Border
- Shadow
- Component
- 내 기존 CSS 변수 또는 스타일에 적용하는 방법
- Allowed files 후보
- 현재 desktop, 390x844, npm run build 검증 방법

조건:
- 레퍼런스 전체를 복제하지 마.
- 로고, 이미지, 브랜드 고유 그래픽을 가져오지 마.
- 새 라이브러리, 외부 font, 무거운 animation을 제안하지 마.
- 아직 파일을 수정하지 마.
```
