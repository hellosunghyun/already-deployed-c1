# Slide 10. Posts를 미리 만드는 이유

4회차에는 [Notion](https://www.notion.so/)을 콘텐츠 관리 도구처럼 연결합니다.

하지만 오늘은 Notion API를 붙이지 않습니다.

오늘은 먼저 글 목록이 사이트에서 어떻게 보일지 만듭니다.

```text
샘플 글 데이터
→ Posts 페이지
→ 나중에 외부 데이터 응답을 같은 모양으로 변환
```

---

## 오늘 하지 않는 것

- Notion database 만들기
- Integration token 만들기
- secret 설정하기
- API 호출하기

---

[← 이전](./09a-component-data-analogy.md) · [다음 →](./11-codex-demo.md)

<details><summary>말할 포인트</summary>

1회차에서 Notion을 나중으로 미룬 이유와 이어집니다.
오늘은 Notion을 붙이는 날이 아닙니다.

먼저 글 목록이 들어갈 자리와 모양을 만들어둡니다.
나중에 4회차에서 API 응답을 `title`, `slug`, `date`, `summary`, `tags` 같은 화면용 데이터로 바꿔 끼우면 된다고 설명합니다.

API, secret, token 이야기는 오늘 하지 않습니다.
오늘 필요한 것은 외부 연동이 아니라, 글 목록이 화면에서 어떤 모양으로 쓰일지 정하는 것입니다.
즉 Posts를 완성된 블로그로 만들지 않고, 나중에 바꿔 끼울 데이터 자리만 먼저 잡습니다.

</details>
