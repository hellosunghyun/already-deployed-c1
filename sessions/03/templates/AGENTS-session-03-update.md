# AGENTS.md 3회차 업데이트 템플릿

아래 문장을 기존 `AGENTS.md`에 필요한 만큼만 추가합니다.
너무 길게 만들지 말고 프로젝트에서 계속 지킬 규칙만 남깁니다.

## 디자인 수정 규칙

- 디자인 수정은 화면 전체가 아니라 특정 `URL`, `viewport`, `target`을 기준으로 한다.
- 레퍼런스는 그대로 복제하지 않고 `color`, `typography`, `spacing`, `radius`, `shadow`, `layout`, `component` 토큰으로 분해해 사용한다.
- getdesign.md, Refero Styles, designmd.app 같은 DESIGN.md 레퍼런스는 필요한 요소만 선택해 참고한다.
- 레퍼런스에서 한 번에 가져올 요소는 기본적으로 1개로 제한한다.
- 프로젝트 루트에 `DESIGN.md`가 있으면 디자인 작업 전 그 파일을 참고하되, 사용자가 지정한 적용 영역 밖으로 확장하지 않는다.
- 스크린샷이나 Codex Browser comment가 있으면 해당 영역을 우선 기준으로 삼는다.
- 수정 전에는 원인 후보와 최소 수정 계획을 먼저 설명한다.
- 사용자가 승인하기 전에는 파일을 수정하지 않는다.
- 새 라이브러리, 외부 폰트, 큰 구조 변경은 사용자 승인 없이 하지 않는다.
- 브랜드 고유 이미지, 로고, 고유 그래픽, 복잡한 애니메이션은 레퍼런스에서 그대로 가져오지 않는다.
- 기존 `src/data/projects.json`, `src/data/posts.json` 같은 데이터 구조는 디자인 수정 과정에서 임의로 바꾸지 않는다.
- 디자인 수정 후에는 desktop과 390px mobile에서 확인한다.
- 가능한 경우 Codex Browser로 렌더링 결과를 확인한다.
- 가능한 경우 `npm run build`로 검증한다.
- commit과 push는 변경사항 요약 후 사용자 승인 뒤 진행한다.

## Codex에게 보낼 업데이트 프롬프트

```text
현재 프로젝트의 AGENTS.md에 3회차 디자인 수정 규칙을 반영하고 싶어.

먼저 현재 AGENTS.md를 읽고,
아래 규칙 중 이미 있는 것과 새로 추가해야 할 것을 나눠줘.

추가하고 싶은 규칙:
- 디자인 수정은 URL, viewport, target을 기준으로 한다.
- 레퍼런스는 그대로 복제하지 않고 color, typography, spacing, radius, shadow, layout, component 토큰으로 분해해 사용한다.
- getdesign.md, Refero Styles, designmd.app 같은 DESIGN.md 레퍼런스는 필요한 요소만 선택해 참고한다.
- 레퍼런스에서 한 번에 가져올 요소는 기본적으로 1개로 제한한다.
- 프로젝트 루트에 DESIGN.md가 있으면 디자인 작업 전 참고한다.
- 스크린샷이나 Codex Browser comment를 기준으로 고칠 영역을 좁힌다.
- 수정 전에는 원인 후보와 최소 수정 계획을 먼저 설명한다.
- 새 라이브러리, 외부 폰트, 큰 구조 변경은 승인 없이 하지 않는다.
- 브랜드 고유 이미지, 로고, 고유 그래픽, 복잡한 애니메이션은 레퍼런스에서 그대로 가져오지 않는다.
- 디자인 수정 후 desktop과 390px mobile에서 확인한다.
- 가능하면 npm run build로 검증한다.
- commit/push는 요약 후 승인 뒤 진행한다.

아직 파일을 수정하지 말고,
먼저 추가할 문장만 제안해줘.
```
