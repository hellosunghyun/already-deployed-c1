---
theme: default
title: 배포했는데요? 1기 — 2회차
info: 1회차 Astro 개인 홈페이지를 Home / About / Projects / Posts 구조로 확장하는 2회차 발표자료
class: deck
transition: fade-out
drawings:
  persist: false
mdc: true
---

<section class="deck-slide dark">
  <div class="eyebrow">SESSION 02 / STRUCTURE</div>
  <h1 class="hero-title">첫 배포 이후,<br><span class="accent">사이트에 길</span> 만들기</h1>
  <p class="subtitle">1회차에서는 홈페이지를 인터넷에 올렸습니다.<br>2회차에서는 방문자가 읽을 수 있는 구조로 나눕니다.</p>
  <div class="code-panel">Home / About / Projects / Posts</div>
  <div class="slide-number">01 / 27</div>
</section>

<!--
지난 시간에 GitHub Pages까지 성공한 분도 있고, 로컬 실행이나 예제 폴더에서 다시 시작해야 하는 분도 있을 거예요. 오늘은 그 차이를 실패로 보지 않습니다. 오늘은 예쁜 디자인을 완성하는 시간이 아니라, Home / About / Projects / Posts라는 기본 구조를 만들고 다음 세션으로 이어갈 수 있게 정리하는 시간입니다.
-->

---

<section class="deck-slide">
  <div class="eyebrow">CONTEXT</div>
  <h1 class="title">2회차는 <span class="accent">구조</span>를 만드는 회차입니다</h1>
  <div class="timeline">
    <div class="timeline-row"><span class="step">01</span><span class="desc">인터넷에 올라가는 첫 버전</span></div>
    <div class="timeline-row active"><span class="step">02</span><span class="desc">방문자가 읽을 수 있는 구조</span></div>
    <div class="timeline-row"><span class="step">03</span><span class="desc">화면의 특정 요소를 짚어 디자인 수정</span></div>
    <div class="timeline-row"><span class="step">04</span><span class="desc">외부 콘텐츠 소스 연결</span></div>
    <div class="timeline-row"><span class="step">05</span><span class="desc">운영 가능한 홈페이지로 정리</span></div>
  </div>
  <div class="slide-number">02 / 27</div>
</section>

<!--
2회차를 독립된 완성 과제로 말하지 않습니다. 오늘은 뒤 회차를 위한 중간 다리입니다. 구조와 기록이 남으면 3회차 디자인 수정, 4회차 외부 콘텐츠 연결로 이어갈 수 있습니다.
-->

---

<section class="deck-slide">
  <div class="eyebrow">SCOPE</div>
  <h1 class="title">오늘은 많이 다루지만,<br>같은 완성도를 요구하지 않습니다</h1>
  <div class="grid-3 content-grid">
    <div class="card"><span class="badge">STRUCTURE</span><strong>Home / About / Projects / Posts</strong><p>페이지와 섹션, Astro 라우팅, Layout과 Navigation을 함께 봅니다.</p></div>
    <div class="card"><span class="badge">CONTENT</span><strong>Projects / Posts</strong><p>카드, 상세 링크, JSON 데이터, slug, 샘플 글 목록을 다룹니다.</p></div>
    <div class="card"><span class="badge">VERIFY</span><strong>Browser / build / 기록</strong><p>commit, push, deploy 확인과 다음 질문까지 남깁니다.</p></div>
  </div>
  <div class="slide-number">03 / 27</div>
</section>

<!--
오늘 나오는 단어가 많다는 것을 먼저 인정합니다. 하지만 발표 시간에 이 단어를 전부 구현하는 것은 아닙니다. 워크북에서 다시 만날 단어를 미리 익히는 시간입니다.
-->

---

<section class="deck-slide success-slide dark">
  <div class="eyebrow">SUCCESS CRITERIA</div>
  <h1 class="title">성공 기준은<br>세 단계입니다</h1>
  <div class="grid-3 content-grid">
    <div class="card"><span class="badge">BEST</span><strong>최상</strong><p>네 페이지, Navigation, Projects 카드, Posts 목록, build, Pages 반영까지 끝납니다.</p></div>
    <div class="card"><span class="badge">STANDARD</span><strong>표준</strong><p><code>/about</code>, <code>/projects</code>, <code>/posts</code>가 열리고 Layout / Navigation 상태를 압니다.</p></div>
    <div class="card"><span class="badge">MINIMUM</span><strong>최소</strong><p>현재 상태, 열린 URL, 안 열린 URL, build 로그나 실패 로그, 다음 질문이 남습니다.</p></div>
  </div>
  <div class="slide-number">04 / 27</div>
</section>

<!--
오늘은 모두가 같은 속도로 움직이지 않습니다. 어떤 사람은 Pages 반영까지 갈 수 있고, 어떤 사람은 URL 확인과 실패 로그 기록에서 멈출 수 있습니다. 그 차이를 성공과 실패로 나누지 않습니다.
-->

---

<section class="deck-slide">
  <div class="eyebrow">KEEP THE WORK</div>
  <h1 class="title">1회차 결과를<br>버리지 않습니다</h1>
  <div class="compare">
    <div class="card"><div class="label">1회차 흐름</div><div class="text">만든다 → 확인한다 → 저장한다 → 배포한다 → 링크로 본다</div></div>
    <div class="card"><div class="label">2회차 요청</div><div class="text">새로 만들기보다 현재 프로젝트에 구조 추가하기</div></div>
  </div>
  <div class="slide-number">05 / 27</div>
</section>

<!--
AI에게 "홈페이지 새로 만들어줘"라고 하면 기존 설정이나 1회차 결과가 사라질 수 있습니다. 오늘은 새로 만드는 요청보다 이어서 작업하는 요청이 중요합니다.
-->

---

<section class="deck-slide section-center">
  <div>
    <div class="eyebrow">HOME</div>
    <h1 class="title">홈페이지는<br><span class="accent">입구</span>입니다</h1>
    <p class="subtitle">처음 온 방문자는<br>이 사람이 누구인지 먼저 봅니다.<br>그 다음 해본 일과 더 볼 자료를 찾습니다.</p>
  </div>
  <div class="slide-number">06 / 27</div>
</section>

<!--
Home을 내가 하고 싶은 말을 전부 넣는 곳으로 생각하면 금방 길어집니다. 오늘은 Home을 입구처럼 봅니다.
-->

---

<section class="deck-slide">
  <div class="eyebrow">INFORMATION ARCHITECTURE</div>
  <h1 class="title">정보를 네 갈래로 나눕니다</h1>
  <div class="grid-4 content-grid">
    <div class="card"><span class="badge">HOME</span><strong>첫인상과 안내</strong></div>
    <div class="card"><span class="badge">ABOUT</span><strong>소개 흐름</strong></div>
    <div class="card"><span class="badge">PROJECTS</span><strong>같은 형식의 사례 목록</strong></div>
    <div class="card"><span class="badge">POSTS</span><strong>글 중심 기록</strong></div>
  </div>
  <p class="subtitle">이 구분은 정답이 아니라 이번 수업의 기준입니다.</p>
  <div class="slide-number">07 / 27</div>
</section>

<!--
Home / About / Projects / Posts 구분을 정답처럼 말하지 않습니다. 다만 오늘은 같은 기준을 두고 실습해야 하므로 이 네 갈래로 나눕니다.
-->

---

<section class="deck-slide">
  <div class="eyebrow">HOME ROLE</div>
  <h1 class="title">Home은 첫인상과 안내입니다</h1>
  <ul class="big-list">
    <li>이름 또는 닉네임</li>
    <li>한 줄 소개</li>
    <li>관심 분야 2~3개</li>
    <li>About / Projects / Posts로 가는 링크</li>
  </ul>
  <div class="quote-panel">Home의 목표는 길게 설명하는 것이 아니라<br>다음 페이지로 자연스럽게 보내는 것입니다.</div>
  <div class="slide-number">08 / 27</div>
</section>

<!--
Home에서 완벽한 자기소개를 쓰려고 오래 멈추지 않게 합니다. 이름, 한 줄 소개, 관심 분야, 주요 링크 정도면 시작할 수 있습니다.
-->

---

<section class="deck-slide">
  <div class="eyebrow">ABOUT ROLE</div>
  <h1 class="title">About은 소개 흐름입니다</h1>
  <div class="split">
    <p class="subtitle">처음 보는 사람이 "이 사람이 어떤 배경과 관심사를 가진 사람인지" 이해하는 페이지입니다.</p>
    <div class="card"><span class="badge">CAN INCLUDE</span><strong>한 문장 소개, 관심 분야, 배우는 중인 것, 해본 일, 앞으로 만들고 싶은 것</strong><p>완성된 자기소개서가 아니라 초안이면 충분합니다.</p></div>
  </div>
  <div class="slide-number">09 / 27</div>
</section>

<!--
About은 긴 이력서가 아닙니다. 방문자가 이 사람이 어떤 사람인지 대략 이해할 수 있으면 됩니다.
-->

---

<section class="deck-slide">
  <div class="eyebrow">PROJECTS ROLE</div>
  <h1 class="title">Projects는 사례 목록입니다</h1>
  <div class="compare">
    <div class="card"><div class="label">ABOUT</div><div class="text">다양한 소개가 이어지는 흐름</div></div>
    <div class="card"><div class="label">PROJECTS</div><div class="text">비슷한 형식의 카드가 반복되는 목록</div></div>
  </div>
  <p class="subtitle">정식 출시 프로젝트가 아니어도 됩니다.<br>수업 실습과 학습 기록도 프로젝트 카드가 될 수 있습니다.</p>
  <div class="slide-number">10 / 27</div>
</section>

<!--
Projects를 말하면 참가자가 "나는 프로젝트가 없는데요"라고 느낄 수 있습니다. 정식 출시 프로젝트가 아니어도 된다고 먼저 말합니다.
-->

---

<section class="deck-slide">
  <div class="eyebrow">POSTS ROLE</div>
  <h1 class="title">Posts는 글 중심 기록입니다</h1>
  <div class="compare">
    <div class="card"><div class="label">PROJECTS</div><div class="text">카드와 상세정보</div></div>
    <div class="card"><div class="label">POSTS</div><div class="text">제목, 날짜, 요약, 태그가 있는 글 목록</div></div>
  </div>
  <div class="quote-panel">오늘 Posts는 완성된 블로그가 아닙니다.<br>글이 들어갈 자리를 먼저 만듭니다.</div>
  <div class="slide-number">11 / 27</div>
</section>

<!--
Posts를 만든다고 해서 오늘 블로그 시스템을 완성하는 것은 아닙니다. 오늘은 글 목록이 사이트 안에서 어떤 모양으로 보일지 먼저 잡습니다.
-->

---

<section class="deck-slide dark">
  <div class="eyebrow">TODAY'S SHAPE</div>
  <h1 class="title">오늘 만드는 기본 형태</h1>
  <div class="grid-4 content-grid">
    <div class="card"><span class="badge">HOME</span><strong>이름, 한 줄 소개, 주요 링크</strong></div>
    <div class="card"><span class="badge">ABOUT</span><strong>짧은 소개와 관심사</strong></div>
    <div class="card"><span class="badge">PROJECTS</span><strong>클릭 가능한 프로젝트 카드</strong></div>
    <div class="card"><span class="badge">POSTS</span><strong>샘플 글 목록</strong></div>
  </div>
  <p class="subtitle">완성된 문장보다 중요한 것은 나중에 바꿀 수 있는 자리입니다.</p>
  <div class="slide-number">12 / 27</div>
</section>

<!--
완성된 문장보다 중요한 것은 나중에 바꿀 수 있는 자리를 만드는 것입니다.
-->

---

<section class="deck-slide">
  <div class="eyebrow">PAGE VS SECTION</div>
  <h1 class="title">페이지와 섹션은 다릅니다</h1>
  <div class="compare">
    <div class="card"><div class="label">PAGE</div><div class="text">주소가 따로 있는 화면</div><p>예: <code>/about</code></p></div>
    <div class="card"><div class="label">SECTION</div><div class="text">한 페이지 안의 구역</div><p>예: Home 안의 관심 분야</p></div>
  </div>
  <div class="slide-number">13 / 27</div>
</section>

<!--
페이지와 섹션은 주소가 따로 있느냐로 판단하게 합니다. 이 구분이 잡히면 AI에게 요청할 때 결과가 덜 흔들립니다.
-->

---

<section class="deck-slide compact-slide">
  <div class="eyebrow">PRACTICE</div>
  <h1 class="title">페이지와 섹션을 구분해봅니다</h1>
  <div class="grid-2 content-grid">
    <div class="card"><span class="badge">PAGE</span><strong>About 화면을 따로 만들고 싶다</strong><p>주소가 따로 생깁니다.</p></div>
    <div class="card"><span class="badge">SECTION</span><strong>Home 안에 관심 분야 소개를 넣고 싶다</strong><p>한 페이지 안에 구역이 생깁니다.</p></div>
    <div class="card"><span class="badge">PAGE</span><strong>Projects 목록을 주소로 열고 싶다</strong></div>
    <div class="card"><span class="badge">SECTION</span><strong>첫 화면 아래에 연락처 블록을 넣고 싶다</strong></div>
  </div>
  <div class="slide-number">14 / 27</div>
</section>

<!--
진행자가 바로 답을 말하지 말고 참가자에게 먼저 물어봅니다. About 페이지와 Home 안의 About 섹션이 다르다는 감각만 잡으면 됩니다.
-->

---

<section class="deck-slide">
  <div class="eyebrow">ASTRO ROUTING</div>
  <h1 class="title">Astro에서는 파일이 주소가 됩니다</h1>
  <div class="code-panel">src/pages/index.astro     → /<br>src/pages/about.astro     → /about<br>src/pages/projects.astro  → /projects<br>src/pages/posts.astro     → /posts</div>
  <p class="subtitle">파일 이름을 잘 정하면 방문자가 열 수 있는 주소가 생깁니다.</p>
  <div class="slide-number">15 / 27</div>
</section>

<!--
Astro의 전체 라우팅 문법으로 깊게 들어가지 않습니다. 오늘은 src/pages 안의 파일이 주소가 된다는 감각만 잡으면 됩니다.
-->

---

<section class="deck-slide">
  <div class="eyebrow">SWIFTUI COMPARISON</div>
  <h1 class="title">SwiftUI와 비교하면<br>이동의 문제입니다</h1>
  <div class="compare">
    <div class="card"><div class="label">WEB</div><div class="text"><code>/about</code> 주소를 열면 About 페이지가 보임</div></div>
    <div class="card"><div class="label">SWIFTUI</div><div class="text"><code>NavigationLink</code>를 누르면 <code>AboutView</code>가 보임</div></div>
  </div>
  <p class="subtitle">공통점은 사용자가 어디로 이동할 수 있는지 정해둔다는 점입니다.<br>차이점은 웹은 주소, 앱은 화면 흐름이 더 중요하다는 점입니다.</p>
  <div class="slide-number">16 / 27</div>
</section>

<!--
Swift 앱을 조금 해본 참가자에게는 NavigationLink와 AboutView 정도로 비교합니다. 완전히 같은 개념이라고 말하지는 않습니다.
-->

---

<section class="deck-slide">
  <div class="eyebrow">LAYOUT</div>
  <h1 class="title">Layout은 공통 바깥 틀입니다</h1>
  <div class="compare">
    <div class="card"><div class="label">BAD</div><div class="text">about.astro, projects.astro, posts.astro에 Header 복붙</div></div>
    <div class="card"><div class="label">GOOD</div><div class="text">Layout 하나를 만들고 모든 페이지가 그 Layout을 사용</div></div>
  </div>
  <p class="subtitle">Layout은 여러 페이지가 같이 입는 공통 옷입니다.</p>
  <div class="slide-number">17 / 27</div>
</section>

<!--
Layout은 여러 페이지가 같이 쓰는 바깥 틀이라고 말하면 충분합니다. SwiftUI Layout 프로토콜 이야기가 아니라 공통 View 재사용 정도로만 연결합니다.
-->

---

<section class="deck-slide">
  <div class="eyebrow">NAVIGATION</div>
  <h1 class="title">Navigation은 안내판입니다</h1>
  <div class="code-panel">Home      /<br>About     /about<br>Projects  /projects<br>Posts     /posts</div>
  <p class="subtitle">Navigation이 있으면 방문자는 주소를 외우지 않아도 됩니다.</p>
  <div class="slide-number">18 / 27</div>
</section>

<!--
Navigation은 페이지 이동 링크 묶음입니다. Layout 안에 Navigation을 넣어 모든 페이지에서 같은 안내판이 보이게 합니다.
-->

---

<section class="deck-slide">
  <div class="eyebrow">COMPONENT</div>
  <h1 class="title">Component는 반복되는 화면 틀입니다</h1>
  <div class="grid-2 content-grid">
    <div class="card"><span class="badge">CARD CONTENT</span><strong>프로젝트 이름, 설명, 역할, 사용 도구, 결과, 자세히 보기</strong></div>
    <div class="card"><span class="badge">SEPARATION</span><strong>ProjectCard = 카드 모양<br>projects.json = 카드에 들어갈 내용 목록</strong></div>
  </div>
  <p class="subtitle">카드 모양은 한 번 만들고, 내용만 바꿔 끼우면 됩니다.</p>
  <div class="slide-number">19 / 27</div>
</section>

<!--
Component는 반복해서 쓰는 화면 틀이라고 설명하면 충분합니다. SwiftUI를 아는 참가자에게는 ProjectCardView 같은 작은 View를 떠올리면 된다고 말합니다.
-->

---

<section class="deck-slide">
  <div class="eyebrow">JSON DATA</div>
  <h1 class="title">JSON은 정보 파일입니다</h1>
  <div class="code-panel">src/data/projects.json = 프로젝트 정보 목록<br>src/data/posts.json    = 글 정보 목록</div>
  <ul class="big-list">
    <li>화면 코드에 문장을 흩뿌리지 않기</li>
    <li>항목을 나중에 추가하기 쉽게 하기</li>
    <li>외부 데이터가 들어와도 화면용 모양으로 바꿔 쓰기</li>
  </ul>
  <div class="slide-number">20 / 27</div>
</section>

<!--
JSON 문법을 자세히 설명하지 않습니다. 처음에는 표 같은 정보 파일이라고 생각해도 됩니다.
-->

---

<section class="deck-slide compact-slide">
  <div class="eyebrow">SLUG</div>
  <h1 class="title">slug는 주소에 쓰는 짧은 이름입니다</h1>
  <div class="code-panel">프로젝트 제목: 첫 개인 홈페이지<br>slug: first-homepage<br>상세 주소: /projects/first-homepage</div>
  <ul class="big-list">
    <li>한글 제목보다 주소로 쓰기 쉽습니다.</li>
    <li>카드에서 상세 페이지 주소를 만들 수 있습니다.</li>
    <li>나중에 항목이 늘어나도 연결 기준이 됩니다.</li>
  </ul>
  <div class="slide-number">21 / 27</div>
</section>

<!--
slug는 제목이 아니라 주소에 쓰는 짧은 이름이라고 말합니다. 동적 라우팅 심화는 오늘 다루지 않습니다.
-->

---

<section class="deck-slide dark">
  <div class="eyebrow">POSTS FIRST</div>
  <h1 class="title">Posts를 미리 만드는 이유</h1>
  <div class="flow">
    <div class="flow-item">샘플 글 데이터</div><div class="flow-arrow">→</div>
    <div class="flow-item">Posts 페이지</div><div class="flow-arrow">→</div>
    <div class="flow-item">나중에 외부 응답을 같은 모양으로 변환</div>
  </div>
  <ul class="big-list">
    <li>오늘은 API를 붙이지 않습니다.</li>
    <li>database, Integration token, secret, API 호출은 하지 않습니다.</li>
  </ul>
  <div class="slide-number">22 / 27</div>
</section>

<!--
오늘 Posts를 만든다고 해서 외부 콘텐츠 소스를 연결하는 것은 아닙니다. 먼저 글 목록이 화면에서 어떤 모양으로 쓰일지 잡아둡니다.
-->

---

<section class="deck-slide verify-slide">
  <div class="eyebrow">VERIFY</div>
  <h1 class="title">만든 뒤에는 검증합니다</h1>
  <div class="code-panel">npm run dev<br>→ Browser에서 /, /about, /projects, /posts 확인<br>→ Navigation 클릭<br>→ Projects 상세 링크 확인<br>→ npm run build<br>→ build 결과 또는 실패 로그 기록</div>
  <div class="compare">
    <div class="card"><div class="label">DEV</div><div class="text">내 컴퓨터에서 화면 확인</div></div>
    <div class="card"><div class="label">BUILD</div><div class="text">배포 전 검증</div></div>
  </div>
  <div class="slide-number">23 / 27</div>
</section>

<!--
AI가 파일을 만들었다고 바로 끝내지 않습니다. 브라우저에서 실제로 페이지가 열리는지 확인하고, build가 되는지 확인해야 합니다.
-->

---

<section class="deck-slide">
  <div class="eyebrow">DEPLOY LOOP</div>
  <h1 class="title">검증 후 GitHub에 올립니다</h1>
  <div class="flow">
    <div class="flow-item">commit</div><div class="flow-arrow">→</div>
    <div class="flow-item">push</div><div class="flow-arrow">→</div>
    <div class="flow-item">GitHub Actions</div><div class="flow-arrow">→</div>
    <div class="flow-item">GitHub Pages</div>
  </div>
  <div class="grid-4 content-grid">
    <div class="card"><strong>commit</strong><p>변경사항 저장점</p></div>
    <div class="card"><strong>push</strong><p>GitHub에 올리기</p></div>
    <div class="card"><strong>Actions</strong><p>배포 작업이 도는 곳</p></div>
    <div class="card"><strong>Pages</strong><p>방문자가 보는 실제 주소</p></div>
  </div>
  <div class="slide-number">24 / 27</div>
</section>

<!--
워크북 10단계와 연결되는 슬라이드입니다. 시간이 부족하면 여기까지 못 가도 실패가 아닙니다. build 결과, git status, Actions 실패 화면, Pages 반영 상태 중 하나라도 기록하면 됩니다.
-->

---

<section class="deck-slide workflow-slide dark">
  <div class="eyebrow">CODEX WORKFLOW</div>
  <h1 class="title">Codex와 작업할 때의 흐름</h1>
  <div class="workflow-row">
    <div class="code-panel">현재 상태 확인<br>→ 계획 받기<br>→ 수정할 파일 확인<br>→ 승인 후 진행<br>→ Browser 확인<br>→ build 확인<br>→ 결과 기록</div>
    <div class="quote-panel">아직 파일을 수정하지 말고,<br>먼저 계획을 설명해줘.</div>
  </div>
  <div class="slide-number">25 / 27</div>
</section>

<!--
데모에서 가장 강조할 것은 코드를 빠르게 쓰는 장면이 아닙니다. AI가 바로 파일을 고치기 전에 계획을 말하게 하는 습관입니다.
-->

---

<section class="deck-slide record-slide">
  <div class="eyebrow">RECORD</div>
  <h1 class="title">마지막에는 기록합니다</h1>
  <div class="grid-3 content-grid">
    <div class="card"><span class="badge">STATE</span><strong>열린 URL<br>안 열린 URL</strong><p>build 결과<br>또는 실패 로그</p></div>
    <div class="card"><span class="badge">STRUCTURE</span><strong>Projects / Posts<br>현재 상태</strong><p>AGENTS.md 갱신<br>또는 프롬프트 기록</p></div>
    <div class="card"><span class="badge">NEXT</span><strong>3회차 디자인<br>수정 재료</strong><p>고칠 화면<br>참고 레퍼런스</p></div>
  </div>
  <p class="subtitle">이 기록이 있으면 다음 세션에서 바로 이어갈 수 있습니다.</p>
  <div class="slide-number">26 / 27</div>
</section>

<!--
마지막에는 구현 욕심을 줄이고 기록으로 넘어갑니다. AGENTS.md는 실제 파일까지 고치면 좋지만 필수 완주 조건은 아닙니다.
-->

---

<section class="deck-slide section-center dark">
  <div>
    <div class="eyebrow">WORKBOOK</div>
    <h1 class="title">이제 워크북으로 갑니다</h1>
    <p class="subtitle">발표자료는 실습 진도표가 아닙니다.<br>오늘 만날 개념을 같은 언어로 맞추는 준비였습니다.</p>
    <div class="quote-panel">끝까지 못 해도 현재 상태와<br>다음 질문을 남기면 됩니다.</div>
  </div>
  <div class="slide-number">27 / 27</div>
</section>

<!--
여기서 발표를 종료합니다. 이후에는 진행자가 계속 강의하기보다, 참가자가 워크북을 보며 직접 움직이게 합니다.
-->
