# 2회차 글 목록 JSON 정보 템플릿

Posts 페이지에 넣을 샘플 글 목록을 JSON 파일로 정리하는 템플릿입니다.
권장 위치는 `src/data/posts.json`입니다.
오늘은 실제 블로그 시스템이나 외부 API를 붙이지 않습니다.

## JSON 구조

```json
[
  {
    "title": "",
    "slug": "",
    "date": "",
    "summary": "",
    "tags": []
  },
  {
    "title": "",
    "slug": "",
    "date": "",
    "summary": "",
    "tags": []
  }
]
```

## 작성 예시

```json
[
  {
    "title": "첫 배포를 하며 배운 것",
    "slug": "first-deploy-reflection",
    "date": "2026-05-19",
    "summary": "Astro와 GitHub Pages로 개인 홈페이지를 처음 배포하며 배운 점을 정리합니다.",
    "tags": ["Astro", "GitHub Pages", "회고"]
  },
  {
    "title": "AI에게 코딩을 맡길 때 필요한 맥락",
    "slug": "ai-coding-context",
    "date": "2026-05-19",
    "summary": "좋은 프롬프트가 왜 필요한지, 계획과 검증을 어떻게 요청하는지 정리합니다.",
    "tags": ["Codex", "AI", "작업기록"]
  }
]
```

## AI에게 보낼 때 붙일 문장

```text
이 글 목록은 2회차용 샘플 데이터야.
지금은 외부 API를 붙이지 말고, src/data/posts.json 파일의 JSON 정보로 목록을 보여주는 구조만 만들어줘.
token, secret, API key는 만들거나 코드에 넣지 마.
나중에 다른 콘텐츠 소스로 바꿔도 화면 코드를 크게 고치지 않도록, 정보 파일과 화면 Component를 분리해줘.
나중에 외부 API 응답을 붙이더라도 원본 응답을 화면에 바로 쓰지 말고, title, slug, date, summary, tags로 정리한 JSON 구조로 변환해서 쓰는 방식으로 설명해줘.
```
