# 12. GitHub Pages 배포하기

## 목표

[GitHub Pages](https://pages.github.com/)로 사이트를 배포해 `github.io` 링크를 만듭니다.

## 왜 하는가

이 단계가 끝나면 다른 사람에게 보낼 수 있는 실제 인터넷 주소가 생깁니다.

## 쉬운 설명

Astro 프로젝트는 그냥 파일만 올린다고 바로 완성되는 것이 아닙니다. 배포 가능한 파일로 바꾸는 **build** 과정이 필요합니다.

공식 [Astro GitHub Pages 배포 가이드](https://docs.astro.build/en/guides/deploy/github/)는 GitHub Actions와 Astro 공식 action을 사용해 배포하는 방식을 안내합니다.

## 공통 프롬프트

```text
이 Astro 프로젝트를 GitHub Pages에 배포하고 싶어.

조건:
- 배포 대상은 GitHub Pages야.
- 저장소는 <github-username>.github.io 사용자 사이트 저장소야.
- Astro 프로젝트라서 build가 필요해.
- GitHub Actions로 build 후 배포하는 방식을 사용하고 싶어.
- 공식 Astro GitHub Pages 배포 가이드의 withastro/action 방식을 참고해줘.

먼저 아래를 설명해줘.

1. GitHub Pages 설정에서 무엇을 선택해야 하는지
2. GitHub Actions workflow가 필요한지
3. 필요한 파일을 만들기 전 전체 계획
4. 내가 GitHub 웹사이트에서 직접 해야 하는 것
5. 네가 코드로 도와줄 수 있는 것
6. 사용자 사이트이므로 astro.config.mjs의 site 값을 어떻게 설정해야 하는지

내가 승인하면 workflow 파일을 만들어줘.
```

## GitHub 웹사이트에서 확인할 곳

- 저장소의 [Actions](https://docs.github.com/en/actions) 탭
- 저장소의 Settings → Pages
- Pages의 Source 설정
- 배포 완료 후 표시되는 URL

## workflow 예시

필요하면 [deploy.yml 예시](../templates/deploy.yml)를 참고하세요.
단, 직접 복사하기 전에 AI에게 현재 프로젝트에 맞는지 확인시키세요.

## 체크박스

- [ ] AI가 GitHub Pages 배포 계획을 설명했다.
- [ ] GitHub Actions workflow가 생성되었다.
- [ ] `astro.config.mjs`의 `site` 값이 확인되었다.
- [ ] GitHub Pages 설정을 확인했다.
- [ ] Actions가 실행되었다.
- [ ] 배포 로그를 확인했다.
- [ ] `https://<username>.github.io` 주소에 접속했다.

## Ready Gate

오늘 마무리 전에 아래가 되어 있으면 가장 좋습니다.

- GitHub Actions가 실행되었습니다.
- GitHub Pages 설정이 완료되었습니다.
- `github.io` 주소가 열리거나, 실패 로그를 확보했습니다.

## 힌트

### Hint 1

배포는 몇 분 걸릴 수 있습니다. 바로 안 열려도 잠시 기다려보세요.

### Hint 2

실패하면 Actions 로그에서 빨간색 실패 단계를 캡처하세요.

### Hint 3

사용자 사이트 저장소가 아니라 프로젝트 사이트로 진행하면 Astro의 `base` 설정이 필요할 수 있습니다. 오늘은 가능하면 사용자 사이트 트랙을 추천합니다.

## 퀴즈

### 질문

GitHub Pages의 역할은 무엇인가요?

A. Codex를 실행하는 앱  
B. GitHub 저장소의 웹사이트 파일을 인터넷 주소로 보여주는 기능  
C. npm 패키지를 설치하는 도구  
D. 내 컴퓨터에서만 보이는 주소

### 정답

B

## 다음 단계

[13. 결과 기록과 다음 숙제 →](./13-record-result-homework.md)
