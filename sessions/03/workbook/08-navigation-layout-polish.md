# 08. Navigation과 레이아웃 밀도 조정

## 목표

공통 Header / Navigation / Footer와 전체 레이아웃 밀도를 정리합니다.

## 왜 하는가

Navigation은 방문자가 사이트 안에서 길을 잃지 않게 하는 안내판입니다.
특히 모바일에서는 링크 간격, 줄바꿈, 터치 영역이 사용성에 직접 영향을 줍니다.

## 확인할 것

```text
Header 높이
브랜드 텍스트 크기
Navigation 링크 간격
현재 페이지 표시 여부
모바일 줄바꿈
Footer가 너무 강하거나 약한지
page width와 section padding
```

## Codex에게 보낼 프롬프트

```text
공통 Header / Navigation / Footer와 전체 레이아웃 밀도를 점검하고 싶어.

대상:
- URL: /, /about, /projects, /posts
- Viewport: 1440x900, 768x1024, 390x844
- Target: Header, Navigation, Footer, page container

확인할 것:
1. 모든 페이지에서 Navigation이 같은 위치와 모양으로 보이는지
2. 모바일에서 링크가 너무 붙거나 어색하게 줄바꿈되는지
3. Header가 모바일에서 과하게 높아지는지
4. 현재 페이지를 알 수 있는 표시가 필요한지
5. page container와 섹션 여백이 너무 좁거나 넓은지
6. Footer가 콘텐츠와 잘 구분되는지

수정 방향:
- 모바일에서 링크가 터치하기 쉽게 보이게 한다.
- Header와 Navigation은 단순하게 유지한다.
- 현재 페이지 표시가 가능하면 aria-current 또는 active class를 검토한다.
- 전체 색상 톤은 유지한다.

제약:
- 새 라이브러리 추가하지 마.
- 페이지 콘텐츠 문장 자체는 크게 바꾸지 마.
- 배포 설정은 건드리지 마.
- 아직 수정하지 말고 문제 목록과 최소 수정 계획을 먼저 제안해줘.
```

## 승인 후 프롬프트

```text
좋아. Navigation과 레이아웃 밀도에 대한 최소 수정만 진행해줘.

주의:
- Header를 완전히 새로 만들지 마.
- 링크 항목은 Home / About / Projects / Posts를 유지해.
- 모바일 390px에서 확인하고, 가로 스크롤이 생기지 않는지 봐줘.
```

## 체크박스

- [ ] 모든 페이지에 같은 Navigation이 보인다.
- [ ] 모바일에서 Navigation이 크게 깨지지 않는다.
- [ ] 링크 간격이 너무 좁지 않다.
- [ ] 현재 페이지 표시 여부를 판단했다.
- [ ] 전체 page width와 section padding을 확인했다.
- [ ] Footer가 모든 페이지에 자연스럽게 보인다.

## Ready Gate

다음 단계로 넘어가기 전에 아래가 되어 있어야 합니다.

- Navigation이 사용 가능한 상태입니다.
- 모바일에서 링크가 보이고 클릭하기 쉬워 보입니다.
- Header가 콘텐츠를 과하게 밀어내지 않습니다.

## 저장 체크포인트

```text
fix: 모바일 내비게이션과 레이아웃 밀도 정리
```

## 다음 단계

[09. Projects 카드와 Posts 목록 시각 위계 개선 →](./09-projects-posts-visual-hierarchy.md)
