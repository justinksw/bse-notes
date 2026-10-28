# BSE Notes hub — Design brief v1

**Designer:** Celine · **Builder:** Jessie (after Justin OK) · **Substance:** Beatrice · **Coordinator:** Sua  
**Direction locks:** A1 / B1 / C1 / D1 / E1 (Justin 2026-10-28 via Sua)  
**Site title:** **Provisional — BSE Notes** / ZH **BSE 學習筆記** (Sua confirming final name with Justin; treat as swap-ready in build)  
**Status:** Justin **visual OK** 2026-10-28 (via Sua). Chrome LOCKED (Beatrice web-v2 + title A). **Jessie: build hub preview** now. Live only after Justin live OK. Site title provisional **BSE Notes**. Note page = later (await Beatrice substance-v2).

Mockup: `mockup/hub-v1.html` · Logo: `logos/bse-notes.svg` · Shots: `mockup/shots/` · Design note: `mockup/DESIGN-NOTE-hub-v1.md`

---

## 1. Goal

GitHub Pages **notes index** for Justin’s BSE learning notes. One hub lists every note (clear title + creation date) and opens the note page. v1 ship:

1. Hub home with **A1** stacked cards, **B1** creation-date newest-first, **C1** `YYYY-MM-DD` under title.  
2. One **D1 Coming soon** card using a bans-safe **provisional public** title until Beatrice / publish URL exists — then CTA becomes **Open · 開啟** and links to the note.  
3. Note page body / shell (**E1**) = **later brief** after Beatrice web substance — not in this build.

## 2. Locked decisions

| Item | Value |
|---|---|
| Layout | **A1** full-width stacked cards in phone frame |
| Sort | **B1** creation date descending (newest first) |
| Date display | **C1** absolute `YYYY-MM-DD` (Asia/Hong_Kong) under title |
| Empty / first note | **D1** Coming soon → Open when published |
| Note shell | **E1** deferred — hub only this brief |
| Title | **Provisional:** **BSE Notes** / **BSE 學習筆記** |
| Visual system | Kinship with BSE Tools / psychart — see §5 |

### Date source (for Jessie)

Creation date on each card comes from **publish metadata** Jessie will wire later (e.g. `notes/manifest.json` `created` field, or frontmatter). Until a note is published, show `—` or omit the date line. Do **not** invent dates. Sort key = that metadata string, ISO `YYYY-MM-DD`, desc.

## 3. Screen structure (iPhone 13 = 390×844)

Mirror BSE Tools / psychart app shell:

1. **`header.appbar`** — hub mark 32px · h1 **17px/700** · sub **12px** muted (ZH provisional) · **MOCKUP** / **PREVIEW** badge on non-live builds  
2. **Intro** — 12px muted, one line: study notes index (bilingual OK); no site names  
3. **`.sheet`** — white panel, radius 16px top, grab + section label **Notes / 筆記**  
4. **Cards** — `#FAFBFC`, radius **12**, border `--line`; soon cards `#F3F5F8`  
5. **`.demo-note`** — 11px honesty: learning notes · not a Code checker · not official guidance — **no project / hospital / Block names**

### Card anatomy

| Element | Spec |
|---|---|
| Optional mark | 40×40 icon or note mark (ink + accent) |
| Title EN | **15px / 700** — clear, bans-safe public title |
| Title ZH | **12px** muted; `overflow-wrap` / `word-break: keep-all` |
| Creation date | **12px** muted, `YYYY-MM-DD` under title; `—` until published |
| Purpose (optional) | 12px / 11px ZH muted — generic teaching only |
| CTA live | min **44×44**, radius **10**, font **13/600**, ink fill — **Open · 開啟** |
| CTA soon | panel + muted border — **Coming soon · 即將推出**; **not** an `<a>`; no navigation |
| Soon card | `<div class="card soon">` — not a link |

### Card copy (v1) — Justin locked title A (2026-10-28)

Beatrice option A. Old「醫院手術室…」**retired**. Body OT／手術室 examples = Beatrice revise → note layout; not on hub.

| Field | Value |
|---|---|
| Title | **OM-Knowledge｜屋宇裝備 O&M 原則** |
| EN subtitle (hub card) | Building services O&M principles |
| Slug | `om-knowledge` |
| Date | `2026-10-28` |
| Blurb | MVAC 空氣／水側、CAV／VAV 同壓差、消防 pre-action、電力分層、醫用氣體同 CCMS 嘅 O&M 原則同巡查思維——唔寫項目死數、唔標項目類型。 |
| CTA | Coming soon · 即將推出（until note URL → Open · 開啟） |

**Hub / H1 / blurb chrome bans (extra):** `醫院手術室`、`手術室`、`OT`、`Prep`、`醫院`、`hospital`. Body OT teaching examples = Justin via Sua — not on hub card.


## 4. Logo (`logos/bse-notes.svg`)

Notebook / stacked-lines mark: ink `#1E2A50` fill tile, canvas stroke, accent `#C45C26` spine. 64 viewBox; readable at 32–40px. Same family as `bse-tools.svg` (rounded square tile).

## 5. Visual tokens (match tools / psychart — do not diverge)

```
--canvas: #EEF1F4
--panel: #FFFFFF
--ink: #1E2A50
--muted: #5A6178
--line: #C8CDD8
--accent: #C45C26
--focus: #174A7C
body background: #D8DCE2
font stack: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Noto Sans TC", "PingFang TC", "Helvetica Neue", sans-serif
```

Type: appbar h1 **17**; sub/ZH **12**; section EN **13/700**; card EN **15/700**; date/purpose **12**; demo-note **11**; CTA **13/600**.

## 6. Behaviour / repo

- Hub lives in `justinksw/bse-notes` GitHub Pages.  
- Coming soon → no nav. Open → note path from manifest.  
- Sort creation date desc; date from publish metadata.  
- Preview branch + **PREVIEW** / **MOCKUP** badge until Justin live OK.  
- Report to **Sua**; Celine one punch-list on preview.  
- Site title swap when Justin/Sua lock final name (CSS/copy only — no layout redo).

## 7. Hard ban — public Pages (Justin 2026-10-28)

**Must not appear** in hub HTML, meta title/description/og, footer, card copy, visible filenames used as public chrome, or alt text that ships:

- Hospital / institution names  
- Block / floor / room / plant IDs  
- Site / project names  
- Paths or labels that identify a real workplace  

### Explicit strings banned in v1 acceptance (`rg`)

At minimum (case-insensitive where noted):

| String | Notes |
|---|---|
| `QEH` | institution shorthand |
| `Queen Elizabeth` | institution name |
| `Block T` | site Block |
| `BlockT` | compacted form |
| `8/F` / `八樓` | as project floor labels |
| `白內障` / `Cataract` | specialty-centre plaque |
| `BSI-NOTES` | cross-note plaque |
| Equipment tags e.g. `AHU-8-04` | site tags |
| Client / consultant proper names | e.g. Egis |
| `醫院手術室` / hospital-OT framing on **hub card** | Justin 2026-10-28 — hub index must not read as hospital OT project; note body follows Beatrice revised meta separately |

**Hub card:** Justin locked + **visual OK**. Jessie builds from this brief + `mockup/hub-v1.html`.

Beatrice may **extend** bans in the note brief — Jessie re-runs `rg` before share.

Suggested check:

```bash
rg -n -i 'QEH|Queen Elizabeth|Block T|BlockT|8/F|八樓|白內障|Cataract|BSI-NOTES|Egis|AHU-8-04' \
  mockup/hub-v1.html logos/ index.html styles.css notes/ 2>/dev/null
```

Expect **no hits** on banned strings (OM-Knowledge in the locked title is OK).

## 8. Out of scope

- Note page body / E1 shell layout (later brief after Beatrice web substance)  
- Pasting or reusing A5 PDF card pagination  
- Inventing BSE facts or official titles Beatrice hasn’t set  
- Redesigning `bse-tools` / psychart  
- Paid tools · CoP / official-guidance claims  
- Live merge without Justin OK  

## 9. Acceptance list (measurable)

1. **Primary review viewport:** iPhone 13 CSS **390×844** (WebKit); also **320** and **430** — no horizontal scroll; ZH wraps with `overflow-wrap` / keep-all.  
2. Desktop Chrome at 390-wide (or device mode) matches the phone mock.  
3. Tokens/type match §5 (side-by-side with BSE Tools hub — same brand family).  
4. Title shows provisional **BSE Notes** + ZH sub **BSE 學習筆記** (or Justin-final name if swapped before build).  
5. Section label **Notes / 筆記**.  
6. One card: locked title **OM-Knowledge｜屋宇裝備 O&M 原則** + EN subtitle **Building services O&M principles**; date **2026-10-28**; blurb as §3 (no 醫院／手術室／OT／Prep／hospital); CTA **Coming soon · 即將推出** is **not** an `<a>` and does not navigate.  
7. CTA / tap targets ≥ **44px**; focus ring `--focus` on interactive Open CTAs.  
8. Hub mark SVG renders at 32px appbar (and optional 40px card).  
9. Footer / demo-note honesty present; **no** project / hospital / Block names.  
10. Safe-area bottom padding on sheet (`env(safe-area-inset-bottom)`).  
11. **MOCKUP** or **PREVIEW** badge only on non-live builds; removed or replaced for live after Justin OK.  
12. Banned-string `rg` (§7) returns **no hits** in public-facing hub files.  
13. Contrast AA+ for ink/muted on canvas/panel (psychart-aligned tokens).  
14. Sort behaviour documented: creation date desc; ready for manifest wiring (empty/soon state OK until first publish).

## 10. Ask Justin (via Sua)

OK hub **v1** mockup + this brief for Jessie preview build?  
Optional: confirm final site title (keep provisional vs swap). Tweaks → one punch list before/after preview.
