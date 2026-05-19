# 2회차 프로젝트 JSON 정보 템플릿

Projects 페이지에 넣을 프로젝트 또는 경험을 JSON 파일로 정리하기 위한 템플릿입니다.
권장 위치는 `src/data/projects.json`입니다.
정식 프로젝트가 아니어도 됩니다. 수업 실습, 개인 학습, 동아리 활동, 문제 해결 경험도 사용할 수 있습니다.

## JSON 구조

```json
[
  {
    "title": "",
    "description": "",
    "role": "",
    "tools": [],
    "result": "",
    "detail": "",
    "slug": ""
  },
  {
    "title": "",
    "description": "",
    "role": "",
    "tools": [],
    "result": "",
    "detail": "",
    "slug": ""
  },
  {
    "title": "",
    "description": "",
    "role": "",
    "tools": [],
    "result": "",
    "detail": "",
    "slug": ""
  }
]
```

## 작성 예시

```json
[
  {
    "title": "첫 개인 홈페이지",
    "description": "Astro와 GitHub Pages로 만든 개인 홈페이지 첫 버전입니다.",
    "role": "Codex에게 계획을 요청하고, 로컬 확인과 배포 검증을 진행했습니다.",
    "tools": ["Astro", "GitHub Pages", "Codex", "Git"],
    "result": "github.io 주소로 열리는 첫 홈페이지를 만들었습니다.",
    "detail": "처음에는 한 페이지짜리 홈페이지였지만, 배포와 확인 과정을 거치며 내 작업을 인터넷에 올리는 흐름을 경험했습니다. 이후 About, Projects, Posts 구조로 확장할 수 있는 출발점이 되었습니다.",
    "slug": "first-homepage"
  }
]
```

## AI에게 보낼 때 붙일 문장

```text
아래 프로젝트 정보는 초안이야.
경력처럼 과장하지 말고, 실제로 한 일과 배운 점이 드러나게 다듬어줘.
프로젝트 정보는 src/data/projects.json 파일에 넣기 좋은 JSON 구조로 정리해줘.
상세 페이지 주소는 JSON에 직접 넣지 말고, slug를 넣은 뒤 화면 코드에서 /projects/{slug} 형태로 만들게 해줘.
카드에 들어갈 문장은 짧고 읽기 쉽게 만들어줘.
카드를 클릭했을 때 볼 수 있는 상세 설명도 3~5문장으로 만들어줘.
나중에 다른 콘텐츠 소스로 바꾸기 쉽도록, 화면 코드에 문장을 직접 흩뿌리지 않는 구조로 제안해줘.
나중에 외부 API 응답을 붙이더라도 원본 응답을 화면에 바로 넣지 않고, 이 JSON 구조로 변환해서 쓰는 방식으로 설명해줘.
```
