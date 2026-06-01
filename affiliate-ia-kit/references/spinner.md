# FDS Spinner Reference

**Purpose:** A spinner is a loading animation used to indicate that content or an action is in progress.

**Platform:** iOS ✅, Android ✅, Web ✅

---

## Color

| Color | When to use |
|---|---|
| `White` | 어두운 배경 위 |
| `Gray` | 밝은 배경 위 |

---

## Size

- 크기 자유롭게 조정 가능 (fixed size 없음)

---

## Animation

- **Lottie (.json)** 파일로 구현
- 파일 다운로드: [Loading animation .json](https://www.notion.so/prextech/Loading-animation-json-10eeb32ad227809284c4cbda4f989af6?pvs=4)

---

## Audit Checklist

```
🔴 Critical
- Non-FDS Spinner 사용 (직접 구현한 로딩 애니메이션)
  → FDS Spinner Lottie 파일 사용 필요

🟡 Warning
- White spinner를 밝은 배경 위에 사용
  → 밝은 배경에는 Gray spinner 사용
- Gray spinner를 어두운 배경 위에 사용
  → 어두운 배경에는 White spinner 사용
```
