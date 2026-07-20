# 3회차 워크북 인덱스

이 워크북은 **이미 2회차까지 진행한 Astro 개인 홈페이지 레포**를 Codex에서 이어서 고치는 실습 문서입니다.
새 프로젝트를 만들지 않습니다. 기준은 이미 Codex에 가져와 둔 2회차 레포와 기존 채팅입니다.

## 전체 수업과 워크북 시간

3회차 전체 수업은 **120분**입니다.

```text
발표와 시연 30분
+ 개인 워크북 실습 90분
= 전체 120분
```

아래 워크북 시간은 전체 수업 시작 시각이 아니라, **개인 실습을 시작한 시점부터 다시 센 상대 시간**입니다.
예를 들어 전체 수업 0:30에 워크북을 시작했다면 워크북 `W0:00`입니다.

## 실제 진행 흐름

11~13은 10단계 뒤에 모두 실행하는 직렬 과제가 아닙니다.
08단계에서 Target을 고른 뒤 **셋 중 하나만** 열어 D-001 후보를 구체화합니다.

```text
00 → 01 → 03 → 04 → 05 → 06 → 07 → 08
                                      ├─ 11 Home hero
                                      ├─ 12 Navigation / 레이아웃
                                      └─ 13 Projects 또는 Posts
                                             ↓
                            02 최종 Plan → 09 → 10 → 14 → 15 → 16
```

번호는 파일을 찾기 위한 번호이고, 화살표가 실제 실습 순서입니다.

## 공통 단계

0. [워크북 사용법](./00-how-to-use.md)
1. [기존 레포와 Codex 채팅 확인](./01-existing-repo-check.md)
3. [브라우저 활성화와 태그 확인](./03-browser-setup.md)
4. [현재 화면 baseline 기록](./04-visual-baseline.md)
5. [스크린샷과 브라우저 주석 피드백](./05-screenshot-comment-feedback.md)
6. [레퍼런스 사이트 고르기](./06-reference-pick.md)
7. [Codex로 디자인 토큰 브리프 만들기](./07-design-token-brief.md)
8. [원하는 요소만 하나 선택하기](./08-selective-element.md)

## D-001 후보 선택: 하나만 진행

- [11. Home hero 후보](./11-home-hero-challenge.md)
- [12. Navigation / 레이아웃 후보](./12-navigation-layout-challenge.md)
- [13. Projects 또는 Posts 후보](./13-projects-posts-challenge.md)

후보 하나를 구체화했으면 아래 공통 흐름으로 돌아옵니다.

2. [Plan mode로 최종 수정 계획 받기](./02-plan-mode.md)
9. [AGENTS.md 규칙과 백로그 폴더 만들기](./09-design-backlog-folder.md)
10. [D-001 플랜 실행하기](./10-execute-plan.md)
14. [모바일과 접근성 확인](./14-mobile-check.md)
15. [build / commit / deploy](./15-build-deploy.md)
16. [결과 기록과 4회차 준비](./16-record-result-homework.md)

## 90분 워크북 진행 리듬

| 워크북 상대 시간 | 전체 수업 시간 예시 | 단계 | 남길 것 |
|---|---|---|---|
| W0:00-W0:08 | 0:30-0:38 | 00, 01, 03 | 기존 레포, 실제 Local URL, 브라우저 연결 상태 |
| W0:08-W0:18 | 0:38-0:48 | 04-05 | 현재 화면 문제 1~3개, 스크린샷 또는 주석 |
| W0:18-W0:30 | 0:48-1:00 | 06-08, 11·12·13 중 하나 | 레퍼런스 1개, 토큰 브리프, D-001 후보 하나 |
| W0:30-W0:40 | 1:00-1:10 | 02, 09 | 최종 Plan, `docs/design-backlog/README.md`, `D-001.md` |
| W0:40-W1:00 | 1:10-1:30 | 10 | 선택한 D-001 한 건의 실제 수정 |
| W1:00-W1:12 | 1:30-1:42 | 14 | 현재 desktop과 390x844 검증 결과 |
| W1:12-W1:24 | 1:42-1:54 | 15 | build, commit/push 또는 정확한 차단 로그 |
| W1:24-W1:30 | 1:54-2:00 | 16 | before/after, 백로그 상태, 4회차 준비 |

시간이 부족하면 범위를 늘리지 않습니다.
D-001 하나를 검증할 수 없으면 억지로 배포하지 않고 `blocked` 상태와 다음 질문을 남깁니다.

## 오늘의 원칙

```text
기존 2회차 레포에서 이어서 한다.
화면 증거와 D-001 후보를 모은 뒤 Plan mode로 최종 계획을 확정한다.
`@Browser` 또는 일반 브라우저의 스크린샷으로 화면을 같이 본다.
레퍼런스는 전체 복제가 아니라 원하는 요소 하나만 가져온다.
AGENTS.md에는 반복 규칙과 백로그 위치만 남기고, 실제 백로그는 docs/design-backlog/에 작성한다.
D-001 후보는 11~13 중 하나만 고른다.
수정 후에는 현재 desktop, 390x844, build로 확인한다.
검증 실패가 남으면 배포하지 않고 blocked로 기록한다.
```

## 참고 레퍼런스 사이트

| 사이트 | 용도 |
|---|---|
| [getdesign.md](https://getdesign.md/) | 제품/브랜드별 DESIGN.md 분석에서 방향성 고르기 |
| [Refero Styles](https://styles.refero.design/) | colors, typography, spacing, components 예시 고르기 |
| [designmd.app](https://designmd.app/) | DESIGN.md 형식과 ready-to-use style 참고 |

[시작하기 →](./00-how-to-use.md)
