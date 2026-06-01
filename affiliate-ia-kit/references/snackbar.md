# FDS Snackbar Reference

**Purpose:** A snackbar is a brief, temporary notification that confirms the outcome of an action or process that's just happened.

**Platform:** iOS ✅, Android ✅, Web ✅

---

## Component Properties

| Property | Values |
|---|---|
| **Type** | `Success`, `Warning`, `Error` |
| **Content** | `Text only`, `Text+Button` |

---

## Type

| Type | Icon | When to use |
|---|---|---|
| `Success` | 파란 체크 아이콘 (고정) | 액션 성공 |
| `Warning` | 노란 느낌표 아이콘 (고정) | 경고 메시지 |
| `Error` | 빨간 느낌표 아이콘 (고정) | 오류 발생 |

> 타입은 3가지만 사용 가능하며, 아이콘 변경 불가.
> 예기치 못한 오류로 아이콘 타입 지정이 어려울 때만 **info 아이콘**으로 기본 표시됨.

---

## Content

- **Text only:** 메시지 + X(닫기) 버튼
- **Text+Button:** 메시지 + Text Button + X(닫기) 버튼
- Close 버튼: `Icon button/Quaternary/Medium`

---

## Content Overflow

- 텍스트는 **2줄 이내** 권장
- 다국어 변환 시 2줄 이상 허용 — 단, 과도하게 길어질 경우 간결하게 수정 권장

---

## Spec

**Padding**

| 위치 | 값 |
|---|---|
| 상하 | 14px |
| 좌 | 12px |
| 아이콘 → 텍스트 gap | 8px |
| 텍스트 → X버튼 gap | 12px |
| X버튼 우측 | 8px |
| Text+Button 버튼 좌우 | 12px |

**Shadow**

| Layer | Color | Opacity | Offset (x, y, blur, spread) |
|---|---|---|---|
| Shadow 1 | #000000 | 20% | 0, 5, 17, 0 |
| Shadow 2 | #000000 | 15% | 0, 2, 7, 0 |

---

## Touch Area

- **Touch area = Container size** (스낵바 전체 영역)
- 버튼 영역만이 아니라 스낵바 컨테이너 전체가 터치 가능

---

## Placement

위치는 플랫폼별 고정 — 항상 화면 하단에 표시됨

| Platform | 좌우 margin | 하단 margin | Width |
|---|---|---|---|
| App | 16px | 64px | 화면 너비 - 32px |
| Mobile Web | 16px | 64px | 화면 너비 - 32px |
| Desktop | 중앙 정렬 | 48px | Min 343px / Max 448px |

**AOS — Bottom Navigation Bar가 있는 경우:**
- 하단 네비게이션 바 위 **8px**에 위치 (화면 바닥 기준이 아님)

> 모달이 열린 상태에서도 스낵바는 항상 기본 위치에 표시됨

---

## Animation (자동 사라짐)

| Platform | 표시 시간 |
|---|---|
| Android | 4초 |
| iOS / Web | 2초 |

> 플랫폼별 시간이 현재 미세하게 다르며, 추후 통일 예정

---

## Edge Cases

### Case 1: 화면 전환 후 노출
- 스낵바는 화면 전환이 **완전히 완료된 후**에 표시됨

### Case 2: Consecutive snackbars
| Platform | 최대 노출 수 | 동작 방식 |
|---|---|---|
| App | 1개 | 이전 스낵바 사라진 후 다음 스낵바 순차 노출 |
| Desktop / Mobile Web | 3개 | 가장 먼저 표시된 스낵바가 가장 아래, 이후 스낵바는 위로 쌓임 |

- 연속 스낵바 간 간격: **12px**
- 스낵바의 Text Button 클릭 후 새 페이지로 이동하면 해당 스낵바 자동 사라짐

### Case 3: 아이콘 타입 불명확 시
- 예기치 못한 오류로 아이콘 타입 지정이 어려울 때 → **info 아이콘**으로 기본 표시

---

## Audit Checklist

```
🔴 Critical
- Non-FDS Snackbar component detected
- Success / Warning / Error 외 다른 타입 사용
  → Snackbar는 3가지 타입만 지원
- 아이콘 임의 변경
  → 아이콘은 타입에 따라 고정 — 변경 불가
- Touch area가 스낵바 전체가 아닌 버튼 영역만 적용
  → Touch area = 스낵바 컨테이너 전체

🟡 Warning
- Placement가 플랫폼 스펙과 다름
  → App/Mobile Web: 하단 64px, 좌우 16px
  → AOS bottom nav bar 있을 시: 네비게이션 바 위 8px
  → Desktop: 하단 48px, 중앙 정렬, min 343px / max 448px
- App에서 스낵바 2개 이상 동시 노출
  → App은 최대 1개만 노출, 순차 표시
- Desktop/Mobile Web에서 스낵바 4개 이상 동시 노출
  → 최대 3개까지만 노출
- 화면 전환 중 스낵바 노출
  → 화면 전환 완료 후 표시

🟢 Tip
- 텍스트는 2줄 이내로 유지 — 다국어 시 2줄 초과 허용하나 간결하게 수정 권장
- 아이콘 타입 불명확 시 info 아이콘으로 fallback 처리
```
