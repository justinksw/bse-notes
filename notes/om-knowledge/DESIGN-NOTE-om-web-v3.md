# DESIGN-NOTE — OM-Knowledge web v3.1

**Role:** Celine · Designer  
**Content owner:** Beatrice（substance-v2 + brief-v3 locked）  
**Date:** 2026-10-28（Asia/Hong_Kong）  
**Repo path:** `notes/om-knowledge/`  
**Format:** mobile-first HTML web note（**not** A5 PDF）
**Layout version:** v3.1（v3 + in-text EN abbr popovers；substance unchanged）

## Sources (locked)

| Doc | Path |
|---|---|
| Substance | `/workspace/qeh_study/briefs/OM-KNOWLEDGE-web-substance-v2.md` |
| Brief | `/workspace/qeh_study/briefs/CELINE-BRIEF-OM-knowledge-web-v3.md` |
| Visual kinship | `/workspace/bse-tools/mockup/hub-v2.html` tokens（+ bse-notes hub-v1 kinship） |

**Stop using:** substance-v1／brief-v2 body；PDF-era layouts；Prep→OT cascade labels.

## Public chrome（Proposal A — LOCKED）

| Field | Value |
|---|---|
| `<title>` | `OM-Knowledge｜屋宇裝備 O&M 原則` |
| H1 | `屋宇裝備 O&M 原則` |
| EN sub | `Building services O&M principles` |
| Eyebrow | `OM-Knowledge` |
| Blurb／meta description | MVAC 空氣／水側、CAV／VAV 同壓差、消防 pre-action、電力分層、醫用氣體同 CCMS 嘅 O&M 原則同巡查思維——唔寫項目死數、唔標項目類型。 |
| slug | `om-knowledge` |
| created | `2026-10-28` |

Hub back link：`../../` → repo root. Site name provisional：**BSE Notes**.

## Chapter map（public HTML）

| id | Section |
|---|---|
| `#s0` | 點樣用呢本 · 縮寫卡 · TOC |
| `#s1` | 系統地圖（D0；中央＝受控／潔淨送風空間）→ 六塊 D0a–D0f |
| `#s2` | 空氣側 MVAC（2.1–2.7；D3／D2／D8） |
| `#s3` | 水側（3.1–3.3；D4） |
| `#s4` | 消防（4.1–4.4；D5／D9） |
| `#s5` | 電力（5.1–5.3；D6） |
| `#s6` | 醫用氣體系統（通用）（D7） |
| `#s7` | 監控 CCMS |
| `#s8` | 保養巡查思維（每日／每週／每季） |
| `#s9` | 常見故障聯想 |
| `#closing` | 短文末（獲批圖／O&M only — **not** honesty page） |

Fourth tier label everywhere：**教學對位**（not 常見配置 as the tier title）.

## Tokens

```css
--canvas: #EEF1F4;
--panel: #FFFFFF;
--ink: #1E2A50;
--muted: #5A6178;
--line: #C8CDD8;
--accent: #C45C26;
--focus: #174A7C;
--remember-bg: #FFF4E5;
--align-bg: #F0F5F8;
--warn-bg / --warn-bd: #FFF1F0 / #D94A3D;
```

Type: system stack + Noto／PingFang TC. Body **16px** base. Max content width **430px** centered; review frame ~**390px**. Sticky topbar + jump-to-top. Four-tier cards: 記住呢句／點解／保養／巡查睇咩／教學對位. Warn／Escalate callouts.

## Figures

| ID | File | Relabel notes vs PDF-era source |
|---|---|---|
| D0 | `diagrams/D0.svg` | Center：**受控／潔淨送風空間**（was OT 套間） |
| D0a–D0c, D0e–D0f | `diagrams/D0*.svg` | Copied；no scene bans |
| D0d | `diagrams/D0d.svg` | **應急路徑** kept；load line →「控制／關鍵負荷」（removed 手術燈） |
| D2 | `diagrams/D2.svg` | **高要求房 → 緩衝／前室 → 走廊**（was Prep→OT→Anteroom） |
| D3–D9 | `diagrams/D*.svg` | Copied；captions from substance-v2「圖下一句」 |
| **D1** | — | **Absent by design** |

**Checksum Present:** D0, D0a, D0b, D0c, D0d, D0e, D0f, D2, D3, D4, D5, D6, D7, D8, D9  
**Checksum Absent:** D1

Source SVGs adapted from `/workspace/qeh_study/om-notes/diagrams/`（relabeled；D1 not copied）.

## Hard-ban disinfection（chrome + body + SVG）

Public acceptance command:

```bash
rg -n '手術室|\bOT\b|醫院|hospital|Prep|QEH|Block T|白內障|Cataract|BSI-NOTES' \
  notes/om-knowledge/index.html notes/om-knowledge/diagrams/
```

**Result (this build):** **zero hits**.

Also confirmed absent in public HTML／SVG: `HVAC` as system name；`D1`；Essential／發電機 marked `旁路`；honesty／disclaimer page；production credits；fake Pa／ACH／kW facts；equipment tags.

**Must-keep present:** `MVAC`；`以獲批圖／O&M 為準`；`應急路徑`；abbr card with required English full names（AHU／CAV／VAV／HEPA／MVAC／UPS／AVSU／CCMS…）；**no OT row** in abbr card；all figure IDs above；tier title **教學對位**.

## Self-critique → revise（one pass）

| Lens | Finding | Action |
|---|---|---|
| Hierarchy | H1／eyebrow／EN sub clear；four-tier cards readable | Kept；sheet gap 14px |
| Type | Body 16px；tables were 0.85–0.9rem | Bumped table to ≥0.875–0.9375rem |
| Color | Hub kinship tokens；Warn red／Remember amber／Align cool | Unchanged palette |
| Spacing | Mobile single column；overflow risk on wide SVG／tables | `overflow-x: hidden` on `.wrap`；tables in scroll wrap |
| a11y | Sticky back 44px；focus-visible；figure alt；TOC anchors | Hub href fixed to `../../` |
| Bans | Source SVGs had OT／Prep／手術燈 | Relabeled before ship；rg CLEAN |

## Acceptance self-check

1. Mobile-first ~390 · no intentional horizontal overflow · body ≥16px — **PASS**（previews at 390）  
2. H1→H2→H3 · section `id` · TOC jump — **PASS**  
3. Must-keep strings — **PASS**  
4. Hard-ban `rg` on public HTML＋SVG — **PASS（0 hits）**  
5. Figures ID complete；no D1；D0d＝應急路徑；D2＝高要求房／緩衝／前室／走廊 — **PASS**  
6. Substance-v2 fidelity；fourth tier＝教學對位；no invented dead numbers — **PASS**  
7. No PDF／Ghostscript pipeline — **PASS**  
8. This DESIGN-NOTE — **PASS**

## Deliverables

| Path | Role |
|---|---|
| `/workspace/bse-notes/notes/om-knowledge/index.html` | Note page |
| `/workspace/bse-notes/notes/om-knowledge/diagrams/*.svg` | Figures（15；no D1） |
| `/workspace/bse-notes/notes/om-knowledge/note.json` | Meta（status: preview） |
| `/workspace/bse-notes/notes/manifest.json` | Hub list entry（path set） |
| `/workspace/bse-notes/notes/om-knowledge/DESIGN-NOTE-om-web-v3.md` | This file |
| `/workspace/bse-notes/notes/om-knowledge/previews/note-390-hero.png` | Optional preview |
| `/workspace/bse-notes/notes/om-knowledge/previews/note-390-upper.png` | Optional preview |

## Open questions（batch — none blocking ship）

Beatrice substance PASS（v3）：D0 center two-line **KEEP**；D0d「控制／關鍵負荷」**KEEP**. No open substance punches. v3.1＝presentation-only abbr popovers awaiting Justin visual OK via Sua.


## v3.1 — In-text EN abbreviation popovers（layout-only）

**Trigger:** Justin（via Sua）wants body EN abbrs to show full forms on tap／hover, not only the end-of-page 縮寫卡／first-mention parentheses.

### Locked design decision

| Rule | Choice |
|---|---|
| First mention parentheses | **KEEP** existing Beatrice parentheticals（do **not** strip） |
| Every EN abbr occurrence（incl. first） | Wrap with interactive control → popover shows **EN full + ZH full** |
| Rationale | Parentheses help print／scan；popover helps re-reads mid-scroll on phone |

### Interaction

- **Control:** `<button type="button" class="abbr-term">`（not native `<abbr title>` — weak on iOS Safari）
- **Mobile:** tap opens；tap outside／Escape／second tap on same abbr closes
- **Desktop:** hover (~280ms) opens same popover；click／tap still works；pointer leave closes if not focused
- **Keyboard:** focusable button；Enter／Space toggles；Escape closes；`:focus-visible` uses `--focus`
- **a11y:** `aria-expanded`；`aria-label`；`#abbr-live` polite live region announces expansion；popover `role="tooltip"`
- **Source of truth:** glossary table after `#abbr` h3（`.abbr-wrap` whose first `th`＝縮寫）. JS `findGlossaryTable()` → map on `DOMContentLoaded`. Compound key `ΔP／DP` → aliases `ΔP` and `DP`.
- **Visual:** dotted `--accent` underline；open state light accent wash；popover `--panel`／`--ink`／`--muted`／`--line`／`--accent`；max-width **280px**；fixed position clamped to viewport（no horizontal overflow at 320–430）
- **Skipped wraps:** glossary table itself；`script`／`style`／`svg`／`.figure .fid`；chrome `h1`／`.hero .en`／`.eyebrow`／`.topbar`（avoid title clutter）. Body prose、tier cards、TOC labels、blurb、fault tables：**wrapped** when token present.
- **Not rewritten:** Beatrice substance strings — only token wrap. Ban list unchanged.

### Demo flag（headless popup shot）

`?demo=abbr` — on load, opens the first preferred body abbr（MVAC → HEPA → CAV → CCMS → UPS, else first `.abbr-term`），scrolls it into view, sets class `demo-open`／`demo-abbr` on `html`. Used for `previews/note-390-abbr-popup.png`.

### Abbrs wrapped this build（body counts）

Present in glossary；body wrap counts vary by occurrence. Glossary table itself：**0** wraps. Tokens with **0** body hits this pass（still in map for future）：CHW、FSD、EMSD、HA、BSI、DP（body uses **ΔP**）、and any unused alias.

### Previews（regenerated）

| File | Notes |
|---|---|
| `previews/note-320-hero.png` | updated |
| `previews/note-390-hero.png` | updated |
| `previews/note-430-hero.png` | updated |
| `previews/note-390-upper.png` | updated |
| `previews/note-390-abbr-popup.png` | **new** — popover open on MVAC（via `?demo=abbr`） |

### Acceptance add-on（v3.1）

1. Ban `rg` still **0** on public HTML+SVG — PASS  
2. Popover at 320／390／430 — no overflow — PASS  
3. Glossary＝source of truth；no substance wording edits beyond wraps — PASS  
4. First-mention parentheses retained — PASS  
5. `note-390-abbr-popup.png` exists with open popover — PASS  

## Out of scope（this task）

- Hub `index.html` rebuild（Jessie）  
- GitHub Pages publish／CTA flip Coming soon→Open（front door after substance pass＋Justin OK）  
- PDF export  
