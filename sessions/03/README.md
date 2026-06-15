# 배포했는데요? 1기 — 3회차 자료

3회차는 **이미 2회차까지 진행한 Astro 개인 홈페이지를 Codex에서 이어서 고치는 회차**입니다.
새 홈페이지를 만들지 않습니다. 기준은 기존 레포, 기존 Codex 프로젝트, 가능하면 기존 채팅입니다.

## 오늘의 목표

스크린샷, 브라우저 주석, 레퍼런스 토큰, 모바일 확인 결과를 이용해 Codex에게 디자인 수정 요구사항을 정확히 전달합니다.

```text
기존 2회차 레포
→ Plan mode
→ 브라우저 / Browser 확인
→ 레퍼런스 토큰 분석
→ AGENTS.md 백로그
→ 선택한 영역 하나 수정
→ 모바일 / build 검증
```

## 오늘 추가된 핵심

- Plan mode 사용법과 실행법
- 한국어 UI `@브라우저`, 영어 UI `@Browser` 안내
- 태그가 안 될 때 브라우저 설정 활성화 안내
- 기존 2회차 레포와 기존 Codex 채팅에서 이어서 진행하는 기준
- 막혔을 때 질문 템플릿에 수업 레포 링크 포함
- 디자인 백로그를 `AGENTS.md`에 남기는 방식
- 레퍼런스에서 원하는 요소 하나만 가져오는 연습

## 참고 레퍼런스 사이트

| 사이트 | 수업에서의 역할 |
|---|---|
| [getdesign.md](https://getdesign.md/) | DESIGN.md 분석을 보고 스타일 방향 고르기 |
| [Refero Styles](https://styles.refero.design/) | colors, typography, spacing, components 예시 고르기 |
| [designmd.app](https://designmd.app/) | DESIGN.md 형식과 ready-to-use style 참고 |

## 2시간 운영안

| 시간 | 구간 | 목표 |
|---|---|---|
| 0:00-0:10 | 시작 | 기존 레포 / 기존 채팅 / 브라우저 태그 확인 |
| 0:10-0:20 | Plan mode | 수정 계획을 먼저 받는 법 |
| 0:20-0:35 | 화면 기록 | baseline, 스크린샷, 브라우저 주석 |
| 0:35-0:50 | 레퍼런스 | 디자인 토큰 설명시키기, 원하는 요소 하나 선택 |
| 0:50-1:05 | AGENTS.md | 디자인 작업 규칙과 D-001 백로그 기록 |
| 1:05-1:35 | 실행 | D-001만 수정, 브라우저 확인 |
| 1:35-1:50 | 검증 | 390px 모바일, npm run build |
| 1:50-2:00 | 기록 | before/after, 다음 질문, AGENTS.md 상태 갱신 |

## 성공 기준

### 최상

- Plan mode로 계획을 받고 D-001만 실행했다.
- 브라우저 주석 또는 스크린샷으로 Target을 정확히 지정했다.
- 레퍼런스에서 원하는 요소 하나만 토큰으로 가져왔다.
- desktop, 390px 모바일, build까지 확인했다.
- AGENTS.md 백로그가 갱신됐다.

### 표준

- 화면 문제 1개를 6좌표로 설명했다.
- 작은 CSS 수정 1개를 실행했다.
- 모바일 확인 또는 build 로그가 있다.

### 최소

- 기존 레포 상태, 고칠 Target, 다음 요청 프롬프트가 남았다.

## 자료 구조

- [발표자료 인덱스](./presentation/README.md)
- [워크북 인덱스](./workbook/README.md)
- [템플릿](./templates/)
- [브라우저 설정 스크린샷](./assets/codex-browser-settings.png)
- [웹 리서치 노트](./research-notes.md)

## 오늘의 핵심 문장

> 레퍼런스는 복사 대상이 아니라 요구사항 재료입니다.
> Plan mode는 바로 고치기 전에 수정 계약서를 만드는 단계입니다.
