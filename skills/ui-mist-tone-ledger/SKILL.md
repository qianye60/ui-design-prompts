---
name: ui-mist-tone-ledger
description: "Design system for the 'Mist Tone' UI style — A pale-grey order book: one blue pencil, one black stamp. Use when building or restyling web pages, landing pages or UI components in this style, or when the user mentions: Minimal, Calm UI, Tonal Depth, Ops Dashboard, Blue Accent, Wholesale."
---

# Mist Tone

This skill contains a complete, production-grade UI style specification from UI Atlas
(https://ui.ddct.top/p/mist-tone-ledger).

## How to use

1. Read the full specification below before writing any UI code.
2. Implement the design tokens in section 2 exactly — they are the single source of truth.
3. Apply the style to the user's own product, content and framework; never reuse the demo copy verbatim.
4. A reference implementation is bundled in `assets/demo.html`; open it to check proportions and motion.

---

# Mist Tone — Wholesale Operations Dashboard

You are a senior product designer and front-end engineer with an obsessive eye for typography, spacing and restraint. Build an authenticated operations dashboard for a fictional wholesale bakery platform called "Larkrise Bakehouse" in the **Mist Tone** style described below. Treat every value in this brief as a spec, not a suggestion.

## 1. Design Intent

Calm, utilitarian, quietly friendly. Picture a well-kept order book printed on pale grey paper, with one blue pencil for the data and one black stamp for the single action that matters. It is for shop owners and dispatchers who open it daily and want answers in two seconds. The first viewport must feel spacious, soft and trustworthy: a narrow centred column floating in wide empty gutters, with no decoration at all.

Signature details (must be present):
- **Tone-only depth.** Flat `--surface` cards on a white page beside a faintly tinted sidebar. No borders on cards and no shadows anywhere in the base layout.
- **Big number + muted unit.** A 26–28px semibold figure followed by a 14px grey currency or unit code on the same baseline.
- **Split-label filter pills.** One grey capsule holding a muted label, a 1px vertical hairline, then the dark value and a chevron.
- **Single black action.** Exactly one black control per context. All other emphasis is blue or grey.
- **Sparse blue bars.** Chunky solid-blue bars on a gridline-only chart, anchored left when data is thin, with three horizontal lines and a four-label time axis.
- **Tinted notice strip.** A pale-blue rounded bar with a small solid blue pill action.

## 2. Design Tokens

```css
:root {
  /* color */
  --bg: #FFFFFF;
  --sidebar-bg: #F7F8FA;
  --surface: #F5F6F8;
  --surface-2: #EBEDF1;
  --surface-hover: #EFF1F4;
  --surface-press: #E6E9ED;
  --border: #E6E8EC;
  --grid-line: #DDE1E6;
  --text: #1B1D21;
  --text-muted: #646A75;
  --text-faint: #8A8F98;            /* icons and decoration only, never text */
  --accent: #3B7BF4;
  --accent-hover: #5B94F7;
  --accent-deep: #2F66E0;
  --accent-ink: #2557C8;            /* text on tint */
  --accent-tint: #E7EFFD;
  --accent-contrast: #FFFFFF;
  --banner-bg: #2F6BEB;
  --ink-button: #17181A;
  --ink-button-hover: #2B2D31;
  --success-ink: #11793A;
  --success-tint: #E6F6EC;
  /* type */
  --font-display: "Inter", system-ui, -apple-system, "Segoe UI", sans-serif;
  --font-body: "Inter", system-ui, -apple-system, "Segoe UI", sans-serif;
  --font-mono: "JetBrains Mono", ui-monospace, monospace;
  --fs-title: 22px;
  --fs-metric-xl: 28px;
  --fs-metric: 26px;
  --fs-unit: 14px;
  --fs-section: 14px;
  --fs-body: 13px;
  --fs-caption: 12px;
  --fs-tick: 10px;
  /* space (base 4px) */
  --space-1: 4px; --space-2: 8px; --space-3: 12px; --space-4: 16px; --space-5: 20px;
  --space-6: 24px; --space-8: 32px; --space-10: 40px; --space-14: 56px; --space-20: 80px;
  --sidebar-w: 220px;
  --rail-w: 56px;
  --content-max: 792px;
  --control-h: 30px;
  /* shape */
  --radius-xs: 2px;
  --radius-sm: 8px;
  --radius-md: 10px;
  --radius-lg: 16px;
  --radius-pill: 999px;
  /* elevation (popovers only) */
  --shadow-none: none;
  --shadow-pop: 0 8px 24px -8px rgb(20 24 31 / .16), 0 0 0 1px rgb(20 24 31 / .06);
  --ring: 0 0 0 2px var(--bg), 0 0 0 4px var(--accent);
  /* motion */
  --ease-out: cubic-bezier(0.22, 1, 0.36, 1);
  --ease-spring: cubic-bezier(0.34, 1.4, 0.64, 1);
  --dur-fast: 120ms; --dur-base: 200ms; --dur-slow: 600ms;
}
```

## 3. Typography

- Load Google Fonts `Inter` (400, 500, 600, 700) and `JetBrains Mono` (400). Apply `font-variant-numeric: tabular-nums lining-nums` to every number.
- Scale:

| Role | Size | LH | Tracking | Weight | Notes |
| --- | --- | --- | --- | --- | --- |
| Page title | var(--fs-title) | 1.3 | -0.01em | 700 | |
| Metric XL | var(--fs-metric-xl) | 1.1 | -0.015em | 600 | summary cards |
| Metric | var(--fs-metric) | 1.1 | -0.015em | 600 | KPI cards |
| Unit | var(--fs-unit) | 1 | 0 | 400 | `--text-muted`, 6px left gap, baseline-aligned |
| Section label | var(--fs-section) | 1.4 | 0 | 500 | |
| Card label / body / nav | var(--fs-body) | 1.5 | 0 | 400 | nav selected 500 |
| Caption | var(--fs-caption) | 1.5 | 0 | 400 | `--text-muted` |
| Axis tick | var(--fs-tick) | 1 | 0 | 400 | `--text-muted` |

- Rules: no uppercase eyebrows and no wide tracking. Hierarchy comes only from size, weight and grey value. Use `text-wrap: balance` on the title. Never go below 10px, and only for ticks.

## 4. Color & Material

- Ratio: 88% neutrals (white, greys) / 7% ink (text and the black button) / 5% blue.
- Backgrounds: page is flat `--bg`. No gradients, glow or noise anywhere.
- Surfaces: cards, pills and the toggle track use `--surface` with no border and no shadow. A white thumb sits inside the grey toggle. The sidebar is `--sidebar-bg`, separated from the page by tone only. The only 1px lines are the section divider (`--border`) and chart gridlines (`--grid-line`).
- Accent rules: blue is allowed for chart bars, the active nav icon, the notice tint and its pill, links and focus rings. Blue is forbidden as a card fill, as large backgrounds (except the banner), and on more than one chart series colour in the base state. The black button is the only filled dark control. Green appears only as one micro-tag.

## 5. Layout & Grid

- Shell: fixed left sidebar `--sidebar-w`. The main area is white and scrolls with a thin rounded mid-grey scrollbar.
- Content column: `max-width: var(--content-max)`, centred in the space right of the sidebar, leaving wide empty gutters (about 280px each side at 1600px). Padding-top 28px below the banner.
- Grid: 12px gap everywhere. Summary pair is 2 equal columns, KPI row is 3 equal columns, chart is full width.
- Vertical rhythm: title→subtitle 8px; subtitle→notice 16px; notice→summary 12px; summary→divider 36px; divider→filters 32px; filters→KPIs 20px; KPIs→chart 20px; chart→next section label 24px; section label→cards 12px.
- Alignment: everything is left-aligned except the announcement text, which is centred. Card padding is 16px.

## 6. Page Blueprint

### 6.1 Announcement bar
Full width, 35px tall, `--banner-bg`, white 13px centred text with an underlined inline link. Copy direction: "New: rye starter batch tracking is in beta. See what's new". A 16px close icon sits at the right edge with a 28px hit area. Dismiss collapses the height over `--dur-base`.

### 6.2 Sidebar
- Logo block: invented lowercase wordmark "larkrise" in 20px/600 with a tiny black 9px chip reading "ops". It is 40px tall with 24px left padding.
- Primary nav, 4 items: Overview (selected), Orders, Customers, Invoices. Rows are 36px tall with padding 8px 12px, a 1px gap, and a 10px outer margin. Icons are 16px filled rounded glyphs, gap 10px.
- The selected row has `--surface-2` fill, `--radius-md`, a blue icon and weight 500.
- Flexible spacer, then 4 utility items, all grey: Recipes, Support, Price list, Staff chat.
- User chip at the bottom: 28px circular avatar (CSS gradient with initials "MO") plus the name "Marta Oyelaran", 13px.

### 6.3 Page header and notice
- Title "Weekly overview" (22px/700). Under it, a 12px muted caption: "All times shown in local time. Figures may lag by 5 minutes." with a 12px outlined help icon that has a tooltip.
- Notice bar: full column width, about 50px tall, `--accent-tint`, `--radius-lg`, 12px `--accent-ink` text on the left. Copy: "Flour supplier switches to Thursday drop-offs from 14 Nov." On the right is a 30px blue pill "Okay" with 16px side padding.

### 6.4 Summary pair
Each card is 88px tall, `--surface`, `--radius-lg`.
- Left, "Next delivery run": 13px label with a help icon and an 11px pill micro-tag "On schedule" (`--success-tint` bg, `--success-ink` text). The value is "06:30" at 28px with the unit "Tue". A black 30px button "Reschedule" (`--radius-sm`) is vertically centred at the right.
- Right, "Open invoices": a label and the value "£1,284.60" with the muted unit "GBP". No action.

### 6.5 Divider and filter toolbar
A 1px `--border` hairline spans the column. Below it, two split-label pills with 12px gap:
- "Period | Last 30 days ⌄"
- "Customer | All ⌄"

At the far right sit a black pill "Export" (30px tall, 16px padding) and a 16px kebab icon button. This is the only black element in the toolbar.

### 6.6 KPI trio
Three cards of about 86px each: "Revenue" £4,218.40 GBP; "Orders" 312; "Loaves baked" 5,906. Label 13px, value 26px, unit only where relevant.

### 6.7 Chart card (about 287px tall)
- Header: 13px title "Revenue by bake day" plus a muted total "£4,218.40". At the right is a segmented toggle with a `--surface-2` track and a white pill thumb, about 26px tall and 11px labels: "Product | Customer".
- Plot: three horizontal 1px `--grid-line` lines labelled 2,000 / 1,000 / 0 at the left. No vertical lines or axis strokes. The x-axis has four labels: 9/10, 9/20, 9/29, 10/9.
- Bars: solid `--accent`, 18px wide, 6px gap, top radius `--radius-xs`. Anchored left with sample heights proportional to 240, 1,700, 1,860 and 1,060 on the 2,000 scale. The rest of the axis stays empty.

### 6.8 Per-product sections
Below the chart, repeat this pattern per product. A 14px/500 label comes first, for example "Seeded rye loaf", then a card pair "Orders 118" and "Loaves baked 2,240". Add a second group, "Cardamom morning bun", with "Orders 94" and "Units baked 1,880". Cards match 6.4, with no actions.

## 7. Components

| Component | Spec | States |
| --- | --- | --- |
| Black button | height 30px, bg var(--ink-button), white 13px/500 text, padding 0 16px, radius sm (small) or pill (export) | hover: var(--ink-button-hover); active: scale(.98); focus-visible: var(--ring); disabled: 40% opacity |
| Blue pill | height 30px, bg var(--accent), white text, radius pill, padding 0 16px | hover: var(--accent-deep); active: scale(.98); loading: spinner replaces label |
| Filter pill | height 30px, bg var(--surface), radius pill, padding 0 14px; label muted, 14px hairline, value dark, 12px chevron at 1.5px stroke | hover: var(--surface-hover); open: chevron rotates 180° and a popover with var(--shadow-pop) appears |
| Nav item | 36px, radius md, 16px icon | hover: var(--surface-hover); active: var(--surface-press); selected: var(--surface-2), blue icon |
| Summary and KPI card | var(--surface), radius lg, padding 16px, no border, no shadow | static |
| Micro-tag | 11px/500, padding 2px 8px, radius pill | static |
| Segmented toggle | track var(--surface-2), thumb white, radius pill | hover: inactive label to var(--text); focus-visible: ring |
| Bar | solid var(--accent) | hover: var(--accent-hover) plus a tooltip after 80ms (white card, var(--shadow-pop), 12px) |
| Icon button | 28px hit area minimum, 16px icon in var(--text-faint) | hover: bg var(--surface-hover), radius sm |

## 8. Motion & Interaction

- Tokens: use `--ease-out` for everything and `--ease-spring` only for the toggle thumb. Colour transitions take `--dur-fast`.
- Load: cards fade and rise (opacity 0→1, translateY 8px→0) over 320ms, staggered 60ms in DOM order. Never apply `clip-path` to observed elements.
- Bars: `scaleY(0→1)` from `transform-origin: bottom` over `--dur-slow`, staggered 40ms per bar.
- Toggle thumb slides over `--dur-base`. The chevron rotates over `--dur-base`. The popover enters with opacity and translateY(-4px) over 160ms.
- Banner dismiss collapses height and opacity over `--dur-base`.
- Ambient motion: none. This surface stays static and calm.
- Reduced motion: under `prefers-reduced-motion: reduce`, remove all transforms and staggers, keep instant colour changes and render bars at full height.

## 9. Responsive Behavior

- Breakpoints: 1024px and 640px.
- At or below 1024px, the sidebar collapses to a `--rail-w` icon rail with tooltips, and the column fills the remaining width with 24px side padding.
- At or below 640px:
  - The sidebar becomes a left drawer (280px) behind a 44px hamburger in a sticky top bar, with a scrim at `rgb(20 24 31 / .4)`.
  - Summary cards stack to 1 column, and KPI cards become a horizontal scroll-snap strip with 160px-minimum cards.
  - The chart keeps full width and shows 3 x-axis labels.
  - Filter pills wrap, and Export collapses to an icon-only black circle.
- Under `(pointer: coarse)`, raise all controls to 44px tall.

## 10. Accessibility

- Contrast: body text ≥ 4.5:1 on its surface. Use `--text-muted` for all small grey text. `--text-faint` is for icons only. Notice text uses `--accent-ink`, the micro-tag uses `--success-ink`, and the banner uses `--banner-bg` (white on it is ≥ 4.5:1).
- Landmarks: banner `role="region"`, `aside > nav`, `main`, and `section[aria-labelledby]` per block.
- Visible `--ring` on every interactive element. The toggle is a `role="tablist"` with arrow-key support. The filter popover is a listbox with Esc to close and focus return.
- The chart has a `<title>` and `<desc>` plus a visually hidden data table. Bars are focusable and expose their values to screen readers. Icons are `aria-hidden` and icon buttons carry `aria-label`.

## 11. Do / Don't

Do:
- Define depth by one tonal step only: white page, `--surface` card, white thumb.
- Keep exactly one black control per context.
- Pair every large figure with a muted 14px unit on the same baseline.
- Keep the content column at 792px with empty gutters. Do not fill them.
- Draw only three gridlines and four x-labels on the chart.
- Use 16px radius for cards and the notice, and full pills for toggles and filters.
- Use tabular numerals for all figures.

Don't:
- Add card shadows, borders, gradients or glassmorphism.
- Introduce a second accent colour or colour-code bars by category in the base state.
- Use uppercase eyebrows, tracking-wide labels or decorative illustrations.
- Make the chart dense with vertical gridlines, axis strokes or legends.
- Use more than one black button per toolbar or card.
- Stretch the column to full width on desktop.
- Put `--text-faint` on text.

## 12. Output Requirements

- Deliver a single self-contained `index.html` with one `<style>` and one `<script>` (vanilla JS for the banner dismiss, toggle, filter popovers, drawer and tooltips).
- Use realistic, specific copy for "Larkrise Bakehouse" as given. No lorem ipsum and no real brand names.
- No external images. Compose the avatar, icons and chart with CSS and inline SVG.
- Before finishing, self-check:
  - tokens used everywhere, with no stray hex values;
  - all hover, active, focus and disabled states implemented;
  - layout verified at 390px / 768px / 1440px;
  - reduced motion respected.
