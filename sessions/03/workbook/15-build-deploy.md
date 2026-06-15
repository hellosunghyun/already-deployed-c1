# 15. build / commit / deploy

## 목표

디자인 수정이 배포 가능한 상태인지 확인합니다.

## 검증 순서

```text
브라우저 확인
→ npm run build
→ git status
→ 변경 파일 확인
→ commit
→ push
→ GitHub Actions / Pages 확인
```

## Codex에게 보낼 프롬프트

```text
3회차 디자인 수정 결과를 검증하고 싶어.

확인할 것:
1. 수정한 URL이 브라우저에서 정상인지
2. 390px 모바일에서 크게 깨지지 않는지
3. npm run build 결과
4. git status
5. 변경 파일 목록
6. 민감한 값이 포함되지 않았는지
7. 적절한 commit 메시지

아직 commit하지 마.
먼저 요약과 추천 commit 메시지만 보여줘.
```

## commit 메시지 예시

```text
feat: 홈 히어로 시각 위계 개선
feat: 프로젝트 카드 디자인 정리
fix: 모바일 내비게이션 간격 개선
docs: 3회차 디자인 백로그 기록
```

## 실패해도 남길 것

```text
build 실패 로그
git status
어떤 URL이 깨졌는지
다음 질문 프롬프트
```

## 다음 단계

[16. 결과 기록과 4회차 준비 →](./16-record-result-homework.md)
