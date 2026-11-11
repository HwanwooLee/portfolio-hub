# 포트폴리오 허브 · 디자인 기준 (design.md)

> 기준 파일: `../spirit-test/index.html` (캠퍼스 정령 도감)
> 이 문서는 허브와 기존 결과물 5개(프로필, 플래너, 랜딩페이지, 모닝 브리핑, 정령 테스트)의 톤을 하나로 맞추는 기준이다.
>
> **표기 규칙**
> - 표시 없음 = 정령 테스트 코드에 **실제로 있는 값** (줄 번호 표기)
> - **[새로 추가]** = 허브를 위해 이번에 새로 정한 값. 정령 테스트에는 없다.

---

## 0. 허브 방향 한 줄 요약

장르는 **FPS·슈팅게임**. 정령 테스트의 "따뜻한 회흑 + 유리 패널 + 베벨 입체" 톤을 그대로 이어 가되, 더 묵직하고 실사·입체 느낌으로.

| 화면 | 내용 |
|---|---|
| 타이틀 | 불타는 격납고(4-0) 안, 입체 로고, "게임 시작" 버튼. 로고 뒤 문 너머로 불타는 도시. 조명이 숨쉬듯 일렁이고 불씨가 떠오른다 |
| 출격 연출 | 격납고가 떨리기 시작 → 문 너머 폭발이 다가옴 → 폭발 섬광 → 충격파에 불씨·연기·파편이 화면으로 쏟아짐 → 연기가 걷히며 로비 (4-2). 주인공은 HUD가 아니라 배경 세계 |
| 로비 | 같은 격납고 안 작전실. 위 HUD 바(경험치) + 요원 정보 + 작전 브리핑 창 + 작전 타일 5개와 잠긴 칸 1개 |

---

## 1. 색

### 1-1. 정령 테스트 `:root` 색 변수 (그대로 가져옴, 17~28줄)

| 변수 | 값 | 용도 |
|---|---|---|
| `--bg` | `#0B0C10` | 페이지 바탕. 따뜻한 회흑 |
| `--text` | `#EEE9E0` | 기본 글자 (흰색이 아닌 따뜻한 미색) |
| `--sub` | `#A19E97` | 보조 글자, 설명, 라벨 |
| `--dim` | `#66645F` | 가장 약한 글자, 힌트, 잠긴 항목 |
| `--accent` | `#D9D3C7` | 강조 기본 (정령 테스트에서는 결과에 따라 정령 색으로 바뀜) |
| `--accent-l` | `#F6F1E7` | 강조 밝은 면 (빛 받는 윗면) |
| `--accent-d` | `#5E5A52` | 강조 어두운 면 (큰 제목 두께감 그림자 색) |
| `--p-top` | `rgba(36,38,46,.58)` | 유리 패널 윗부분 |
| `--p-bot` | `rgba(17,18,23,.70)` | 유리 패널 아랫부분 |
| `--well` | `rgba(8,9,12,.72)` | 움푹 들어간 홈 (게이지 빈 칸, 체크 칸) |
| `--glass` | `blur(16px) saturate(1.2)` | 유리 뒤 흐림 (`backdrop-filter`) |
| `--bevel` | `inset 0 1px 0 rgba(255,255,255,.075), inset 0 -2px 0 rgba(0,0,0,.38), inset 0 0 0 1px rgba(255,255,255,.022)` | 베벨: 윗면 밝게·아랫면 어둡게 |
| `--lift` | `0 1px 0 rgba(0,0,0,.65), 0 14px 30px -16px rgba(0,0,0,.9)` | 바닥에서 떠 보이는 바깥 그림자 |
| `--r` | `12px` | 기본 모서리 둥글기 |
| `--f-disp` | `"Black Han Sans","Pretendard",sans-serif` | 제목 글꼴 |
| `--f-hud` | `"Chakra Petch","Pretendard",sans-serif` | HUD·숫자 글꼴 |

```css
/* 정령 테스트 :root 그대로 */
:root{
  --bg:#0B0C10;
  --text:#EEE9E0; --sub:#A19E97; --dim:#66645F;
  --accent:#D9D3C7; --accent-l:#F6F1E7; --accent-d:#5E5A52;
  --p-top:rgba(36,38,46,.58); --p-bot:rgba(17,18,23,.70); --well:rgba(8,9,12,.72);
  --glass:blur(16px) saturate(1.2);
  --bevel:inset 0 1px 0 rgba(255,255,255,.075), inset 0 -2px 0 rgba(0,0,0,.38), inset 0 0 0 1px rgba(255,255,255,.022);
  --lift:0 1px 0 rgba(0,0,0,.65), 0 14px 30px -16px rgba(0,0,0,.9);
  --r:12px;
  --f-disp:"Black Han Sans","Pretendard",sans-serif;
  --f-hud:"Chakra Petch","Pretendard",sans-serif;
}
```

### 1-2. 코드에 직접 박혀 있는 보조 색 (변수 아님, 참고용)

| 값 | 쓰인 곳 |
|---|---|
| `#FBF6EC` → `#E4DCCB` → `#CFC5B1` | 기본 버튼 면 그라데이션 (98줄) |
| `#2A241B` | 기본 버튼 글자 (98줄) |
| `#8C8371`, `#3A362E` | 기본 버튼 아래 두께 (99줄) |
| `#2C2F38` → `#22242B`, `#0E0F12` | 보조(ghost) 버튼 면·두께 (105~106줄) |
| `#4A463F`, `#3A3731` | 중간 제목·숫자 두께감 그림자 (115, 125줄) |
| `#07080A` → `#14151A` | 게이지 홈 (322줄) |
| `#D9775F`, `#EDA08A`, `#F0A58F`, `#5A2A20` | 경고 패널 "폭주 주의" (370~373줄) |
| `#8A8781` | 바닥글 (390줄) |

### 1-3. 정령 4종 색 (564~624줄, 결과 화면에서 `--accent` 3단계를 덮어씀)

| 정령 | 기본 `color` | 밝은 면 `light` | 어두운 면 `deep` |
|---|---|---|---|
| igna | `#DD6440` | `#F7B08C` | `#7E2C17` |
| volta | `#DDAA3A` | `#F6DC98` | `#7A5512` |
| mira | `#3FB0A3` | `#A2E3D9` | `#175F57` |
| nova | `#8576DD` | `#C6BEFA` | `#3A3082` |

> 정령 색은 **정령 테스트 안에서만** 쓴다. 허브의 공통 UI에는 쓰지 않는다. (특히 nova 보라색은 허브에서 금지 → 5장 참고)

### 1-4. 포인트 색: 앰버 **[새로 추가]**

허브에 새로 들어가는 색은 **이것 하나뿐**이다. 형광이 아닌, 녹슨 탄피·계기판 불빛 같은 차분한 앰버.

| 변수 | 값 | 용도 |
|---|---|---|
| `--amber-l` | `#E8C58C` | 밝은 면. 그라데이션 윗부분, 숫자 하이라이트 |
| `--amber` | `#C8913F` | 기본. 진행 중인 게이지, 출격 표시 면, 클리어 배지 |
| `--amber-d` | `#6B461A` | 어두운 면. 출격 표시 두께감 그림자, 그라데이션 아랫부분 |

```css
/* [새로 추가] 포인트 색 — 출격·진행·클리어 표시에만 */
:root{
  --amber-l:#E8C58C;
  --amber:#C8913F;
  --amber-d:#6B461A;
}
```

**쓰는 곳 (이 세 가지만)**
1. **출격** — 배경 세계의 불빛: 문 너머 불길, 폭발 불빛, 불씨, 바닥에 번지는 빛
2. **진행** — 경험치 막대와 역량 게이지 채움, 선택된 작전 타일 테두리
3. **클리어** — 결과물 카드의 "완료" 배지

**쓰지 않는 곳**: 배경, 본문 글자, 패널 면 전체, 일반 버튼, 장식선. 한 화면에서 앰버가 차지하는 면적은 작게 유지한다.

> volta의 `#DDAA3A`보다 채도·밝기를 낮춰서, 정령 테스트 안에서도 정령 색과 구분된다.

---

## 2. 글꼴 (3개만, 더 늘리지 않는다)

### 2-1. 불러오는 주소 (8~11줄 그대로)

```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/orioncactus/pretendard@v1.3.9/dist/web/static/pretendard.min.css">
<link rel="preconnect" href="https://fonts.googleapis.com"><link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<!-- 무료·상업적 이용 가능(SIL OFL): Black Han Sans(디스플레이), Chakra Petch(HUD) -->
<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Black+Han+Sans&family=Chakra+Petch:wght@500;600;700&display=swap">
```

| 역할 | 글꼴 | 굵기 | 변수 |
|---|---|---|---|
| 제목·버튼 로고 | Black Han Sans | 400 (한 굵기뿐) | `--f-disp` |
| 숫자·HUD | Chakra Petch | 500 / 600 / 700 | `--f-hud` |
| 본문 | Pretendard | 500 / 600 / 700 / 800 | `body` 기본 |

```css
/* 본문 기본 (31~35줄) */
body{
  font-family:"Pretendard",-apple-system,"Malgun Gothic",sans-serif;
  background:var(--bg); color:var(--text);
  -webkit-font-smoothing:antialiased; overflow-x:hidden; word-break:keep-all;
}
```

> 버튼 글꼴 참고: 정령 테스트의 기본 버튼(`.btn`)은 **Chakra Petch**로 "PLAY"를 썼다. 허브의 "게임 시작"처럼 한글 버튼은 Black Han Sans를 쓴다 **[새로 추가]** (아래 3-2 참고).

### 2-2. 크기 단계 (정령 테스트 실제 값)

| 단계 | 값 | 쓰인 곳 |
|---|---|---|
| 큰 제목 | `font-size:clamp(46px,9vw,92px); line-height:1.02` | 타이틀 로고 `.title h1` (76줄) |
| 큰 제목 (결과) | `font-size:clamp(40px,6vw,62px); line-height:1.08` | 정령 이름 `.info h2` (302줄) |
| 중간 제목 | `font-size:clamp(26px,4.2vw,40px); line-height:1.25` | 미션 제목 `.mtitle` (125줄) |
| HUD 큰 숫자 | `font-size:clamp(40px,6vw,56px)` (Black Han Sans) | 미션 번호 `.hud .mno b` (114줄) |
| 본문 큰 | `font-size:clamp(15px,2.2vw,18px)` | 부제·설명 `.title p`, `.mdesc` (78, 126줄) |
| 본문 | `font-size:16px; line-height:1.5` | 답 버튼 `.ans` (129줄) |
| 본문 작은 | `font-size:14px; line-height:1.55` | 패널 설명 `.skill .d` (314줄) |
| 작은 글씨 | `font-size:13px` | 힌트 `.hint`, 상단바 `.topbar` (108, 56줄) |
| 가장 작은 글씨 | `font-size:12px; line-height:1.7` | 바닥글 `footer` (390줄) |
| HUD 숫자 | `font-family:var(--f-hud); font-weight:700; font-size:17px; font-variant-numeric:tabular-nums` | 스탯 수치 `.stat .v` (332줄) |

### 2-3. 그림자 값 (정령 테스트 실제 값)

```css
/* 큰 제목: 아래쪽 두께감 + 그림자로 떠 보이게 (71~72줄) */
.disp{font-family:var(--f-disp);font-weight:400;letter-spacing:-.01em;color:var(--text);
  text-shadow:0 3px 0 var(--accent-d),0 4px 0 rgba(0,0,0,.5),0 14px 26px rgba(0,0,0,.55)}

/* 중간 제목 (125줄) */
.mtitle{text-shadow:0 2px 0 #3A3731,0 10px 20px rgba(0,0,0,.5)}

/* HUD 큰 숫자 (114~115줄) */
.hud .mno b{font-family:var(--f-disp);font-weight:400;
  text-shadow:0 3px 0 #4A463F,0 12px 22px rgba(0,0,0,.55)}

/* 작은 제목 (210줄) */
.hname{font-family:var(--f-disp);font-size:20px;text-shadow:0 2px 0 rgba(0,0,0,.6)}
```

규칙: **첫 번째 그림자 = 흐림 0, 아래로 2~3px 밀린 단단한 두께**, 두 번째 = 짙은 그림자 한 겹, 마지막 = 넓게 퍼지는 바닥 그림자. 빛나는 글로우는 쓰지 않는다.

### 2-4. 허브 입체 로고 그림자 **[새로 추가]**

정령 테스트 `.disp`의 구조를 그대로 두고 두께만 늘린다. 더 묵직하게.

```css
/* [새로 추가] 허브 타이틀 로고: 두께 3px → 단단한 층 4겹(6px) */
.logo{font-family:var(--f-disp);font-weight:400;letter-spacing:-.01em;color:var(--text);
  font-size:clamp(56px,11vw,128px);line-height:1;
  text-shadow:
    0 1px 0 #B9B2A4, 0 2px 0 #8C8371, 0 4px 0 var(--accent-d), 0 6px 0 #2A2722,
    0 7px 0 rgba(0,0,0,.6), 0 22px 36px rgba(0,0,0,.6)}
```

---

## 3. 부품 (정령 테스트 CSS 그대로 복사)

> 아래 코드는 정령 테스트에서 그대로 옮긴 것이다. 앞 1-1의 `:root` 변수가 먼저 있어야 동작한다.

### 3-1. 유리 패널

```css
/* 공통 표면 (64~67줄) — 클래스 이름만 허브에 맞게 바꿔 쓴다 */
.surface,.panel{
  background:linear-gradient(180deg,var(--p-top),var(--p-bot));
  -webkit-backdrop-filter:var(--glass);backdrop-filter:var(--glass);
  box-shadow:var(--bevel),inset 0 0 0 1px rgba(255,255,255,.04),var(--lift)}
.cut{border-radius:var(--r)}
.panel{padding:20px 22px}

/* 3D 위에 떠 있는 HUD 글 패널 (292~295줄) — 조금 더 투명한 변형 */
.hud-panel{padding:22px 24px;border-radius:18px;
  background:linear-gradient(180deg,rgba(26,27,33,.58),rgba(13,14,18,.7));
  -webkit-backdrop-filter:blur(14px) saturate(1.15);backdrop-filter:blur(14px) saturate(1.15);
  box-shadow:inset 0 1px 0 rgba(255,255,255,.08),inset 0 0 0 1px rgba(255,255,255,.05),0 24px 50px -24px rgba(0,0,0,.9)}

/* 알약 모양 작은 유리 라벨 (117~119줄) */
.chip{font-size:15px;color:var(--text);font-weight:700;padding:7px 12px;border-radius:999px;
  -webkit-backdrop-filter:var(--glass);backdrop-filter:var(--glass);
  background:linear-gradient(180deg,rgba(40,42,50,.6),rgba(24,25,31,.7));box-shadow:var(--bevel),0 4px 10px -6px rgba(0,0,0,.8)}

/* 강조 색이 살짝 섞인 패널 (315, 341줄) */
.panel.tinted{background:linear-gradient(180deg,color-mix(in srgb,var(--accent-d) 38%,var(--p-top)),var(--p-bot))}
```

### 3-2. 입체 버튼 (누르면 눌려 들어감)

```css
/* 기본 버튼 (96~103줄): 아래 6px 두께 → 누르면 translateY(6px)로 두께만큼 내려감 */
.btn{appearance:none;border:0;cursor:pointer;font:inherit;position:relative;border-radius:14px;
  font-family:var(--f-hud);font-weight:700;letter-spacing:.14em;font-size:18px;padding:16px 60px 15px;
  color:#2A241B;background:linear-gradient(180deg,#FBF6EC 0%,#E4DCCB 55%,#CFC5B1 100%);
  box-shadow:inset 0 1px 0 #fff,inset 0 -2px 0 rgba(0,0,0,.12),0 6px 0 #8C8371,0 7px 0 #3A362E,0 16px 24px -8px rgba(0,0,0,.7);
  transition:transform .08s,box-shadow .08s,filter .15s}
.btn:hover{filter:brightness(1.04)}
.btn:active{transform:translateY(6px);
  box-shadow:inset 0 1px 0 rgba(255,255,255,.7),inset 0 2px 6px rgba(0,0,0,.18),0 0 0 #8C8371,0 1px 0 #3A362E,0 4px 10px -4px rgba(0,0,0,.6)}

/* 보조 버튼 (104~107줄): 어두운 금속 */
.btn.ghost{color:var(--text);font-family:"Pretendard",sans-serif;font-weight:700;letter-spacing:0;font-size:15px;padding:14px 24px 13px;
  background:linear-gradient(180deg,#2C2F38 0%,#22242B 100%);
  box-shadow:inset 0 1px 0 rgba(255,255,255,.1),inset 0 -2px 0 rgba(0,0,0,.3),0 5px 0 #0E0F12,0 14px 22px -10px rgba(0,0,0,.8)}
.btn.ghost:active{transform:translateY(5px);box-shadow:inset 0 1px 0 rgba(255,255,255,.05),inset 0 2px 8px rgba(0,0,0,.45),0 0 0 #0E0F12,0 3px 8px -4px rgba(0,0,0,.6)}

/* 모바일: 버튼 가로 꽉 차게 (411줄) */
@media (max-width:760px){ .btn{width:100%} }
```

```css
/* [새로 추가] "게임 시작" 버튼: .btn 구조 그대로, 한글이라 글꼴만 Black Han Sans·자간 0 */
.btn.start{font-family:var(--f-disp);font-weight:400;letter-spacing:0;font-size:24px;padding:18px 64px 16px}
```

### 3-3. 게이지

```css
/* 유리관 안에 액체가 차오르는 게이지 (322~332줄) — 경험치 막대·진행률에 사용 */
.track{position:relative;height:16px;border-radius:999px;overflow:hidden;background:linear-gradient(180deg,#07080A,#14151A);
  box-shadow:inset 0 2px 4px rgba(0,0,0,.85),inset 0 -1px 0 rgba(255,255,255,.07),0 1px 0 rgba(255,255,255,.05)}
.track::after{content:"";position:absolute;inset:0;border-radius:inherit;pointer-events:none;
  background:linear-gradient(180deg,rgba(255,255,255,.2) 0,rgba(255,255,255,.05) 38%,transparent 55%,rgba(255,255,255,.05) 100%)}
.fill{position:absolute;inset:2px auto 2px 2px;width:0;max-width:calc(100% - 4px);border-radius:999px;
  background:linear-gradient(180deg,var(--cl) 0%,var(--c) 48%,var(--cd) 100%);
  box-shadow:0 0 12px color-mix(in srgb,var(--c) 45%,transparent),inset 0 -2px 3px rgba(0,0,0,.25);
  transition:width 1.1s cubic-bezier(.2,.8,.2,1)}
.fill::after{content:"";position:absolute;left:6px;right:6px;top:1px;height:40%;border-radius:999px;
  background:linear-gradient(180deg,rgba(255,255,255,.65),rgba(255,255,255,0))}
.gauge-v{text-align:right;font-family:var(--f-hud);font-weight:700;font-size:17px;font-variant-numeric:tabular-nums}

/* 칸으로 나뉜 진행 막대 (120~124줄) */
.bar{display:grid;grid-template-columns:repeat(6,1fr);gap:6px}
.bar i{height:8px;border-radius:999px;background:var(--well);box-shadow:inset 0 1px 3px rgba(0,0,0,.8),0 1px 0 rgba(255,255,255,.05);transition:background .3s}
.bar i.done{background:linear-gradient(180deg,#FBF6EC,#BDB4A2);box-shadow:inset 0 -1px 0 rgba(0,0,0,.2),0 0 8px rgba(255,240,215,.25)}
.bar i.now{background:linear-gradient(180deg,#8E877A,#5A554C);animation:pulse 1.2s ease-in-out infinite}
@keyframes pulse{50%{opacity:.55}}
```

```css
/* [새로 추가] 허브 게이지는 채움 색을 앰버로 연결 */
.fill{--cl:var(--amber-l);--c:var(--amber);--cd:var(--amber-d)}
```

### 3-4. 카드 테두리 (금속 프레임)

```css
/* 캐릭터 카드 금속 프레임 (238~244줄): 역할 색이 살짝 섞인 메탈 + 안쪽 베벨 */
.card .face{position:absolute;inset:0;overflow:hidden;border-radius:18px;border:7px solid transparent;
  background:
    radial-gradient(90% 80% at 50% 30%,color-mix(in srgb,var(--accent-d) 45%,#191A20),#0F1014 80%) padding-box,
    linear-gradient(155deg,#F4F1EA 0%,color-mix(in srgb,var(--accent-l) 55%,#9FA1A6) 14%,#3B3C42 32%,
      color-mix(in srgb,var(--accent) 40%,#C9C8C4) 50%,#2A2B30 68%,color-mix(in srgb,var(--accent-l) 40%,#B9B8B3) 86%,#4A4B50 100%) border-box;
  box-shadow:inset 0 0 0 1px rgba(0,0,0,.65),inset 0 2px 0 rgba(255,255,255,.12),inset 0 0 40px rgba(0,0,0,.55),
    0 0 0 1px rgba(0,0,0,.6),0 30px 50px -24px rgba(0,0,0,.9),0 0 70px -24px var(--accent)}

/* 카드 왼쪽 위 잘린 명판 태그 (247~251줄) */
.card .tag{position:absolute;left:-6px;top:20px;z-index:3;
  clip-path:polygon(0 0,100% 0,calc(100% - 10px) 100%,0 100%);
  background:linear-gradient(180deg,var(--accent-l),var(--accent) 60%,var(--accent-d));
  color:color-mix(in srgb,var(--accent-d) 50%,#000);font-family:var(--f-hud);font-weight:700;font-size:13px;letter-spacing:.16em;
  text-shadow:0 1px 0 rgba(255,255,255,.35);padding:6px 22px 5px 16px}

/* 잠긴 칸 (82~83줄): 움푹 들어간 홈 */
.slot.locked{background:linear-gradient(180deg,rgba(22,23,28,.66),rgba(14,15,18,.78));box-shadow:inset 0 2px 8px rgba(0,0,0,.6),inset 0 -1px 0 rgba(255,255,255,.04)}
```

> 로비 결과물 카드 5개는 이 금속 프레임을 쓴다. `--accent` 3단계는 기본값(미색 금속)을 유지하고, "클리어" 태그만 앰버로 바꾼다 **[새로 추가]**:
> ```css
> .card .tag.clear{--accent-l:var(--amber-l);--accent:var(--amber);--accent-d:var(--amber-d)}
> ```

### 3-5. 배경 (실사 사진 + 조명 + 노이즈)

```css
/* 배경 사진: 어둡게·살짝 흐리게, 천천히 확대 (37~43줄) */
.scene{position:fixed;inset:0;z-index:-1;pointer-events:none;overflow:hidden;background:#0B0C10}
.scene-l{position:absolute;inset:-3%;background:#0B0C10 center/cover no-repeat;opacity:0;
  filter:blur(3px) brightness(.5) saturate(.85);transition:opacity 1.4s ease;will-change:opacity,transform;
  animation:kenburns 32s ease-in-out infinite alternate}
.scene-l.on{opacity:1}
@keyframes kenburns{from{transform:scale(1.04) translate(0,0)}to{transform:scale(1.16) translate(-1.6%,-1.2%)}}

/* 덮개: 위에서 떨어지는 조명 + 비네팅 + 아래로 갈수록 어둡게 + 노이즈 (45~54줄) */
.bg{position:absolute;inset:0;
  background:
    radial-gradient(70% 55% at 50% -12%, rgba(255,244,226,.13), transparent 62%),
    radial-gradient(48% 40% at 50% -6%, color-mix(in srgb,var(--accent) 18%,transparent), transparent 70%),
    radial-gradient(ellipse 85% 75% at 50% 42%, transparent 35%, rgba(5,5,8,.78) 100%),
    linear-gradient(180deg,rgba(12,12,16,.35) 0%,rgba(10,10,13,.55) 55%,rgba(8,8,10,.85) 100%);
}
.bg::after{content:"";position:absolute;inset:0;opacity:.07;
  background-image:url("data:image/svg+xml;utf8,<svg xmlns='http://www.w3.org/2000/svg' width='180' height='180'><filter id='n'><feTurbulence type='fractalNoise' baseFrequency='.85' numOctaves='2' stitchTiles='stitch'/><feColorMatrix values='0 0 0 0 1 0 0 0 0 1 0 0 0 0 1 0 0 0 .55 0'/></filter><rect width='100%' height='100%' filter='url(%23n)'/></svg>");
}
```

> 허브는 사진 한 장을 깔지 않고 **불타는 격납고** 장면(4-0)을 배경으로 쓴다. 위 `.scene-l` 사진 겹 대신 원경 사진 + WebGL 3D를 쓰고, 덮개(`.bg`)의 비네팅과 노이즈(.07)는 그대로 올린다. WebGL을 못 쓸 때만 위 `.bg` 조명 덮개 전체를 쓴다. **[새로 추가]**

---

## 4. 연출 원칙 **[새로 추가]**

> 정령 테스트에 있는 참고 값: 화면 등장 `.5s` (58~60줄), 알 착지 흔들림 `thud .35s` 위 7px (151~152줄), 섬광 `flash .65s` (225~228줄), 명판 `slam .42s` (206~208줄), 진동 18~40ms (924, 947줄).
> 아래 허브 규칙은 이 값들을 바탕으로 새로 정한 것이다.

### 4-0. 배경 세계: 불타는 격납고

출격 연출의 주인공은 HUD가 아니라 **배경 세계 자체**다. 세 겹으로 쌓는다.

| 겹 | 내용 | 만드는 방법 |
|---|---|---|
| 원경 | 불타는 듯한 노을 하늘 + 멀리 도시 실루엣 | 실사 사진 `images/hangar-sky.jpg` (출처는 `images/credits.md`). 3D 공간의 400m 뒤에 세운 판처럼 배치 |
| 중경 | 문 너머 폐허: 무너진 고층 건물, 크레인 실루엣, 불길, 연기 기둥 | Three.js. 검은 실루엣, 멀수록 불빛에 물듦 |
| 근경 | 격납고 안: 철골 기둥, 천장 트러스, 반쯤 열린 문, 바닥 반사, 탐조등 빛줄기 3개, 불씨·먼지·연무 | Three.js. 폭 84 × 높이 44 × 깊이 90 (m) |

- **시차**: 마우스(휴대폰은 기울기, 둘 다 없으면 느린 자동 흔들림)에 따라 카메라가 좌우 최대 3.2m, 위아래 1.2m 움직인다. 겹마다 거리가 달라 저절로 다른 속도로 움직인다. 로고는 최대 4px.
- **로비 배경**: 타이틀과 같은 세계가 살아 있되, 글을 읽는 화면이라 어둡고 잔잔하게.
  - 카메라를 작전실 쪽으로 옮긴다: 왼쪽으로 14m, 높이 6m, 문 쪽으로 30m 다가감 (세로 화면은 8m·10m). 흔들림 없음, 시차는 35%.
  - 장면 전체에 `blur(3px) brightness(.64) saturate(.85)`. 해상도 70%, 휴대폰은 초당 30장.
  - 작전 브리핑 창 안쪽을 유리(`backdrop-filter:blur(14px) saturate(1.15)`, 어두운 면 투명도 .6~.8)로 바꿔 패널 뒤로 철골과 문 너머 불빛이 흐릿하게 비친다. 금속 프레임(3-4)은 그대로.
  - 불씨: 타이틀과 같은 불씨가 계속 떠오른다. 흐린 유리 뒤에서도 보이도록 크기 2.6배, 휴대폰은 개수 절반.
  - 문 너머 불빛: 불규칙하게 깜빡인다 (밝기 약 0.45 ~ 1.35배: 느린 일렁임 + 빠른 떨림 + 초당 6번 중 14% 확률로 확 밝아짐). 문 안쪽에 앰버 불빛 한 겹(투명도 최대 .34)이 같이 깜빡인다.
  - 연기층: 바닥에서 2~10m 높이로 넓고 얇은 연기 7겹(휴대폰 4겹)이 70~170초에 한 번 가로질러 흐른다. 투명도 최대 .1.
  - 넣지 않은 것: 열기 아지랑이(화면 전체를 일그러뜨려야 해서 글 읽는 화면에 부담), 패널 테두리에 직접 불빛 넣기(5장 "빛 번짐 금지").
  - 움직임 줄이기 설정이면 같은 구도의 정지 화면 한 장.
- **색**: 불빛은 `--amber` / `--amber-l`, 조명은 정령 테스트 덮개의 조명색 `rgb(255,244,226)`만 쓴다. 3D 재질의 회흑색(철골·벽·바닥)은 3D 안에서만 쓰고 UI로 꺼내지 않는다.
- **성능**: 휴대폰은 입자 수 38%, 해상도 상한 1.5배. 평균 프레임 시간이 24ms를 넘으면 해상도를 20%씩(최저 0.7배) 낮추고, 그래도 느리면 입자를 절반으로 줄인다.
- **대체**: WebGL이나 three.js를 못 쓰면 사진만 화면 가득 깔고 조명 덮개(3-5)를 올린다.

### 4-1. HUD 요소 규칙

> 출격 연출에서는 조준선·조준경·탄약 숫자를 **쓰지 않는다** (배경 세계가 주인공). 아래 규칙은 로비 등 다른 곳에 HUD 요소를 넣을 때만 적용한다.

| 요소 | 선 굵기 | 색 | 글꼴 |
|---|---|---|---|
| 모서리 프레임 (ㄱ자 4개) | 2px, 팔 길이 28px, 화면 가장자리에서 24px 안쪽 (모바일 16px) | `--sub` 투명도 .7 | — |
| 조준선 | 2px, 가운데 4px 비움, 팔 길이 10px | `--text` 투명도 .85 + 어두운 바깥선 `0 0 0 1px rgba(0,0,0,.5)` (밝은 배경에서도 보이게) | — |
| 조준경 원 | 1.5px | `--text` 투명도 .5 | — |
| 탄약 숫자 | — | 남은 숫자 `--amber-l`, 총탄 수 `/ 30` 은 `--dim` | Chakra Petch 700, `font-variant-numeric:tabular-nums`, 크기 `clamp(40px,6vw,56px)` |
| 시스템 점검 문구 | — | 기본 `--sub`, 끝의 "확인" 표시만 `--amber` | Chakra Petch 600, 13px, `letter-spacing:.06em` (정령 테스트 `.hudt`와 동일) |

- HUD 선은 전부 **단색 실선**. 글로우·그라데이션 선을 쓰지 않는다.
- 점검 문구는 한글로 쓴다. 영문 대문자는 숫자 단위(`AMMO`, `HP`) 정도만.
- 앰버는 "진행 중"이거나 "완료"인 것에만. 대기 상태 HUD는 회색 계열.

### 4-2. 출격 연출 타임라인

"게임 시작"을 누른 순간부터 로비가 다 보일 때까지 **4.75초**. 코드의 `T`, `FLASHES` 상수와 같은 숫자다.

| 시간 | 단계 | 일어나는 일 |
|---|---|---|
| 0 ~ 0.5s | — | 타이틀 글자·버튼이 사라지고 배경 세계만 남는다 |
| 0 ~ 1.3s | ① 떨림 시작 | 격납고가 "드드드드" 떨리기 시작 (세기 0 → 0.05). 천장에서 부스러기가 떨어지고(양 0 → 25%), 조명이 가끔 깜빡인다 (어두워지는 깊이 최대 20%) |
| 1.3 ~ 2.9s | ② 다가오는 폭발 | 떨림이 점점 세진다 (0.05 → 0.25). 부스러기 25 → 100%, 조명 깜빡임 깊이 최대 80%. 문 너머에서 폭발 불빛 5번: 1.30 / 1.75 / 2.10 / 2.40 / 2.65초, 거리 330 → 280 → 220 → 170 → 120m 로 다가오며 점점 크고 밝게 |
| **2.9s** | ③ 폭발 | 문 바로 밖에서 폭발. 섬광이 격납고 전체를 밝힌다. 떨림 최대 (1.0) |
| 2.9 ~ 3.8s | ④ 충격파 | 카메라가 0.9초 동안 14m 앞으로 밀리고 화각이 +9° 벌어졌다 돌아온다. 원경 사진도 12% 커진다. 불씨·파편·연기가 문에서 화면 쪽으로 쏟아진다 (초속 28~120m). 탐조등은 꺼진다 (밝기 12%) |
| 3.45 ~ 3.95s | ⑤ 연기 | 연기 장막이 화면을 덮는다 (0.5초) |
| 3.95s | — | 장막 뒤에서 로비로 교체 |
| 3.95 ~ 4.75s | ⑤ 걷힘 | 연기가 두 겹으로 흩어지며 로비가 드러난다 (0.8초) |

- **건너뛰기**: Esc 또는 화면 클릭(누른 뒤 0.2초부터). 장막 0.18초 → 로비 → 걷힘 0.35초. 소리는 0.15초 안에 줄인다.

#### 소리 설계

Web Audio로 직접 합성한다. 음원 파일·다른 게임 효과음을 쓰지 않는다. 출격 소리는 "효과음" 설정을 따른다 (아래 "배경음악·효과음").

**타이밍**
| 시간 | 소리 |
|---|---|
| 0 ~ 2.8s | 차오르는 소리 "드르르르릉". 음량과 음높이가 끝까지 계속 올라간다 |
| 2.8 ~ 2.9s | **정적 0.1초** (차오르던 소리를 0.004초 만에 끊음) |
| 2.9s | 폭발 "팍". 화면 섬광·충격파와 같은 순간. 출력 지연과 마스터 리미터 지연(6ms)만큼 앞당겨 예약한다 |
| 2.9 ~ 6.5s | 잔향과 땅 울림이 서서히 꺼짐 (로비가 나온 뒤에도 약 1.7초 남음) |

**차오르는 소리 (층 6개, 전체 음량 0.09 → 1.3초에 0.32 → 2.8초에 1.05, 마지막엔 마스터 리미터가 눌러 줌)**
| 층 | 만드는 법 | 층 음량 |
|---|---|---|
| 서브베이스 | 사인파 30 → 62Hz | .3 |
| 거친 엔진음 | 톱니파 60 → 124Hz + 사각파 45 → 93Hz를 포화시키고 저역 통과 420 → 2600Hz. 8 → 36Hz로 빨라지는 맥동("드르르")을 건다 | 1.05 |
| 엔진이 우는 소리 | 톱니파 210 → 640Hz를 좁은 대역(420 → 1300Hz)으로, 같은 맥동에 실음. 스피커에서 들리는 중음 | .1 → .8 |
| 금속 떨림 | 흰 잡음을 좁은 대역 3개(1250 / 2100 / 3300Hz, 30% 올라감)로 울리고 24 → 64Hz로 떨게 함 | .12 → .9 |
| 차오르는 바람 | 흰 잡음, 고역 통과 400 → 2600Hz | .005 → .2 |
| 다가오는 폭발 5번 | 갈색 잡음(280Hz 아래) + 사인파 78 → 34Hz. 1.30 / 1.75 / 2.10 / 2.40 / 2.65초 | .3 → .86 |

**터지는 소리 (층 4개 + 잔향)**
| 층 | 만드는 법 | 음량·길이 |
|---|---|---|
| 깊은 저음 한 방 | 사인파 100 → 30Hz (0.45초) + 사인파 52 → 26Hz (1.2초) + 같은 저음을 세게 포화시킨 배음(320Hz 중심) | .85, 1.9초 / .3, 2.5초 / .9, 1.2초 |
| 날카로운 파열음 | 흰 잡음 0.014초("딱") + 1500Hz 위 잡음 0.13초 + 파편 자글거림(3.2kHz 중심, 1.4초) | 1.3 / 1.1 / .8 |
| 폭발 몸통 | 흰 잡음, 저역 통과 8000 → 180Hz로 어두워짐 + 중음 "콰-"(650Hz 중심 대역 잡음) | 1.05, 2.4초 / 1.8, 1.8초 |
| 땅 울림 | 갈색 잡음(150Hz 아래) | .4, 3.3초 |
| 잔향 | 직접 만든 3.4초짜리 감쇠 잡음을 컨볼버에 넣음. 파열음과 몸통만 보냄 | 보내는 양 .6, 돌아오는 양 1.5 |

**마지막 단**: 출격 소리도 아래 "전체 음량 구조"의 마스터 하나를 거친다 (따로 두던 리미터는 없앴다).
렌더링해서 잰 값: 최댓값 0.93, 정적 구간 0.002, 폭발 시작은 예약 시각과 같다 (리미터 지연 6ms를 앞당겨 보정).

#### 배경음악·효과음

모두 Web Audio로 직접 합성한다. 다른 게임·영화 음악과 효과음을 쓰지 않는다.

**배경음악**: 박진감 넘치는 시네마틱 액션. 묵직하고 긴장감 있지만 무너진 느낌이 아니라 "이제 출격한다"는 추진력. **120 BPM, D 단조, 8마디(16초) 반복.** 발진기·잔향은 계속 돌고 음표만 0.35초 앞서 예약해서 이음매가 없다.

- 진행: Dm · Dm · B♭ · B♭ · F · C · Gm · A. B♭·F·C에서 밝게 풀리고, 마지막 A(장화음)에서 긴장이 최고로 올라 다시 Dm으로 돌아간다. 멜로디는 없다.

| 층 | 만드는 법 | 위치 (좌우 / 앞뒤) |
|---|---|---|
| 저음 오스티나토 | 16분음표로 쉬지 않고 몰아치는 톱니파 둘. 3-3-2 강세마다 필터가 열림 | 가운데 / 가까이 (잔향 없음) |
| 서브 저음 | 근음 사인파, 마디의 1·3박 | 가운데 / 가까이 |
| 현악 스타카토 | 8분음표로 화음 음을 짧게 끊음 (300Hz~3kHz) | 좌우 번갈아 ±0.45 / 중간 |
| 킥 | 140 → 42Hz + 포화 배음(240Hz) + 딸깍 | 가운데 / 가까이 |
| 스네어 | 2·4박, 잡음 1.9kHz + 몸통 210Hz | 가운데 / 가까이 |
| 큰 북(톰) | 마디 끝 3타(150 / 120 / 95Hz). 4마디째는 반 마디 동안 북을 몰아치고 스네어가 쌓임 | 좌우 ±0.25 / 가까이 |
| 하이햇 | 7.5kHz 위 아주 작게 (효과음 대역과 안 겹침) | 오른쪽 0.35 / 가까이 |
| 상승 아르페지오 | 화음 7음이 위로 올라가는 16분음표. 4마디째 한 번, 8마디째 크게 차오르며 밝아짐 | 14초 주기로 좌우를 오감 + 좌우로 튀는 메아리(3/16박) / 중간 |
| 차오르는 소리 | 잡음이 300 → 6000Hz로 열리며 커짐. 4마디째 반 마디, 8마디째 한 마디 | 가운데 / 중간 |
| 터짐 | 1·5마디 첫 박: 넓게 퍼지는 금속 잡음 + 낮은 쿵 | 좌우 ±0.55 / 중간 |
| 넓은 패드 | 화음 4음, 왼쪽·오른쪽 톱니파를 살짝 다르게. 1400Hz 아래, 마디마다 미끄러지듯 바뀜 | 좌우 끝 ±0.8 / 멀리 (잔향 많이) |

- 잔향: 3.2초, 좌우 채널을 따로 만들어 넓게. 먼 층(패드 .9, 아르페지오 .4, 터짐 .5)일수록 많이, 가까운 층(저음·킥 0)은 없음.
- 저음과 리듬은 가운데라 휴대폰 한쪽 스피커로 들어도 비지 않는다. 좌우 폭(side/mid)은 약 0.73.
- 음악 버스 압축(기준 -28dB, 4:1)으로 타격을 고르게 눌러 촘촘하게.
- 시작: 브라우저가 자동 재생을 막으므로 **첫 클릭·터치·키 입력**(Esc 제외) 순간부터, 약 4초에 걸쳐 들어온다.
- 출격: 차오르는 동안 35%로 비켜 주고, **폭발 직전 정적(2.8초)부터 8%**. 로비가 나타나면 다음 16분음표를 1마디 첫 박으로 다시 시작해 "터짐"과 함께 **바로 힘차게** 들어온다 (0.1초 안에 원래 음량). 건너뛰기 때도 같다.
- 다른 탭으로 가면 조용히 꺼졌다가 돌아오면 다시 올라온다.

**효과음**: 버튼, 작전 타일, 링크에 적용. 두 소리는 높이와 무게가 확실히 다르다.
| 소리 | 언제 | 만드는 법 |
|---|---|---|
| "틱" (가볍고 금속성) | 마우스를 올릴 때 (요소에 **들어갈 때 한 번만**, 0.04초 안에 연달아 나지 않음), 키보드 ← → 로 작전 타일을 바꿀 때 | 비정수배 배음 1720 / 2580 / 3610Hz가 0.03~0.045초에 꺼짐 + 3kHz 딸깍 0.005초 |
| "철컥" (묵직한 기계식) | 클릭할 때, Enter로 시작·작전 진입할 때 | "철": 포화시킨 사인파 170 → 58Hz 쿵 + 650Hz·1150Hz 대역 잡음 / 0.045초 뒤 "컥": 3kHz 딸깍 + 걸쇠 울림 1330 / 1990 / 2740 / 3520Hz |

- 터치 기기는 올림 소리가 없다. 회색으로 꺼진 버튼(`aria-disabled`)은 소리가 없다.

#### 전체 음량 구조

모든 소리(배경음악·효과음·출격)는 **마스터 하나**를 거쳐 나간다:
`MASTER_VOLUME`(스크립트 맨 위 상수, 기본 1.0) → 리미터(`DynamicsCompressor`: 기준 -3dB, 비율 20:1, 반응 1ms, 복귀 120ms) → 부드러운 넘침 방지(0.8까지 그대로, 위는 0.93 아래로 접음) → 스피커.

- 크롬의 압축기는 막 만들어진 뒤 약 0.15초 동안 첫 소리를 크게 눌러 버린다 (측정: 0.54 → 0.13). 그래서 마스터는 첫 클릭·키 입력 순간 미리 만들고, 처음 0.25초는 압축기를 우회한다.
- 노트북·휴대폰 스피커는 150Hz 아래가 거의 안 나온다. 모든 소리는 **150Hz~4kHz 성분을 충분히** 갖는다. 저음은 남기되 그것만으로 들리게 하지 않는다.

**음량 관계** (렌더링해서 잰 값, dBFS. 대역은 150Hz 아래 / 150Hz~2kHz / 2kHz 위)
| 소리 | 최댓값 | 실효값 | <150Hz | 150Hz~2kHz | >2kHz |
|---|---|---|---|---|---|
| 배경음악 | 0.51 | -22.6 | -26.6 | -24.8 | -43.2 |
| "틱" | 0.79 | -28.2 (0.3초) | -77.6 | -30.3 | -32.3 |
| "철컥" | 0.66 | -23.6 (0.4초) | -30.5 | -26.0 | -30.2 |
| 출격 차오름 (0~2.8초) | 0.93 | -11.8 | -13.4 | -17.4 | -26.4 |
| 출격 폭발 (2.9초~) | 0.93 | -15.1 | -19.3 | -19.4 | -21.0 |

- 배경음악 최댓값 < 효과음 최댓값 < 출격. 효과음("틱"·"철컥")은 배경음악이 거의 없는 2kHz 위 대역에 에너지가 있어서 배경음악 위로 또렷이 들린다.
- 배경음악은 오래 들어도 거슬리지 않도록 실효값 -20dB 아래로 둔다. 2kHz 위는 효과음보다 10dB 넘게 작게 (하이햇은 7.5kHz 위로만). 출격 중에는 35% → 8%로 내려간다.

**켜기/끄기**: 화면 오른쪽 위 "배경음악", "효과음" 버튼 두 개 (`.btn.ghost.sm`). 각각 따로 켜고 끄며, 브라우저에 저장(`hubMusic`, `hubSfx`)해서 다시 들어와도 유지된다. 로비에서는 위 HUD 바 안 "타이틀로" 왼쪽으로 옮겨 간다. 출격 소리는 "효과음"을 따른다.

### 4-3. 떨림·섬광 규칙

**출격 연출 안에서는 떨림이 점점 세지다 폭발 순간 최대가 된다. 로비·버튼·카드에서는 흔들림 금지.**

떨림은 화면(DOM)이 아니라 **3D 카메라**를 흔든다. 세기 1 = 카메라가 좌우 약 ±1.3m, 위아래 약 ±1m 움직이는 정도 (가까운 기둥은 크게, 먼 도시는 거의 안 움직임).

| 구간 | 떨림 세기 | 기울어짐(roll) |
|---|---|---|
| ① 0 ~ 1.3s | 0 → 0.05 (일정하게 증가) | 최대 0.06° |
| ② 1.3 ~ 2.9s | 0.05 → 0.25 (뒤로 갈수록 빠르게 증가) + 폭발 불빛마다 순간 +0.02 ~ +0.10 | 최대 0.4° |
| ③ 2.9s | **1.0** (최대) | 최대 1.15° |
| ④ 2.9s 이후 | `1.0 × e^(-3.2t)` 로 줄어듦 (0.5초 뒤 0.2, 1초 뒤 0.04) | 같이 줄어듦 |
| 로비·타이틀 | **0** | 0 |

- 떨림 주파수: 15 / 24 / 37Hz 를 섞는다 (좌우), 17 / 27Hz (위아래), 11Hz (기울어짐).
- 섬광: 폭발 순간 **한 번만**. 화면에 흰 덮개를 씌우지 않고, 장면 안의 불빛 세기를 올려서 밝힌다 (문 쪽 빛 최대 약 23배, 노출 최대 +72%. 0.2초 뒤 절반 아래로, 1.5초 안에 원래대로).
- 다가오는 폭발 불빛 5번은 문 너머에만 보이는 작은 불빛이다 (각 0.6초 안에 꺼짐). 격납고 전체를 밝히는 섬광은 ③ 한 번뿐.
- 진동(`navigator.vibrate`)은 쓰지 않는다.

**금지**: 떨림·섬광을 버튼 클릭, 카드·타일 선택, 로비 진입 뒤, 타이틀 대기 화면에 쓰지 않는다. 로비에서는 화면이 흔들리는 일이 없다.

### 4-4. 화면 전환 속도

| 전환 | 길이 | 곡선 |
|---|---|---|
| 일반 화면 등장 | 0.5s, 아래에서 12px 올라오며 | `ease` (정령 테스트 `@keyframes in` 그대로) |
| 출격 → 로비 | 연기 덮임 0.5s + 걷힘 0.8s | 일정한 속도 |
| 로비 → 타이틀 | 연기 덮임 0.2s + 걷힘 0.3s | 일정한 속도 |
| 작전 브리핑 내용 교체 | 0.28s, 옆에서 14px | `cubic-bezier(.2,.8,.2,1)` |
| 게이지 차오름 | 1.1s | `cubic-bezier(.2,.8,.2,1)` (정령 테스트 `.fill` 그대로) |
| 버튼 눌림 | 0.08s | 정령 테스트 `.btn` 그대로 |

### 4-5. 움직임 줄이기 설정 (prefers-reduced-motion)

정령 테스트는 모든 움직임을 끄는 한 줄(414줄)과, 부화 연출 대신 결과만 페이드로 보여 주는 `calm` 처리(220~223, 876~879줄)를 쓴다. 허브도 같은 방식을 따른다.

```css
/* 정령 테스트 414줄 그대로 */
@media (prefers-reduced-motion:reduce){*{animation:none!important;transition:none!important}}
```

**허브의 대체 방법**
| 원래 연출 | 움직임 줄이기일 때 |
|---|---|
| 배경 세계의 시차, 불씨, 조명 일렁임 | 3D 장면을 **정지 화면 한 장**으로만 그린다 (창 크기가 바뀔 때만 다시 그림) |
| 출격 연출 (떨림, 폭발, 충격파, 소리) | **전부 없음** |
| 타이틀 → 로비 | 어두운 장막 페이드만: 덮임 0.25s → 로비 → 걷힘 0.35s (연기 겹이 흩어지는 움직임 없음) |
| 게이지 차오름, 브리핑 교체 | 바로 표시 |

> 주의: 위 CSS 한 줄은 `animationend` / `transitionend` 이벤트도 발생하지 않게 만든다. 그래서 장막 페이드는 CSS가 아니라 JS가 투명도를 직접 바꾸고, 연출의 다음 단계는 시간으로 넘긴다. 움직임 줄이기 여부는 JS에서 `matchMedia("(prefers-reduced-motion: reduce)")`로 확인한다 (정령 테스트 844, 876줄 방식).

### 4-6. 마우스 포인터 **[새로 추가]**

| 상태 | 모양 | 색 | 파일 |
|---|---|---|---|
| 기본 | FPS 조준선: 가운데 점(지름 2.8px) + 끊어진 십자선(가운데 11px 비움, 팔 7px) | `--text` #EEE9E0 | `images/cursor/aim.svg` |
| 누를 수 있는 곳 (버튼, 작전 타일, 링크) | "조준 고정": 십자선이 안쪽으로 좁혀지고(팔 4px) 네 모서리에 괄호가 생김 | `--amber` #C8913F, 가운데 점 `--amber-l` | `images/cursor/lock.svg` |
| 글 입력칸 | 브라우저 기본 글자 커서 | — | — |

- 크기 32×32px, 선 굵기 2px. 밝은 배경에서도 보이도록 같은 모양을 4px 굵기의 어두운 선(#0B0C10, 투명도 .75)으로 먼저 깔고 그 위에 그린다.
- 클릭 지점은 조준선 **정중앙** `16 16`. 그림을 못 불러오면 `crosshair` / `pointer`로 대체된다.
- 마우스가 있는 기기에만 적용한다 (`(hover:hover) and (pointer:fine)`). 휴대폰은 적용하지 않는다.
- CSS의 다른 `cursor` 규칙보다 뒤에 둔다 (앞에 두면 `.btn{cursor:pointer}`에 덮인다).
- SVG 주석 안에 `--`(하이픈 두 개)를 쓰지 않는다. XML 오류가 나서 그림 전체가 안 읽힌다.

---

## 5. 하지 말 것 (AI가 만든 티 나는 디자인)

| 하지 말 것 | 대신 이렇게 |
|---|---|
| 보라·파랑 네온 그라데이션, 무지개 그라데이션 | 회흑 바탕 + 미색 금속 + 앰버 하나. 그라데이션은 같은 색의 밝은 면 → 어두운 면(위 → 아래)만 |
| 여기저기 빛 번짐 (`box-shadow:0 0 30px 색`) | 빛은 위에서 떨어지는 조명 한 곳(`.bg`)과 게이지 채움에만. 출격 섬광은 한 번뿐 |
| 자간 넓힌 영문 대문자 남발 | 한글 위주. 넓은 자간 영문은 로고 위 작은 부제 한 줄, 명판 태그 정도만 (정령 테스트 297줄 주석 "자간 넓힌 영문은 여기만"과 같은 원칙) |
| 1px 테두리 박스 반복 (`border:1px solid`) | 테두리 대신 `--bevel`(윗면 밝게·아랫면 어둡게) + `--lift`(바깥 그림자)로 면을 구분 |
| 장식 개수 늘리기 (아이콘, 선, 점, 배지 추가) | 입체감은 **조명·질감·그림자**로. 노이즈 질감(.07), 베벨, 두께감 그림자, 금속 프레임 |

추가로 지킬 것
- 새 글꼴, 새 색을 더하지 않는다. 필요하면 기존 변수의 투명도만 바꾼다.
- 글자색에 순백(`#fff`)을 쓰지 않는다. `--text`(`#EEE9E0`)를 쓴다.
- 정령 색 4종(특히 nova `#8576DD` 보라)을 허브 공통 UI로 끌어오지 않는다.
- 이모지를 아이콘 대신 쓰지 않는다.
