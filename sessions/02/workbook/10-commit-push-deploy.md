# 10. commit / push / deploy 확인

## 목표

2회차 변경사항을 GitHub에 올리고 GitHub Pages 반영 상태를 확인합니다.

## 왜 하는가

로컬에서만 잘 보이는 것은 최종 결과가 아닙니다.
1회차에서 만든 배포 루프를 2회차 변경사항에도 다시 적용해야 합니다.

```text
수정
→ 브라우저 확인
→ build
→ commit
→ push
→ GitHub Actions
→ GitHub Pages 확인
```

## 공통 프롬프트

이 프롬프트는 일부러 자세합니다.
길다고 줄이기보다, 현재 상태와 확인 기준을 빠뜨리지 않기 위해 그대로 복사해서 사용하세요.

```text
2회차 변경사항을 commit하고 GitHub Pages 배포까지 확인하고 싶어.

현재 목표:
- Home / About / Projects / Posts 구조를 GitHub에 올린다.
- GitHub Pages에서 변경사항이 반영되는지 확인한다.

먼저 확인할 것:
1. git status
2. 변경 파일 목록
3. secret, token, password, API key 같은 민감한 값이 포함되어 있지 않은지
4. package-lock.json 등 의존성 파일 변경 여부
5. npm run build가 성공했는지
6. remote가 GitHub 저장소를 가리키는지
7. 현재 branch가 배포 대상 branch인지

작업 방식:
- 아직 commit하지 마.
- 아직 push하지 마.
- 먼저 변경사항 요약과 추천 commit 메시지를 알려줘.
- 내가 승인하면 commit을 만들어줘.
- commit 후 push를 진행해줘.
- push 후 GitHub Actions 또는 Pages 상태를 확인하는 방법을 알려줘.

추천 commit 메시지 형식:
- feat: 페이지 구조와 내비게이션 추가
- feat: 프로젝트 카드와 글 목록 추가
- fix: 2회차 페이지 build 오류 수정
- docs: 2회차 작업 기록 추가

완료 후 아래 형식으로 보고해줘.

1. commit 메시지
2. commit hash
3. push한 branch
4. GitHub 저장소 URL
5. GitHub Pages 확인 URL
6. GitHub Actions 확인 방법
7. 아직 남은 문제
```

## 승인 후 추가 프롬프트

```text
좋아. 방금 요약한 변경사항을 commit하고 push해줘.

주의:
- 민감한 값이 있으면 commit하지 말고 멈춰줘.
- 관련 없는 파일이 섞여 있으면 먼저 알려줘.
- push가 끝나면 GitHub Pages에서 확인할 URL과 Actions 확인 위치를 알려줘.
```

## 시간이 부족할 때

commit / push / deploy까지 못 가도 실패가 아닙니다.
아래 중 하나를 남기면 다음 세션에서 이어갈 수 있습니다.

```text
- npm run build 성공 결과
- npm run build 실패 로그
- git status 결과
- GitHub Actions 실패 화면
- GitHub Pages에서 아직 반영되지 않은 URL
```

오늘의 최소 성공은 배포 성공만이 아닙니다.
현재 상태를 정확히 남기는 것도 성공입니다.

## GitHub Pages가 바로 안 바뀔 때

```text
push는 끝났는데 GitHub Pages 화면이 아직 안 바뀐 것 같아.

확인해줘:
1. GitHub Actions가 실행 중인지
2. 실패한 workflow가 있는지
3. Pages 설정이 올바른지
4. 브라우저 캐시 문제일 가능성이 있는지
5. 지금 내가 기다려야 하는지, 수정해야 하는지

먼저 확인 방법을 설명하고, 내가 직접 봐야 하는 화면이 있으면 정확한 위치를 알려줘.
```

## 체크박스

- [ ] `git status`를 확인했다.
- [ ] 변경 파일 목록을 확인했다.
- [ ] 민감한 값이 없는지 확인했다.
- [ ] commit을 만들었다.
- [ ] GitHub에 push했다.
- [ ] GitHub Actions 상태를 확인했다.
- [ ] GitHub Pages URL을 열어봤다.
- [ ] 반영됐거나, 실패 로그를 확보했다.

## Ready Gate

오늘 마무리 전에 아래 중 하나 이상이 남아 있으면 다음 세션에서 이어갈 수 있습니다.

- GitHub에 2회차 변경사항이 올라갔습니다.
- 아직 push하지 못했다면 `git status` 결과가 있습니다.
- build가 성공했거나 실패 로그가 있습니다.
- GitHub Actions 실패 화면이나 Pages 반영 상태가 기록되어 있습니다.
- 다음 질문이 있습니다.

## 힌트

<details>
<summary>Hint 1</summary>

GitHub Actions는 몇 분 걸릴 수 있습니다. push 직후 바로 반영되지 않아도 잠시 기다려보세요.

</details>

<details>
<summary>Hint 2</summary>

GitHub Pages가 이전 화면을 보여주면 브라우저 새로고침 또는 시크릿 창에서 확인해보세요.

</details>

<details>
<summary>Hint 3</summary>

배포가 실패하면 Actions 탭의 빨간색 실패 항목을 열고, 실패한 단계의 로그를 복사해서 AI에게 주세요.

</details>

## 퀴즈

### 질문

push 이후 GitHub Pages가 안 바뀌었을 때 가장 먼저 확인할 곳은?

- A. GitHub Actions 실행 상태
- B. Mac 배경화면 설정
- C. 외부 콘텐츠 관리 도구 설정
- D. npm 공식 블로그

<details>
<summary>정답 보기</summary>

**정답**

A

</details>

## 다음 단계

[11. 결과 기록과 다음 숙제 →](./11-record-result-homework.md)
