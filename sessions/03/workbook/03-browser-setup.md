# 03. 브라우저 활성화와 태그 확인

## 목표

Codex가 로컬 화면을 함께 볼 수 있게 브라우저 기능을 켭니다.

## 태그 이름

```text
한국어 UI: @브라우저
영어 UI: @Browser
```

둘 중 자동완성되는 것을 사용합니다.

## 먼저 테스트

```text
@브라우저 http://localhost:4321/ 을 열어서 Home 화면이 보이는지 확인해줘.
```

영어 UI라면:

```text
@Browser http://localhost:4321/ 을 열어서 Home 화면이 보이는지 확인해줘.
```

## 태그가 안 될 때 설정

설정에서 브라우저를 켭니다.

```text
설정 → 통합 → 브라우저
```

권장값:

```text
브라우저: 켬
주석 스크린샷: 항상 포함
승인: 항상 허용 또는 매번 확인
```

참고 화면: [브라우저 설정 스크린샷](../assets/codex-browser-settings.png)

## Ready Gate

- [ ] `@브라우저` 또는 `@Browser`가 자동완성된다.
- [ ] localhost 화면을 열 수 있다.
- [ ] Codex가 화면 상태를 말로 설명했다.

## 다음 단계

[04. 현재 화면 baseline 기록 →](./04-visual-baseline.md)
