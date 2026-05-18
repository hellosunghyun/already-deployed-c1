# 05. AGENTS.md / CLAUDE.md 만들기

## 목표

AI가 프로젝트의 기본 규칙을 잊지 않도록 규칙 파일을 만듭니다.

## 왜 하는가

AI에게 매번 같은 말을 반복하지 않기 위해서입니다. 특히 AI는 사람과 다르게 목표를 **최소한의 수정**으로만 달성하려고 하지 않을 수 있습니다. 때로는 과하게 파일을 바꾸거나, 필요 없는 라이브러리를 설치하거나, 전체 구조를 바꿀 수 있습니다.

그래서 프로젝트 시작 시 규칙을 명확히 남깁니다.

## 도구별 파일 이름

| 도구 | 파일 |
|---|---|
| Codex | `AGENTS.md` |
| Antigravity | `AGENTS.md` |
| Claude Code | `CLAUDE.md` |

> Claude Code는 `AGENTS.md`가 아니라 `CLAUDE.md`를 사용합니다.

## 규칙 파일에 들어갈 내용

- 이 프로젝트는 Astro 개인 홈페이지입니다.
- 배포 목표는 GitHub Pages입니다.
- 새 라이브러리는 승인 없이 설치하지 않습니다.
- 관련 없는 파일은 수정하지 않습니다.
- secret, token, password, API key를 코드에 쓰지 않습니다.
- 삭제 명령은 실행 전에 물어봅니다.
- 변경사항이 생기면 자주 commit합니다.
- commit 메시지는 `feat: 한국어설명` 같은 형태로 작성합니다.

## 왜 자주 commit하나요?

AI와 작업하면 변경 속도가 빠릅니다. 실수했을 때 돌아갈 수 있으려면 변경 단위를 자주 저장해야 합니다.

commit은 작업의 **안전 저장점**입니다.

## 공통 프롬프트

```text
이 프로젝트에서 AI 에이전트가 참고할 규칙 파일을 만들고 싶어.

내가 쓰는 도구는 [여기에 Codex / Claude Code / Antigravity 중 하나 입력]이야.

파일 이름 규칙:
- Codex 또는 Antigravity라면 AGENTS.md를 만들어줘.
- Claude Code라면 CLAUDE.md를 만들어줘.

규칙 파일에는 아래 내용을 포함해줘.

1. 이 프로젝트는 Astro 기반 개인 홈페이지다.
2. 최종 배포 목표는 GitHub Pages의 github.io 주소다.
3. 새 라이브러리는 내 승인 없이 추가하지 않는다.
4. 관련 없는 파일은 수정하지 않는다.
5. secret, token, password, API key를 코드에 쓰지 않는다.
6. 삭제 명령은 실행 전에 반드시 물어본다.
7. 수정 후 변경한 파일과 이유를 설명한다.
8. 가능하면 npm run build로 확인한다.
9. 변경사항이 생기면 자주 commit한다.
10. commit 메시지는 feat: 한국어설명, fix: 한국어설명, chore: 한국어설명, docs: 한국어설명 형태를 사용한다.

먼저 파일 내용을 보여줘.
내가 승인하면 파일을 생성해줘.
```

## 체크박스

- [ ] 내 도구에 맞는 파일 이름을 선택했다.
- [ ] 규칙 파일 초안을 확인했다.
- [ ] GitHub Pages 배포 기준이 들어 있다.
- [ ] 자주 commit하라는 규칙이 들어 있다.
- [ ] secret 금지 규칙이 들어 있다.
- [ ] 파일을 생성했다.

## Ready Gate

다음 단계로 넘어가기 전에 아래가 되어 있어야 합니다.

- Codex / Antigravity 사용자는 `AGENTS.md`가 있습니다.
- Claude Code 사용자는 `CLAUDE.md`가 있습니다.
- 파일 안에 GitHub Pages 배포 기준과 commit 규칙이 들어 있습니다.

## 템플릿

- [AGENTS.md 템플릿](../templates/AGENTS.md)
- [CLAUDE.md 템플릿](../templates/CLAUDE.md)

## 다음 단계

[06. Astro 프로젝트 만들기 →](./06-create-astro-project.md)
