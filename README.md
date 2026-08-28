# DADA 학습 — 대문

세 개의 영어 학습 앱으로 들어가는 한 장짜리 홈.

| 앱 | 주소 |
|---|---|
| 고등영어문법 | `grammar.dada-town.com` |
| 문장 패턴 드릴 | `pattern.dada-town.com` |
| 듣기 수업 도구 | `listen.dada-town.com` |

`index.html` 파일 하나가 전부다. 빌드 단계도, 의존성도 없다.
브라우저로 파일을 직접 열어도 그대로 보인다.

---

## 고치는 법

**주소가 바뀌면** — `index.html` 의 `<a class="app" href="...">` 세 줄만 고친다.

**앱을 추가하려면** — `<a class="app">` 한 덩어리를 복사해 붙이고 이름·설명·아이콘을 바꾼다.

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
