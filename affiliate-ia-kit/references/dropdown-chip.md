# FDS Dropdown Chip Reference

**Purpose:** A dropdown chip is a chip-style trigger used to select options from a dropdown.

**Platform:** iOS ✅, Android ✅, Web ✅

---

## Component Properties

| Property | Values |
|---|---|
| **Type** | `Primary`, `Secondary` |
| **Content** | `Icon`, `Image`, `Only text` |
| **Highlight selection** | `ON`, `OFF` (Primary only) |
| **State** | `Enabled`, `Hover` (=Pressed), `Focus` (Web only), `Disabled` |
| **Radius** | `Full radius` (default), `8px` (option) |

---

## Type

### Primary
- Background color 있음
- **Highlight selection ON/OFF** 옵션 제공 — 상황에 따라 토글 가능
  - **ON:** 배경 컬러 강조 적용 (선택된 상태 시각적 구분)
  - **OFF:** 기본 배경 스타일

### Secondary
- 배경 없음 (transparent)
- **폰트 웨이트 Strong 고정** — 배경이 없기 때문에 텍스트로 강조를 주는 형태
- Highlight selection 없음

---

## Radius

| Option | Value | When to use |
|---|---|---|
| Default | Full radius (pill) | 일반적인 사용 |
| Option | 8px | 주변 UI(버튼, 컨테이너 등)가 각진 스타일일 때 자연스럽게 어우러지도록 사용 |

> **Why 8px radius option?** Full radius가 기본이지만, 주변 UI가 각진 스타일일 때 8px이 더 자연스럽게 어우러짐. 주변 스타일과의 조화가 필요할 때 선택적으로 사용.

---

## Anatomy

| Content type | Leading element | Chevron |
|---|---|---|
| Icon | 20×20px icon | 16×16px |
| Image | 24×24px image | 16×16px |
| Only text | — | 16×16px |

---

## Spacing Spec

> 폰트와 아이콘 크기는 Mobile·Desktop 동일 — 좌우 및 상하 여백만 다름

### Primary

**Height (fixed)**

| Platform | Height |
|---|---|
| Mobile web / App | 32px |
| Desktop | 36px |

**Padding (left \| gap \| gap \| right)**

| Content | Mobile web / App | Desktop |
|---|---|---|
| Icon | 8 \| 4 \| 4 \| 8 | 12 \| 4 \| 4 \| 12 |
| Image | 4 \| 4 \| 4 \| 8 | 4 \| 4 \| 4 \| 12 |
| Only text | 12 \| 4 \| 8 | 16 \| 4 \| 12 |

### Secondary

Mobile / Desktop 동일 — Primary Mobile web/App 패딩과 동일하게 적용

| Content | Padding |
|---|---|
| Icon | 8 \| 4 \| 4 \| 8, height 32px |
| Image | 4 \| 4 \| 4 \| 8 |
| Only text | 12 \| 4 \| 8 |

### Group Spacing

- Chip 간 간격: **8px** (Mobile / Desktop 동일)

---

## UX Usecase

### 1. 드롭다운이 여러 개일 때 → Highlight selection ON 권장
- 여러 Dropdown Chip이 그룹으로 나열된 상황에서 옵션 선택 후 해당 chip의 Highlight selection을 ON으로 전환
- 어떤 필터가 활성화됐는지 시각적으로 구분해줌

### 2. 단일 드롭다운일 때 → Highlight selection ON/OFF 둘 다 가능
- 드롭다운이 하나만 있는 경우, 선택 후 Highlight selection ON으로 강조할 수도 있고
- 기본값이 항상 명확한 맥락에서는 OFF 상태 그대로 유지해도 됨

---

## Audit Checklist

```
🔴 Critical
- Non-FDS Dropdown Chip component detected

🟡 Warning
- Focus state applied on iOS/Android (Focus is for web only)
- Primary Desktop chip height not 36px (should differ from Mobile 32px)
- Primary Mobile/App chip height not 32px
- Padding values not matching platform spec
  → Primary Mobile: Icon(8|4|4|8), Image(4|4|4|8), Only text(12|4|8)
  → Primary Desktop: Icon(12|4|4|12), Image(4|4|4|12), Only text(16|4|12)
  → Secondary: same as Primary Mobile regardless of platform
- Highlight selection always OFF in a group of multiple chips
  → When multiple chips are grouped, turn ON after selection to indicate active filter
- 8px radius used without surrounding angular UI context
  → Use 8px radius only when nearby UI elements (buttons, containers) use angular styling

🟢 Tip
- Group으로 사용할 때 chip 간 간격은 8px 권장
- Secondary는 배경이 없으므로 폰트 Strong 고정 — 임의로 폰트 웨이트 변경 불가
- 단일 드롭다운에서는 Highlight selection ON/OFF 중 맥락에 맞게 선택
```
