# 08. 원하는 요소만 하나 선택하기

## 목표

레퍼런스에서 딱 하나만 가져옵니다.

## 선택지

```text
Hero title scale
Navigation treatment
Project card framing
Posts list density
Color role
Layout rhythm
```

## 금지

```text
전체 색상 복제
로고 / 이미지 복제
브랜드 고유 그래픽 복제
무거운 animation 추가
외부 font 무단 추가
새 UI 라이브러리 설치
```

## 선택 브리프

```text
Reference:
Selected element:
Apply to:
Bring:
Avoid:
Allowed files:
Verification:
```

예시:

```text
Reference: styles.refero.design의 Linear 계열 dark command deck
Selected element: Project card framing
Apply to: /projects 카드 목록
Bring: 카드 gap, muted text 위계, 얇은 border
Avoid: 전체 dark background, 로고, animation, 외부 font
Allowed files: src/pages/projects.astro, src/styles/global.css
Verification: @브라우저 또는 @Browser로 desktop과 390px 확인, npm run build
```

## 다음 단계

[09. AGENTS.md에 디자인 백로그 남기기 →](./09-agents-design-backlog.md)
