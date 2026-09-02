# DADA 학습 — 대문

네 개의 영어 학습 앱으로 들어가는 한 장짜리 홈.

| 앱 | 주소 |
|---|---|
| 고등영어문법 | `grammar.dada-town.com` |
| VOCAMAP | `vocamap.dada-town.com` |
| 문장 패턴 드릴 | `pattern.dada-town.com` |
| 듣기 수업 도구 | `listen.dada-town.com` |

`index.html` 파일 하나가 전부다. 빌드 단계도, 의존성도 없다.
브라우저로 파일을 직접 열어도 그대로 보인다.

앱은 **가로 타일**로 놓는다. 넓은 화면은 한 줄(4열), 460px 이하는 2×2.
360px 에서 4열이면 한 칸이 78px 라 앱 이름이 두 줄로 깨지기 때문이다.

아이콘을 위에, 글자를 아래에 두는 세로 타일 형태를 쓴다 — 가로로 여러 칸을 나누면
한 칸의 글자 폭이 좁아서, 카드를 옆으로 눕히면 설명이 여러 줄로 흘러 버린다.
그래서 설명도 짧게(10자 안팎) 유지한다.

---

## 고치는 법

**주소가 바뀌면** — `index.html` 의 `<a class="app" href="...">` 세 줄만 고친다.

**앱을 추가하려면** — `<a class="app">` 한 덩어리를 복사해 붙이고 이름·설명·아이콘을 바꾼 뒤,
`.apps` 의 `grid-template-columns` 를 열 수에 맞춰 고친다(좁은 화면 쪽 미디어 쿼리도 함께).

색·글꼴·모서리 값은 고등영어문법(engrammar)과 같은 토큰을 쓴다.
세 앱이 한 식구로 보이게 하려는 것이므로, 한쪽을 바꾸면 다른 쪽도 같이 맞춘다.

---

## 배포 — Cloudflare Pages

1. Workers & Pages → Create → Pages → **Connect to Git** → 이 저장소 선택
2. 빌드 설정

   | 항목 | 값 |
   |---|---|
   | Framework preset | None |
   | Build command | (비워둠) |
   | Build output directory | `/` |

3. Save and Deploy
4. Custom domains → `learn.dada-town.com` 연결

빌드가 없으므로 `git push` 하면 바로 반영된다.
