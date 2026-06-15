# 레퍼런스 토큰 적용 프롬프트 템플릿

GPT가 레퍼런스 홈페이지나 DESIGN.md에서 설명한 디자인 토큰을 Codex에게 적용시킬 때 쓰는 템플릿입니다.

## 1. GPT에게 먼저 보낼 프롬프트

```text
아래 홈페이지 또는 DESIGN.md 예시를 내 개인 홈페이지의 디자인 레퍼런스로 분석해줘.

Reference source:
[getdesign.md / Refero Styles / designmd.app / 직접 찾은 사이트]

Reference URL 또는 DESIGN.md excerpt:
[입력]

목표:
이 사이트를 그대로 복제하려는 것이 아니라,
내 Astro 개인 홈페이지에 적용할 수 있는 디자인 토큰을 설명받고 싶어.

이번에 가져올 요소는 하나만 고를 거야.
후보:
- Hero title scale
- Navigation treatment
- Project card framing
- Posts list density
- Color role
- Layout rhythm

분석 항목:
- color: background, surface, text, muted, border, accent
- typography: hero title, section title, body, line-height, weight
- spacing: section padding, content width, card/list gap, card/list padding
- radius: card/button radius
- shadow: 사용 여부와 강도
- layout: max-width, grid, mobile 전환
- component: 선택 요소와 관련된 UI 규칙

추가 요청:
- 가져올 점 3개
- 가져오지 않을 점 3개
- 내 홈페이지의 Home hero / Projects card / Posts list / Navigation 중 어디에 적용하면 좋을지

제약:
- 브랜드 고유 이미지, 로고, 고유 그래픽은 복제하지 마.
- 정확한 HEX나 폰트명을 모르면 추정이라고 표시해줘.
- 외부 폰트나 새 라이브러리 추가는 기본적으로 제외해줘.
```

## 2. DESIGN.md 내용을 붙여 넣을 때 프롬프트

```text
아래는 레퍼런스 사이트에서 가져온 DESIGN.md 내용이야.
이 파일 전체를 내 사이트에 복제하지 말고, 내 홈페이지에 적용 가능한 작은 브리프로 줄여줘.

DESIGN.md:
[붙여넣기]

내 사이트:
- Astro 개인 홈페이지
- Home / About / Projects / Posts 구조
- CSS 변수는 global.css의 :root에 있을 수 있음
- 새 라이브러리와 외부 폰트 추가 금지

이번에 가져올 요소:
[Hero title scale / Navigation treatment / Project card framing / Posts list density / Color role / Layout rhythm 중 하나]

출력:
1. 적용 영역
2. 적용할 token 3~5개
3. 유지할 기존 톤
4. 버릴 token
5. CSS variable 후보
6. Codex에게 보낼 작업 지시
7. desktop / 390px mobile 검증 기준
```

## 3. GPT 응답을 줄이는 프롬프트

```text
방금 분석을 Codex에게 줄 수 있는 적용 브리프로 줄여줘.

조건:
- 적용 영역은 1개만 고른다.
- 가져올 요소도 1개만 고른다.
- CSS 변수 후보를 제안한다.
- 기존 사이트 톤을 유지한다.
- 전체 리디자인이 아니라 작은 CSS 수정으로 끝낸다.

출력:
1. 적용 영역
2. 이번에 가져올 요소
3. 적용할 token 3~5개
4. 유지할 기존 톤
5. 하지 않을 것
6. CSS variable 후보
7. Codex에게 보낼 작업 지시
8. desktop / 390px mobile 검증 기준
```

## 4. Codex에게 보낼 적용 프롬프트

```text
@Browser http://localhost:4321/ 을 열어서 현재 화면을 확인해줘.

아래는 GPT가 레퍼런스 홈페이지 또는 DESIGN.md에서 추출한 디자인 토큰 적용 브리프야.
레퍼런스를 그대로 복제하지 말고, 내 홈페이지의 선택 영역에만 반영하고 싶어.

Token application brief:
[붙여넣기]

적용할 영역:
[입력]

이번에 가져올 요소:
[입력]

제약:
- 새 라이브러리 추가 금지
- 외부 폰트 추가 금지
- 브랜드 고유 이미지/로고/그래픽 복제 금지
- 기존 데이터 구조 변경 금지
- 관련 없는 파일 수정 금지
- 전체 리디자인 금지

작업 방식:
1. 아직 파일 수정하지 마.
2. 현재 CSS 구조에서 어떤 변수나 선택자를 활용할지 설명해줘.
3. 수정할 파일 목록을 말해줘.
4. 가장 작은 수정 계획을 제안해줘.
5. 내가 승인하면 진행해줘.

검증:
- desktop에서 before/after 확인
- 390px mobile에서 제목, navigation, card/list 깨짐 확인
- npm run build 실행
```

## 5. 승인 후 프롬프트

```text
좋아. 방금 계획대로 진행해줘.

주의:
- 선택한 영역만 수정해줘.
- token brief에 없는 새 디자인 방향을 임의로 추가하지 마.
- 수정 후 변경한 파일과 이유를 알려줘.
- Codex Browser에서 desktop과 390px mobile 확인 결과를 알려줘.
- npm run build 결과를 알려줘.
```
