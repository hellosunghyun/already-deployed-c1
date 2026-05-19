# 09. 브라우저와 build로 검증하기

## 목표

브라우저와 `npm run build`로 2회차 변경사항이 실제로 동작하는지 확인합니다.

## 왜 하는가

AI가 파일을 만들었다고 끝이 아닙니다.
브라우저에서 페이지가 열리고, build가 성공해야 배포 가능한 상태라고 볼 수 있습니다.

## 쉬운 설명

오늘 확인할 것은 두 가지입니다.

```text
브라우저 확인 = 사람이 보는 화면 확인
build 확인 = 배포 가능한 파일을 만들 수 있는지 확인
```

둘 중 하나만으로는 부족합니다.

`npm run dev`와 `npm run build`는 역할이 다릅니다.

```text
npm run dev
= 작업 중인 사이트를 내 컴퓨터에서 열어보는 명령

npm run build
= 배포 가능한 결과물을 만들 수 있는지 확인하는 명령
```

`dev`에서 화면이 보여도 `build`에서 실패할 수 있습니다.
그래서 마지막에는 build 결과나 실패 로그를 꼭 남깁니다.

## 오늘의 검증 우선순위

시간이 부족하면 새 기능을 더 만들지 말고 검증으로 넘어갑니다.

우선순위는 아래입니다.

```text
1. /, /about, /projects, /posts 중 어떤 URL이 열리는지 확인
2. Navigation이 보이는지 확인
3. npm run build 실행
4. 성공하면 결과 기록
5. 실패하면 실패 로그 기록
```

Projects 카드나 Posts 문장이 덜 완성되어도 괜찮습니다.
하지만 어떤 URL이 열리고, build가 성공했는지 실패했는지는 반드시 남깁니다.

## 공통 프롬프트

이 프롬프트는 일부러 자세합니다.
길다고 줄이기보다, 현재 상태와 확인 기준을 빠뜨리지 않기 위해 그대로 복사해서 사용하세요.

```text
2회차에서 만든 Home / About / Projects / Posts 구조가 제대로 동작하는지 검증하고 싶어.

현재 확인할 것:
1. npm run dev로 로컬 개발 서버 실행
2. 브라우저에서 / 열기
3. 브라우저에서 /about 열기
4. 브라우저에서 /projects 열기
5. 브라우저에서 /posts 열기
6. Navigation 링크로 페이지 이동 확인
7. Projects 카드의 자세히 보기 링크가 상세 페이지로 이동하는지 확인
8. 화면에서 텍스트가 겹치거나 너무 깨지는 부분이 없는지 확인
9. npm run build 실행
10. build 오류가 있으면 원인과 수정 방향 설명

중요:
- 검증 중 문제가 발견되면 바로 대규모 수정하지 마.
- 먼저 문제를 목록으로 정리해줘.
- 수정이 필요하면 가장 작은 수정 계획을 설명해줘.
- 내가 승인하면 수정해줘.

완료 후 아래 형식으로 보고해줘.

1. 확인한 URL 목록
2. 각 페이지 상태
3. Navigation 동작 여부
4. Projects 카드 상세 링크 동작 여부
5. npm run build 결과
6. 발견한 문제
7. 수정한 파일이 있다면 파일 목록과 이유
8. 다음 단계로 넘어가도 되는지
```

## Codex에서는 Browser로 확인하기

Codex에서는 로컬 사이트를 Browser로 직접 열어 확인하는 흐름을 기본으로 둡니다.

```text
@browser 로컬 사이트를 확인해줘.

확인할 주소:
- http://localhost:4321/
- http://localhost:4321/about
- http://localhost:4321/projects
- http://localhost:4321/posts

각 페이지가 열리는지, Navigation 링크가 동작하는지, Projects 카드의 자세히 보기 링크가 상세 페이지로 이동하는지, 모바일에서 크게 깨지는 부분이 있는지 확인해줘.
```

## build 실패 시 프롬프트

```text
npm run build에서 아래 오류가 났어.

[오류 붙여넣기]

요청:
- 오류 원인을 초보자도 이해할 수 있게 설명해줘.
- 어떤 파일이 문제인지 추정해줘.
- 바로 전체를 고치지 말고, 가장 가능성 높은 원인부터 확인해줘.
- 수정이 필요하면 최소 수정 계획을 먼저 말해줘.
```

## 체크박스

- [ ] 로컬 개발 서버가 실행되었다.
- [ ] `/` 페이지가 열린다.
- [ ] `/about` 페이지가 열린다.
- [ ] `/projects` 페이지가 열린다.
- [ ] `/posts` 페이지가 열린다.
- [ ] Navigation 링크가 동작한다.
- [ ] Projects 카드의 자세히 보기 링크가 동작한다.
- [ ] `npm run build`를 실행했다.
- [ ] build 성공 또는 실패 로그를 확보했다.

## Ready Gate

다음 단계로 넘어가기 전에 아래가 되어 있어야 합니다.

- 열린 URL과 안 열린 URL을 구분했습니다.
- Navigation이 보이는지 확인했습니다.
- `npm run build`를 실행했습니다.
- build가 성공했거나, 실패 로그를 기록했습니다.
- Projects 카드나 Posts가 덜 끝났다면 현재 상태를 기록했습니다.

## 힌트

<details>
<summary>Hint 1</summary>

`npm run dev`가 이미 실행 중이면 새 터미널에서 `npm run build`를 실행해도 됩니다.

</details>

<details>
<summary>Hint 2</summary>

페이지가 하나만 404라면 파일 이름이나 경로 문제일 가능성이 큽니다.

</details>

<details>
<summary>Hint 3</summary>

build 오류는 브라우저에서 보이는 문제보다 더 엄격하게 잡힐 수 있습니다. 오류 메시지를 그대로 복사해 AI에게 주세요.

</details>

## 퀴즈

### 질문

`npm run build`를 실행하는 이유로 가장 적절한 것은?

- A. 배포 가능한 정적 파일을 만들 수 있는지 확인하기 위해
- B. GitHub 계정을 만들기 위해
- C. 브라우저 주소를 외우기 위해
- D. 외부 콘텐츠 API token을 만들기 위해

<details>
<summary>정답 보기</summary>

**정답**

A

</details>

## 다음 단계

[10. commit / push / deploy 확인 →](./10-commit-push-deploy.md)
