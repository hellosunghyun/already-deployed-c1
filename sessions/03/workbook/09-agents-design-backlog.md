# 09. AGENTS.md에 디자인 백로그 남기기

## 목표

디자인 수정 기준과 백로그를 AGENTS.md에 남깁니다.

별도 메모가 흩어지면 Codex가 다음 요청에서 맥락을 잃습니다.
3회차에서는 백로그도 AGENTS.md를 활용합니다.

## AGENTS.md에 넣을 섹션

```markdown
## 3회차 디자인 작업 규칙

- 새 프로젝트를 만들지 않고 기존 Astro 홈페이지에서 이어서 작업한다.
- 디자인 수정 전에는 Plan mode 또는 계획 응답을 먼저 사용한다.
- 스크린샷, 브라우저 주석, URL, viewport를 기준으로 Target을 좁힌다.
- 레퍼런스는 전체 복제하지 않고 선택한 요소 하나만 토큰으로 적용한다.
- 새 라이브러리, 외부 font, 무거운 animation은 사용자 승인 없이 추가하지 않는다.
- 수정 후 @브라우저 또는 @Browser로 desktop과 390px 모바일을 확인한다.
- 가능하면 npm run build로 검증한다.

## 3회차 디자인 백로그

- [ ] D-001
  - URL:
  - Viewport:
  - Target:
  - Problem:
  - Direction:
  - Reference:
  - Selected element:
  - Bring:
  - Avoid:
  - Verification:
  - Status: planned
```

## Codex에게 보낼 프롬프트

```text
현재 AGENTS.md에 3회차 디자인 작업 규칙과 디자인 백로그 섹션을 추가하고 싶어.

조건:
- 기존 규칙은 지우지 마.
- 너무 길게 만들지 마.
- 백로그는 오늘 실행할 D-001 하나만 먼저 넣어.
- 레퍼런스 전체 복제 금지, 기존 레포에서 이어서 작업, @브라우저/@Browser 검증 규칙을 포함해.
- 아직 수정하지 말고 추가할 문안만 먼저 보여줘.
```

## Ready Gate

- [ ] AGENTS.md에 3회차 디자인 규칙이 있다.
- [ ] D-001 백로그가 있다.
- [ ] 오늘 실행할 항목이 하나로 좁혀졌다.

## 다음 단계

[10. 플랜 실행하기 →](./10-execute-plan.md)
