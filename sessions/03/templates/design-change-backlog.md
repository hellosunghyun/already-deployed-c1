# AGENTS.md 디자인 백로그 양식

3회차에서는 별도 백로그 파일보다 `AGENTS.md`의 `3회차 디자인 백로그` 섹션을 우선 사용합니다.

```markdown
- [ ] D-001
  - URL: /projects
  - Viewport: 390x844
  - Target: 첫 번째 프로젝트 카드
  - Problem: 제목, 설명, 태그의 위계가 약함
  - Direction: 제목 굵기 강화, 설명 줄간격 조정, 태그 톤 낮추기
  - Reference: https://styles.refero.design/
  - Selected element: Project card framing
  - Bring: 카드 gap, muted text 위계, 얇은 border
  - Avoid: 전체 dark theme, logo, animation, 외부 font
  - Verification: @브라우저 또는 @Browser로 desktop/390px 확인, npm run build
  - Status: planned
```

## 상태값

```text
planned → doing → done → blocked
```
