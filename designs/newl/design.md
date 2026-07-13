# NEWL — 디자인 토큰 (slide-deck용)

NEWL 연구실 웹사이트/디자인 시스템(`@newl/design-system`)의 슬라이드 덱 버전.
작업 폴더에 이 파일을 `design.md`로 복사해 두면 slide-deck 스킬이 Traction 기본
토큰 대신 이 토큰을 사용한다. 예시 렌더링은 [`screenshots/`](screenshots/) 참고.

## colors

| token | value | 용도 |
|---|---|---|
| primary | `#0A2463` | 네이비 — 제목·잉크·주요 도형 |
| primary-light | `#1E3A8A` | 호버·보조 네이비 |
| accent | `#FFB800` | 골드 — 핵심 강조 (슬라이드당 1~3곳) |
| accent-light | `#FFD166` | 옅은 강조 배경 |
| energy-green | `#06D6A0` | 데이터 시리즈 2 |
| energy-blue | `#118AB2` | 데이터 시리즈 3 |
| bg | `#FFFFFF` | 슬라이드 배경 |
| bg-alt | `#F8F9FC` | 카드·밴드 배경 |
| bg-dark | `#0A2463` | 다크 섹션/표지 배경 (이 디자인에서는 허용) |
| body | `#4A4A6A` | 본문 |
| ink | `#1A1A2E` | 제목·강조 텍스트 |
| border | `#E2E8F0` | 카드 테두리 |
| red | `#D64545` | 금지/✗ 전용 (Traction 규칙 유지) |

- 강조 체계: Traction의 그린 역할을 **골드 `#FFB800`** 가 맡는다. 긍정/핵심 = 골드,
  보조 = 잉크 볼드, 금지 = 레드 전용.
- 다크 표지: 배경 `#0A2463` + 흰 제목 + 골드 핵심어 (`newl-design-system`의 Hero 패턴).
  본문 슬라이드는 밝은 배경 유지.

## fonts

| token | value |
|---|---|
| head/body | `"Pretendard", "Inter", sans-serif` (CDN: jsdelivr pretendard static) |
| mono | `"JetBrains Mono", "Consolas", monospace` — 숫자·ID·변수명 |

## type scale (확대판 — 16px 기본이 아니라 18px 기본)

| step | px | 용도 |
|---|---|---|
| hero | 64 | 표지 제목 |
| 4xl | 44 | 큰 숫자(stat) |
| 3xl | 36 | 섹션 제목 |
| 2xl | 28 | statement(한 줄 메시지) |
| xl | 24 | 카드 제목 |
| lg | 20 | 부제 |
| base | 18 | 본문 |
| sm | 15 | 메타·캡션 |
| xs | 13 | 라벨·태그 |

## icons — Lucide (lucide.dev, ISC)

- **유일한 아이콘 소스는 Lucide.** 이모지·아이콘 폰트·외부 이미지 금지는 그대로.
- 삽입 방식: **인라인 SVG** — `https://unpkg.com/lucide-static/icons/<name>.svg`
  를 가져와 붙여넣는다 (산출물은 단일 HTML 유지).
- 스타일: stroke `1.75`, `stroke="currentColor"`, `fill="none"` (Lucide 기본값 유지).
- 크기: `1em`~`1.4em` (텍스트 옆), 히어로 워터마크는 `3em`+.
- 색: 기본 잉크/라벨색, 핵심만 골드, 금지 표시는 레드.
- 자주 쓰는 이름: `atom` `flask-conical` `microscope` `battery-charging` `zap`
  `sun` `leaf` `book-open` `graduation-cap` `file-text` `users` `award`
  `search` `arrow-right` `external-link` `check` `x` `alert-triangle`

```html
<!-- 예: 칩 안의 Lucide 아이콘 (인라인 SVG, currentColor 상속) -->
<span style="color:#FFB800">
  <svg xmlns="http://www.w3.org/2000/svg" width="1.2em" height="1.2em" viewBox="0 0 24 24"
       fill="none" stroke="currentColor" stroke-width="1.75"
       stroke-linecap="round" stroke-linejoin="round"><!-- lucide path --></svg>
</span>
```

## radius / spacing

- radius: sm `6px` · md `10px` · lg `16px` · full `999px` (칩/배지는 full)
- spacing: 8px 배수

## 컴포넌트 대응 (newl-design-system → 슬라이드)

| 웹 컴포넌트 | 슬라이드에서 |
|---|---|
| Hero | 표지 — 네이비 배경, 골드 라벨 필, 흰 제목 + 골드 `<em>` |
| SectionHeader | 슬라이드 제목 + 골드 밑줄 60×3px |
| Card | 본문 카드 (흰 배경, `#E2E8F0` 테두리, radius 16) |
| Tag | 키워드 칩 (pill, 골드/네이비) |
| ImpactBadge/JcrBadge | 지표 배지 (mono, 작게) |
