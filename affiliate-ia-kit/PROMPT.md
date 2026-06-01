# Affiliate Dashboard — Information Architecture 탐색 세션

## 📌 이 세션에서 하고 싶은 것

Flipster Affiliate 대시보드의 **정보 구조(IA)를 새로 탐색**하고 싶어. 현재 구조는 Figma에서 그대로 가져온 1차 버전이고, 사용자 시나리오 관점에서 더 나은 구조가 있는지 의논하고 싶음.

이 세션에서는 코드를 바로 고치기보다 **아이데이션 → 구조 옵션 비교 → 합의 후 적용** 순으로 진행하고 싶어.

---

## 🎯 컨텍스트

### 누가 보는 화면?
**Affiliate 파트너** — Flipster에 사용자를 추천하고 거래 수수료의 일부를 리워드로 받는 사람. 마케터, 인플루언서, 풀 운영자 등 다양함.

### 현재 화면에 담긴 정보 (대략 7개 섹션)
1. **Trading commission 카드** — 총 리워드 / 직접 추천인 수 / 평균 리워드, 직접 vs 서브 어필리에이트 비중
2. **Total USDT balance 카드** — 현재 잔액 + 최근 리워드 히스토리
3. **Events 카드 3개** — 진행 중인 프로모션/이벤트
4. **Rewards trend 차트** — 7/30/전체 기간 리워드 추이
5. **New referee conversion (퍼널)** — 클릭 → 가입 → 입금 → 첫 거래 전환율
6. **Top contributors** — 상위 추천인 리스트
7. **Referee history 테이블** — 일자별 리워드 내역 (펼치면 사용자별 상세)

### 탭 구조
Overview / **User List** / My referee group / Event center

---

## 💡 의논하고 싶은 IA 질문들

다음 질문들을 하나씩 짚어주면 좋겠어. 정답을 주기보다 **선택지와 트레이드오프**를 보여줘.

### Q1. Overview 의 정보 우선순위
지금은 "수익 요약 → 잔액 → 이벤트 → 추이 → 퍼널 → 기여자 → 히스토리" 순서야.
- Affiliate 가 매일 들어와서 가장 먼저 보고 싶은 게 뭘까?
- "잔액"이 "리워드 요약"보다 상단에 있어야 할까, 아니면 지금이 맞을까?
- Events 카드를 Overview 중간에 끼우는 게 적절할까, 아니면 별도 탭(Event center)으로만 두는 게 맞을까?

### Q2. KPI 의 절대값 vs 변화량
지금 KPI 카드는 절대값(17,190.32 USDT, 46명)만 보여줘.
- "어제 대비 +X" 같은 델타가 더 유용하지 않을까?
- 아니면 affiliate 는 누적이 중요하니까 절대값이 맞을까?
- 기간 필터(오늘/7일/30일/전체)를 KPI 에 붙이는 게 좋을까?

### Q3. "Direct referee vs Sub-Affiliate" 의 정보 중요도
지금 Trading commission 카드 안에 비중 막대 + 테이블로 들어가 있어.
- 이게 메인 카드 안에 들어가는 게 맞을까, 별도 섹션이 맞을까?
- 두 추천 유형을 더 강하게 비교할 수 있는 패턴이 있을까?

### Q4. 퍼널(New referee conversion) 의 위치
지금 차트 아래에 있어. 이 정보의 사용처는?
- "내 추천 링크 클릭률이 낮은가? 가입 전환이 낮은가?" 디버깅용
- 그렇다면 Overview 보다 별도 분석 페이지가 맞지 않을까?

### Q5. 테이블 vs 카드 vs 차트
Referee history 는 큰 테이블이야. 그런데:
- 일별 합계라면 차트가 더 직관적
- 사용자별 상세라면 검색/필터 가능한 테이블
- 두 정보를 한 테이블에서 펼치기(expand) 방식으로 합친 게 지금 구조인데, 이게 직관적일까?

### Q6. 탭 4개의 동등성
Overview / User List / My referee group / Event center 가 모두 같은 위계로 있어.
- 이 중에 "사실은 Overview 의 하위 섹션" 인 게 있지 않을까?
- "My referee group" 과 "User List" 의 차이는 사용자가 직관적으로 알 수 있을까?

---

## 🎨 디자인 시스템 (FDS) — 가드레일

새 IA 를 만들더라도 다음은 지켜야 함:

- **Dark mode only** — 라이트 모드 없음
- **FDS semantic tokens** 만 사용 — 하드코딩 hex 금지
- **Pretendard** sans, 숫자는 **monospace** (가격/수량/% 등 financial value)
- **4px spacing scale** — 4/8/12/16/24/32/40/48/64/80
- **Radius**: 0/4/8/12/16/full
- **컴포넌트**: Tabs(Large=48px Scrollable), Choice Chip(36px 데스크탑, full radius), Badge(20px), Button(Primary/Secondary × Accent/Neutral/Buy/Sell), Icon Button(4단계 hierarchy)

자세한 토큰/컴포넌트 스펙은 첨부된 `references/` 폴더 참고.

---

## 📂 첨부 파일

| 파일 | 용도 |
|---|---|
| `affiliate-dashboard.html` | **현재 상태** (1차 구현 완료, 메인 브랜치 격) |
| `affiliate-dashboard-ia-explore.html` | **탐색용 분기** (이 세션에서 수정할 파일) |
| `figma-preview.html` | Figma 원본 디자인 미리보기 |
| `references/*.md` | FDS 토큰/컴포넌트 레퍼런스 22개 |
| `SKILL.md` | FDS 사용 가이드 |

---

## 🛠 진행 방식 (제안)

1. 위 Q1~Q6 중 **2-3개** 같이 고르고 시작
2. 각 질문마다: **현재 상태 분석 → 대안 옵션 2-3개 → 트레이드오프 → 추천**
3. 결정된 방향만 `affiliate-dashboard-ia-explore.html` 에 적용
4. 적용 후 스크린샷으로 before/after 비교

준비됐으면 "Q1부터 시작하자" 라고 말해줘. 또는 다른 관점에서 시작하고 싶으면 그것도 OK.
