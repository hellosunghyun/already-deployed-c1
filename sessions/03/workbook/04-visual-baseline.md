# 04. 현재 화면 baseline 기록

## 목표

수정 전 화면 상태를 기록합니다.

## 확인할 URL

```text
/
/about
/projects
/posts
```

## Codex에게 보낼 프롬프트

```text
@브라우저 또는 @Browser로 로컬 사이트를 확인해줘.

확인할 URL:
- http://localhost:4321/
- http://localhost:4321/about
- http://localhost:4321/projects
- http://localhost:4321/posts

각 페이지에서 디자인 문제를 1개씩만 찾아줘.
문제는 취향이 아니라 관찰 가능한 말로 써줘.
예: 제목 위계 약함, 카드 간격 좁음, 모바일 줄바꿈 과함, 링크가 눈에 안 띔.

아직 수정하지 마.
```

## baseline 기록 폼

```text
URL:
Viewport:
좋은 점:
문제:
가장 먼저 고칠 영역:
수정 전 스크린샷 위치 또는 브라우저 주석:
```

## Ready Gate

- [ ] 수정 전 문제 1개 이상이 기록됐다.
- [ ] URL과 viewport가 함께 적혀 있다.
- [ ] 아직 코드는 수정하지 않았다.

## 다음 단계

[05. 스크린샷과 브라우저 주석 피드백 →](./05-screenshot-comment-feedback.md)
