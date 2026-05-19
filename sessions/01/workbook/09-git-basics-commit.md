# 09. Git 기초와 자주 commit하기

## 목표

[Git](https://git-scm.com/)이 왜 필요한지 이해하고, 변경사항을 자주 commit하는 습관을 만듭니다.

## 왜 하는가

AI와 작업할수록 commit이 더 중요합니다. AI는 사람보다 빠르게, 많이, 과감하게 수정할 수 있습니다. 작은 단위로 commit을 남겨야 실수했을 때 돌아갈 수 있습니다.

## 쉬운 설명

| 단어 | 의미 |
|---|---|
| Git | 변경 기록을 남기는 도구 |
| commit | 변경 사항에 이름표를 붙여 저장하는 것 |
| push | 내 컴퓨터의 commit을 GitHub로 올리는 것 |
| remote | 내 프로젝트와 연결된 GitHub 저장소 주소 |

## commit 메시지 형식

오늘은 아래 형식을 씁니다.

```text
feat: 홈 화면 초안 추가
fix: GitHub Pages 배포 설정 수정
chore: 초기 프로젝트 생성
docs: AGENTS.md 규칙 추가
```

분류는 이렇게 이해하면 됩니다.

- `feat`: 기능 또는 화면 추가
- `fix`: 문제 수정
- `chore`: 설정, 설치, 초기화
- `docs`: 문서 수정

## 공통 프롬프트

```text
지금까지 변경된 내용을 commit하고 싶어.

먼저 아래를 확인해줘.

1. 현재 git 저장소가 초기화되어 있는지
2. 변경된 파일 목록
3. secret, token, password, API key 같은 민감한 값이 포함되어 있지 않은지
4. 어떤 commit 메시지가 적절한지

아직 commit하지 말고 먼저 설명해줘.
내가 승인하면 commit해줘.

commit 메시지는 아래 형식을 사용해줘.
- feat: 한국어설명
- fix: 한국어설명
- chore: 한국어설명
- docs: 한국어설명
```

## 체크박스

- [ ] git이 무엇인지 대략 이해했다.
- [ ] commit이 안전 저장점이라는 것을 이해했다.
- [ ] 변경 파일 목록을 확인했다.
- [ ] 첫 commit 메시지를 정했다.
- [ ] AI가 commit 전 확인 내용을 설명했다.

## Ready Gate

다음 단계로 넘어가기 전에 아래가 되어 있어야 합니다.

- commit이 왜 필요한지 이해했습니다.
- 변경 파일 목록을 확인했습니다.
- 민감한 값이 올라가지 않는지 확인했습니다.

## 퀴즈

### 질문

AI와 작업할수록 commit을 자주 해야 하는 이유는?

- A. 홈페이지 디자인이 자동으로 예뻐지기 때문에
- B. 실수했을 때 이전 상태로 돌아가기 쉽기 때문에
- C. GitHub 계정이 무료가 되기 때문에
- D. npm 설치가 빨라지기 때문에

<details>
<summary>정답 보기</summary>

**정답**

B

</details>

## 다음 단계

[10. GitHub 저장소 만들기 →](./10-create-github-repo.md)
