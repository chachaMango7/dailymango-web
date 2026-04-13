# Design System — Dailymango Web

**Repo**: `dailymango-web`
**Domain**: https://dailymango.rollingmango.co.kr
**Last updated**: 2026-04-13

---

## Product Context

- **What this is**: Service brand web presence for **Dailymango**, a mobile app studio under **Rollingmango** (parent company). Hosts the landing page, per-app pages, legal docs, and support.
- **Who it's for**: Prospective app users in Korea (primary) and English-speaking markets (secondary). Also serves as the source for store listing URLs.
- **Space**: Wellness / lifestyle mobile apps. First product is **마음의 쉼표 · Paperday** (daily quotes + aurora backgrounds).
- **Project type**: Marketing site (static, no framework, GitHub Pages hosted).

---

## Aesthetic Direction

**Direction**: **Editorial × Playful Warmth**
Think small-studio print matter, not SaaS template. Kinfolk magazine meets a neighborhood mango juice brand. Generous whitespace, serif display type, asymmetric layouts, warm cream paper background, and mango yellow as a deliberate accent (not a flood).

**Decoration level**: **Intentional** — subtle paper texture (optional), editorial rule lines, issue numbers and metadata in sidebars. No decorative blobs, no gradients-on-everything, no icon-in-circle grids.

**Mood**: Quietly confident, hand-touched, unhurried, romantic. A 20-something woman picks up a beautifully printed zine at a small cafe in Hapjeong. Soft. Warm. Worth saving to her Instagram.

**Target emotional response**: The visitor (primary: Korean women 20–35) should feel "이거 나 쓰고 싶다" within 3 seconds — and want to share the page itself, not just the app.

**Reference feel**:
- Kinfolk, Cereal magazine (layout density, serif treatment)
- Frank Chimero's personal site (hand-touched editorial warmth)
- Tonal design in independent bookstores (typography first, color supporting)

---

## Brand Foundation (from Rollingmango CI)

- **Parent brand**: Rollingmango (손글씨 워드마크 + 파도치는 M 심볼)
- **Service brand**: Dailymango (이 웹사이트의 주인)
- **First app under Dailymango**: 마음의 쉼표 · Paperday

**CI assets already defined**:
- Mango Yellow `#FFD852`
- Mango Green `#4B9141`
- Apple Mango `#FF9838`
- Wavy M symbol (recreated as inline SVG until logo files are provided)
- Rollingmango wordmark (handwriting-style, not yet provided as file — wait for export)

---

## Typography

**Display / Hero (Korean)**: `Noto Serif KR` at weight 500–600
- Rationale: Editorial serif for Korean. Warm, readable at large sizes. Pairs with Fraunces for bilingual headlines.
- Loading: Google Fonts `<link>`

**Display / Hero (English)**: `Fraunces` variable
- Rationale: Warm, characterful serif with personality. Variable axes allow display weight adjustments. Much more distinctive than Playfair or Lora.
- Loading: Google Fonts variable

**Body / UI**: `Pretendard Variable`
- Rationale: Best-in-class Korean sans-serif. Modern, clean, reads well at small sizes. Variable font, self-hostable via jsDelivr CDN.
- Loading: `<link href="https://cdn.jsdelivr.net/gh/orioncactus/pretendard@v1.3.9/dist/web/variable/pretendardvariable.min.css" rel="stylesheet">`

**Data / Code**: Not used. This is a marketing site, not a dashboard.

**Type Scale** (base = 16px):

| Token | Size | Line-height | Usage |
|---|---|---|---|
| `display-xl` | 72px / 4.5rem | 1.1 | Hero headline (desktop) |
| `display-lg` | 56px / 3.5rem | 1.12 | Hero (tablet) |
| `display-md` | 40px / 2.5rem | 1.15 | Section heading |
| `display-sm` | 32px / 2rem | 1.2 | Sub-section heading |
| `title-lg` | 24px / 1.5rem | 1.3 | Card title |
| `title-md` | 20px / 1.25rem | 1.35 | Minor heading |
| `body-lg` | 18px / 1.125rem | 1.7 | Intro paragraph |
| `body-md` | 16px / 1rem | 1.65 | Default body |
| `body-sm` | 14px / 0.875rem | 1.6 | Meta, footer |
| `caption` | 12px / 0.75rem | 1.5 | Eyebrow, labels |

Display sizes use `clamp()` for fluid scaling on mobile.

**Letter-spacing**:
- Display serif: `-0.02em` (tightened)
- Body sans: `-0.005em` (slight)
- Caps labels: `0.12em` (opened)

---

## Color

**Approach**: **Restrained** — background is paper cream, text is warm ink, mango yellow appears only where it matters (underlines, badges, symbol backgrounds, hover states). Roughly 5–10% of the total visual area is yellow.

| Token | Hex | Usage |
|---|---|---|
| `--paper` | `#FAF7ED` | Primary background (warm cream) |
| `--paper-soft` | `#F5F0DD` | Secondary background, subtle surface tint |
| `--ink` | `#1A1614` | Primary text (warm black, not pure #000) |
| `--ink-dim` | `#554D43` | Secondary text, body meta |
| `--ink-muted` | `#9B8F7E` | Tertiary text, captions, rules |
| `--rule` | `#E8E0C9` | Dividers, hairlines |
| `--mango-yellow` | `#FFD852` | Accent (badges, highlights, symbol) |
| `--mango-yellow-ink` | `#1A1614` | Text on yellow (always ink, never white) |
| `--mango-green` | `#4B9141` | Label accent, success states |
| `--apple-mango` | `#FF9838` | Hover/active, emphasis (rare) |
| `--blush` | `#F8E1DC` | Romantic soft accent surfaces |
| `--blush-deep` | `#EBB8B0` | Pull quotes, decorative elements |
| `--peach` | `#F5C7A9` | Warm accent surfaces |
| `--lavender-mist` | `#E8DFEF` | Tertiary soft accent (rare) |

**Gradients**: Avoid. If needed for app icon backgrounds only: `linear-gradient(135deg, var(--mango-yellow), var(--apple-mango))`.

**Dark mode**: Deferred. Marketing site primarily viewed during daytime. If added later, redesign surfaces (don't just invert).

**Contrast targets**:
- Body text on `--paper`: `--ink` (#1A1614) → 13.8:1 AAA ✓
- Meta on `--paper`: `--ink-dim` → 6.2:1 AA ✓
- Label on `--mango-yellow`: `--ink` → 11.1:1 AAA ✓

---

## Spacing

**Base unit**: 8px. Use rem-based multiples.

**Scale**:
| Token | px | rem | Usage |
|---|---|---|---|
| `space-3xs` | 2px | 0.125rem | Hairline padding |
| `space-2xs` | 4px | 0.25rem | Tight gaps |
| `space-xs` | 8px | 0.5rem | Small gap |
| `space-sm` | 16px | 1rem | Standard gap |
| `space-md` | 24px | 1.5rem | Component padding |
| `space-lg` | 40px | 2.5rem | Section inner spacing |
| `space-xl` | 64px | 4rem | Section vertical rhythm |
| `space-2xl` | 96px | 6rem | Major section breaks |
| `space-3xl` | 128px | 8rem | Hero top padding (desktop) |

**Density**: Comfortable to Spacious. This is editorial, not dashboard. Give text room to breathe.

---

## Layout

**Approach**: **Hybrid — grid-disciplined for the overall column, creative-editorial for within sections.**

**Column widths**:
- Max content width (text-heavy pages): `640px` (legal docs, support)
- Max content width (landing): `960px`
- Gutter: `24px` mobile, `40px` desktop
- Outer padding: `20px` mobile, `32px` desktop

**Grid**: 12-column desktop, but feel free to break to 10/8/6 for sidebar effects.

**Asymmetric patterns to use**:
- Hero headline left-aligned, issue meta ("№ 01", date) on the right sidebar
- Section labels in left margin, content in right 8 columns
- Pull quotes that break out of the content column

**Border radius hierarchy**:
- Sharp edges (`0`): most containers, rules, dividers
- `2px`: buttons, small badges (subtle softening)
- `8px`: input fields, minor cards
- `12px`: app cards, feature blocks (main rounded elements)
- `24px`: app icon tiles (prominent rounded)

---

## Motion

**Approach**: **Minimal-functional.** No scroll animations, no reveal-on-view, no parallax. Only hover/focus transitions and small state changes.

**Tokens**:
- `duration-fast`: `120ms`
- `duration-med`: `200ms`
- `duration-slow`: `320ms`
- `ease-out`: `cubic-bezier(0.16, 1, 0.3, 1)` (defaults)
- `ease-in-out`: `cubic-bezier(0.6, 0, 0.2, 1)` (rare)

**Allowed animations**:
- Hover color changes (med ease-out)
- Button/link underline slide (fast ease-out)
- Card lift on hover (`translateY(-2px)`, med ease-out)
- Focus ring fade (fast)

**Forbidden**:
- Hero text fade-in on page load
- Scroll-triggered reveal
- Auto-playing gradient shifts
- Blur-in effects

---

## Components (conventions)

**Links**:
- Body links: `--ink`, underlined with `--mango-yellow` 2px offset underline. Hover: underline thickens to 3px, color stays.
- Nav links: `--ink-dim` default, `--ink` on hover. No underline.

**Buttons**:
- Primary: Solid `--ink` background, `--paper` text, `2px` radius. Hover: background `--apple-mango`, text stays `--paper`.
- Secondary: Transparent, `1.5px` `--ink` border, `--ink` text. Hover: background `--ink`, text `--paper`.
- No drop shadows on buttons. Flat and confident.

**Cards**:
- Background: `--paper-soft` or `--paper` with `1.5px` `--rule` border
- Radius: `12px`
- Padding: `space-md` to `space-lg`
- Hover: border becomes `--mango-yellow`, no shadow

**Dividers**:
- Horizontal rules: `1px` solid `--rule`, full width or short `40px` decorative rules
- Avoid gradient dividers

---

## Copy & Tone

- **Korean primary, English secondary**. Headlines can be bilingual when the English adds texture (e.g., "마음의 쉼표 · PAPERDAY").
- **No marketing cliches**: Avoid "Built for X", "Empowering Y", "Revolutionary", "Effortless".
- **Concrete over aspirational**: "매일 한 줄의 명언" beats "당신의 일상에 영감을".
- **Lowercase English for metadata**: "issue №01", "spring 2026", "made in seoul".

---

## Anti-Slop Rules

The previous two redesigns failed because they fell into these traps. Do not repeat:

1. **No three-column feature grid with icons in colored circles.** Use asymmetric layouts or 2-column with real content.
2. **No purple/violet gradients.** Our accent is mango yellow.
3. **No centered-everything layouts.** Lean left-aligned editorial.
4. **No "bouncy" rounded sans-serif as display type.** Use serif for display.
5. **No badge-icon-title-description card pattern everywhere.** One featured app card is enough; use prose or other patterns elsewhere.
6. **No stock gradient buttons.** Flat primary button in `--ink`.
7. **No emoji as decoration.** ✨🎨💫 are banned. Use the wavy M symbol or nothing.
8. **No Google Fonts sans defaults** (Inter, Poppins, Roboto). We use Pretendard + Fraunces + Noto Serif KR.

---

## Decisions Log

| Date | Decision | Rationale |
|---|---|---|
| 2026-04-13 | Initial DESIGN.md created | Grounded in Rollingmango CI + editorial direction to escape SaaS template trap |
| 2026-04-13 | Noto Serif KR + Fraunces for display | Editorial feel, bilingual pair, rejects bouncy rounded sans default |
| 2026-04-13 | Paper cream background (#FAF7ED) | Yellow as accent 5-10%, not as flood. Background evokes print |
| 2026-04-13 | Layout = hybrid grid with editorial breaks | Asymmetric to feel like a magazine, not a landing page template |
