# 원하는 요소만 따오기 템플릿

레퍼런스 사이트를 볼 때 전체를 따라 하지 않고, 내 홈페이지에 필요한 요소만 골라오는 연습용 템플릿입니다.

## 1. 레퍼런스 선택

```text
Reference source: getdesign.md / Refero Styles / designmd.app / 직접 찾은 사이트
Reference URL:
Reference name 또는 style name:
```

## 2. 가져올 요소 하나만 선택

```text
선택한 요소:
- [ ] Hero title scale
- [ ] Navigation treatment
- [ ] Project card framing
- [ ] Posts list density
- [ ] Color role
- [ ] Layout rhythm

왜 이 요소를 고르는가:
내 홈페이지의 어떤 문제를 해결하는가:
```

## 3. 가져올 것과 버릴 것

```text
Bring:
1.
2.
3.

Avoid:
1.
2.
3.
```

예:

```text
Bring:
1. 카드 사이 gap이 넓고 안정적인 점
2. 제목과 설명의 font-weight 대비
3. tag가 보조 정보처럼 보이는 muted color

Avoid:
1. 레퍼런스의 브랜드 색 전체 적용
2. 어두운 배경 전체 복제
3. hover animation과 외부 폰트 추가
```

## 4. 토큰으로 바꾸기

```text
Color token:
Typography token:
Spacing token:
Radius token:
Shadow token:
Layout token:
Component rule:
```

## 5. 내 홈페이지 적용 좌표

```text
URL:
Viewport:
Target:
Problem:
Direction:
Constraint:
Verification:
```

## 6. Codex에게 보낼 최종 문장

```text
@Browser [URL]을 열어 현재 화면을 먼저 확인해줘.

아래 레퍼런스에서 전체가 아니라 선택한 요소 하나만 가져오고 싶어.

Reference:
[URL 또는 DESIGN.md excerpt]

Selected element:
[예: Project card framing]

Token brief:
[Color / Typography / Spacing / Radius / Shadow / Layout / Component rule]

적용 위치:
- URL:
- Viewport:
- Target:

요청:
- 선택한 요소와 관련된 CSS만 최소 수정해줘.
- 기존 콘텐츠 구조와 데이터 구조는 유지해줘.
- 브랜드 고유 이미지, 로고, 전체 색상 톤, 애니메이션은 따라 하지 마.
- 아직 수정하지 말고 현재 CSS 구조에서 어디를 바꿀지 계획만 제안해줘.

검증:
- desktop before/after
- 390px mobile
- npm run build
```
