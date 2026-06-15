# 13. commit / push / deploy 확인

## 목표

3회차 디자인 수정 결과를 GitHub에 올리고 GitHub Pages 반영 상태를 확인합니다.

## 왜 하는가

로컬에서 좋아 보이는 것은 최종 결과가 아닙니다.
수정 결과가 GitHub에 저장되고, Pages 주소에서 열리는지 확인해야 3회차가 끝납니다.

## Codex에게 보낼 프롬프트

```text
3회차 디자인 수정 결과를 commit하고 GitHub Pages 반영까지 확인하고 싶어.

먼저 확인할 것:
1. git status
2. 변경 파일 목록
3. secret, token, password, API key 같은 민감한 값 포함 여부
4. package-lock.json 등 예상하지 못한 변경 여부
5. npm run build 성공 여부
6. remote가 GitHub 저장소를 가리키는지
7. 현재 branch가 배포 대상 branch인지

작업 방식:
- 아직 commit하지 마.
- 아직 push하지 마.
- 먼저 변경사항 요약과 추천 commit 메시지를 알려줘.
- 내가 승인하면 commit을 만들어줘.
- commit 후 push를 진행해줘.
- push 후 GitHub Actions 또는 Pages 상태를 확인하는 방법을 알려줘.

추천 commit 메시지:
- feat: 홈 히어로 시각 위계 개선
- feat: 프로젝트 카드 디자인 정리
- fix: 모바일 내비게이션 줄바꿈 개선
- fix: 접근성 focus 스타일 보강
- docs: 3회차 디자인 수정 기록 추가
```

## 승인 후 프롬프트

```text
좋아. 방금 요약한 변경사항을 commit하고 push해줘.

주의:
- 민감한 값이 있으면 commit하지 말고 멈춰줘.
- 관련 없는 파일이 섞여 있으면 먼저 알려줘.
- push 후 GitHub Pages 확인 URL과 Actions 확인 위치를 알려줘.
```

## 체크박스

- [ ] `git status`를 확인했다.
- [ ] 변경 파일 목록을 확인했다.
- [ ] 민감한 값이 없는지 확인했다.
- [ ] build 결과를 확인했다.
- [ ] commit 메시지를 정했다.
- [ ] commit을 만들었다.
- [ ] push했다.
- [ ] GitHub Pages 또는 Actions 상태를 확인했다.

## Ready Gate

오늘 마무리 전에 아래 중 하나 이상이 남아 있으면 충분합니다.

- GitHub에 3회차 변경사항이 올라갔습니다.
- 아직 push하지 못했다면 `git status` 결과가 있습니다.
- build 성공 또는 실패 로그가 있습니다.
- GitHub Actions 실패 화면이나 Pages 반영 상태가 기록되어 있습니다.

## 다음 단계

[14. 결과 기록과 4회차 준비 →](./14-record-result-homework.md)
