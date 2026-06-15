# Codex Browser comment 프롬프트 모음

## 1. 로컬 화면 열기

```text
@Browser http://localhost:4321 을 열어줘.
Home / About / Projects / Posts 링크가 보이는지 확인해줘.
아직 파일은 수정하지 마.
```

## 2. 주석 영역 분석

```text
@Browser 내가 comment로 표시한 영역을 기준으로 봐줘.

요청:
1. 이 영역이 어떤 페이지의 어떤 요소인지 설명해줘.
2. 관련 CSS selector 후보를 찾아줘.
3. 적용된 font-size, line-height, margin, padding, gap, max-width를 확인해줘.
4. 문제 원인 후보를 2~3개로 정리해줘.
5. 아직 수정하지 말고 최소 수정 계획만 제안해줘.
```

## 3. Home hero 주석 기반 요청

```text
@Browser Home hero에 남긴 comment를 기준으로 봐줘.

문제:
제목과 소개 문장 사이의 위계는 괜찮지만 첫 화면에서 다음 행동이 약해 보여.

방향:
- 제목 크기는 유지하거나 조금만 조정
- 소개 문장 max-width와 line-height 정리
- About / Projects / Posts 링크를 더 명확하게
- 모바일 390px에서 제목 줄바꿈 확인

제약:
- 새 라이브러리 추가 금지
- 외부 폰트 추가 금지
- 색상 톤 유지
- 아직 수정하지 말고 계획 먼저
```

## 4. Projects 카드 주석 기반 요청

```text
@Browser /projects에서 내가 표시한 카드 영역을 봐줘.

문제:
카드 제목, 설명, 태그, 결과 문장이 모두 비슷한 무게로 보여서 훑기 어렵다.

방향:
- 제목 위계 강화
- 설명과 role/result는 보조 정보처럼 정리
- 태그는 작고 정돈되게
- 카드 간격과 내부 padding 균형 맞추기

제약:
- projects.json 구조 유지
- 상세 페이지 구조 크게 변경 금지
- 새 라이브러리 추가 금지
- 먼저 계획만
```

## 5. 모바일 확인 요청

```text
@Browser 아래 viewport로 확인해줘.

- 390x844
- 768x1024
- 1440x900

확인할 것:
1. 가로 스크롤이 생기는지
2. Navigation이 깨지는지
3. Home 제목이 4줄 이상으로 깨지는지
4. Projects 카드가 읽기 쉬운지
5. Posts 목록이 너무 빽빽하지 않은지

문제가 있으면 바로 수정하지 말고 문제 목록과 최소 수정 계획을 먼저 말해줘.
```

## 6. 수정 후 검증 요청

```text
@Browser 수정 결과를 다시 확인해줘.

확인할 URL:
- /
- /about
- /projects
- /posts

확인할 viewport:
- 390x844
- 1440x900

보고 형식:
1. 확인한 URL
2. 수정이 반영된 영역
3. 좋아진 점
4. 아직 남은 문제
5. build 전에 고쳐야 할 문제
```


## 레퍼런스 토큰 적용 프롬프트

```text
@Browser http://localhost:4321/ 을 열어서 현재 화면을 먼저 확인해줘.

아래는 GPT가 다른 홈페이지 레퍼런스에서 추출한 디자인 토큰 브리프야.
레퍼런스를 그대로 복제하지 말고, 내 홈페이지의 선택한 영역에만 적용해줘.

Token brief:
[붙여넣기]

적용할 영역:
[Home hero / Projects card / Posts list / Navigation 중 하나]

요청:
1. 현재 CSS 구조에서 이 토큰을 어디에 매핑할지 설명해줘.
2. 기존 :root CSS 변수가 있으면 가능한 한 그것을 활용해줘.
3. 전체 리디자인하지 말고 선택 영역만 최소 수정해줘.
4. 새 라이브러리와 외부 폰트는 추가하지 마.
5. 먼저 수정 계획만 말해줘.
6. 내가 승인하면 수정해줘.

검증:
- desktop viewport
- 390px mobile viewport
- npm run build
```
