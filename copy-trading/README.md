# Copy Trading — Mobile Prototype

Flipster Copy Trading 모바일 프로토타입. **모바일 전용**, `375 × 812` (iPhone X~) 기준.

## 화면

| 파일 | 설명 |
|---|---|
| `index.html` | 첫 화면 — Copy Trading `Discover` 탭 (Today's Pick / Highest ROI / Masters in Action) + `Copy activity` 빈 상태 |

원본 디자인: [Figma — copy-trading `iteration02`](https://www.figma.com/design/XeuI6yfbNX2mXkfqTk9RwO/copy-trading?node-id=1-2783)

## 구성

- **Status bar / GNB**: iPhone 노치 스타일 상태바 + 하단 네비게이션(Market · **Copy** · Trade · Earn+ · Assets)
- **Tabs**: `Discover` / `Copy activity` (탭 전환 동작)
- **Today's Pick**: 가로 스크롤 트레이더 카드
- **Highest ROI**: 대표 트레이더 카드 (배지 · 30D ROI · P&L · Win rate/Turnover/Leverage · Copy)
- **Masters in Action**: 실시간 포지션 활동 리스트

인터랙션(프로토타입 수준): 탭 전환, GNB active 상태, `Copy` 버튼 토스트.

## 디자인 시스템

[Flipster Design System (FDS)](../affiliate-ia-kit/references/) 를 그대로 적용 — dark mode only, Pretendard, 4px spacing scale, FDS semantic 토큰(color / typography / spacing / corner-radius).

> 참고: egress 정책으로 Figma 원본 에셋(아이콘·차트·아바타 이미지) 다운로드가 차단되어, 모든 아이콘·미니 차트는 inline SVG로, 아바타는 그라디언트 + 이모지로 원본 지오메트리(사이즈)에 맞춰 재현했습니다.
