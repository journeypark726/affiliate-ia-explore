# FDS Choice Chip Reference

**Purpose:** A choice chip lets the user select one option from a set. Only one chip can be selected at a time — selecting a new chip unselects the previous one. One chip should always be pre-selected by default (like radio buttons), ideally the most common or desired option.

**Platform:** iOS ✅, Android ✅, Web ✅

---

## Component Properties

| Property | Values |
|---|---|
| **Type** | `Selected`, `Unselected` |
| **Content** | `Text only`, `Text+Badge`, `Icon`, `Icon+Badge`, `Icon only` |
| **State** | `Enabled`, `Hover` (=Pressed), `Focus` (Web only) |
| **Radius** | `Full radius` (default), `8px` (option) |

> No Disabled state for Choice Chip.

---

## States

| State | Selected | Unselected |
|---|---|---|
| Enabled | ✅ | ✅ |
| Hover (=Pressed) | ❌ | ✅ |
| Focus | ✅ | ✅ |

> **Selected일 때는 Hover/Pressed를 적용하지 않음** — Segmented Control, Tabs와 동일한 패턴.
> Focus는 Web only.

---

## Radius

| Option | Value | When to use |
|---|---|---|
| Default | Full radius (pill) | 일반적인 사용 |
| Option | 8px | 주변 UI(버튼, 컨테이너 등)가 각진 스타일일 때 자연스럽게 어우러지도록 사용 |

> **Why 8px radius option?** Dropdown Chip과 동일한 이유 — 주변 UI가 각진 스타일일 때 full radius보다 8px이 더 자연스럽게 어우러짐.

---

## Anatomy

| Content type | Description |
|---|---|
| Text only | 텍스트만 |
| Text+Badge | 텍스트 + 숫자 뱃지 |
| Icon | 아이콘 + 텍스트 |
| Icon+Badge | 아이콘 + 텍스트 + 숫자 뱃지 |
| Icon only | 아이콘만 (텍스트 없음) |

> **Badge는 Choice Chip 전용으로 커스텀 개발** — 일반 FDS Badge 컴포넌트가 아님.

---

## Status Badge (Red dot)

- Red dot은 **Unselected 상태에서만** 노출
- 선택(Selected) 시 red dot 사라짐
- **Red dot border color 변경 가능** — 개발적으로 오픈된 구조로, BG level 0~3 어떤 배경 컬러가 와도 자연스럽게 대응 가능

---

## Spacing Spec

> 폰트와 아이콘 크기는 Mobile·Desktop 동일 — 좌우 및 상하 여백만 다름

**Height (fixed)**

| Platform | Height |
|---|---|
| Mobile web / App | 32px |
| Desktop | 36px |

**Padding (left \| gap \| right)**

| Content | Mobile web / App | Desktop |
|---|---|---|
| Only Text | 12 \| 12 | 16 \| 16 |
| Text+Badge | 12 \| 4 \| 8 | 16 \| 4 \| 12 |
| Icon | 8 \| 4 \| 12 | 12 \| 4 \| 16 |
| Icon+Badge | 8 \| 4 \| 4 \| 8 | 12 \| 4 \| 4 \| 12 |
| Icon only | 8 \| 8 | 12 \| 12 |

### Group Spacing

- Chip 간 간격: **8px** (Mobile / Desktop 동일)

---

## UX Usecase

### 그룹으로 사용
- 여러 옵션 중 하나를 선택하는 필터 (예: 5m / 1h / 24h 시간 필터)
- 선택된 chip은 Selected 상태로 강조

### 단일로 사용
- 두 가지 뷰 전환 (예: Allocation / Trend)

---

## Audit Checklist

```
🔴 Critical
- Non-FDS Choice Chip component detected
- Text+Badge 또는 Icon+Badge에 일반 FDS Badge 컴포넌트 사용
  → Choice Chip의 Badge는 전용 커스텀 컴포넌트 — 일반 FDS Badge 사용 불가

🟡 Warning
- Focus state applied on iOS/Android (Focus is for web only)
- Selected 상태에 Hover/Pressed 적용
  → Selected일 때는 Hover/Pressed를 적용하지 않음
- Mobile chip height not 32px / Desktop chip height not 36px
- Padding values not matching platform spec
  → Mobile: Only Text(12|12), Text+Badge(12|4|8), Icon(8|4|12), Icon+Badge(8|4|4|8), Icon only(8|8)
  → Desktop: Only Text(16|16), Text+Badge(16|4|12), Icon(12|4|16), Icon+Badge(12|4|4|12), Icon only(12|12)
- Red dot applied on Selected state
  → Red dot은 Unselected 상태에서만 노출
- 8px radius used without surrounding angular UI context

🟢 Tip
- Group으로 사용할 때 chip 간 간격은 8px 권장
- Red dot border color는 배경에 맞게 조정 가능 (BG level 0~3 대응)
```
