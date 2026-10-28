# BSE Notes hub — Direction note

**Designer:** Celine · **Coordinator:** Sua · **Substance:** Beatrice · **Builder (after brief):** Jessie  
**Repo (planned):** `justinksw/bse-notes` · GitHub Pages  
**Status:** Direction only — **no mockup / no build** until Justin yes on A–E. **Public-name hard ban locked** (Justin 2026-10-28 via Sua).  
**Skills:** design-build-handoff (UI/repo) · substance-design-notes (study substance → design; web notes are redesigned for screen, not PDF paste)

## Goal

A GitHub Pages **notes index** for Justin’s BSE learning notes: one place to see every note and open it. Hub list shows a **clear title** per note, **sorted by creation date** (newest first unless Justin says otherwise), each row/card a link into that note’s page.

First note (when Beatrice ships web substance + brief): internal working name OM-Knowledge — **public title must be bans-safe** (no hospital / Block / site / project names). Web layout is a **new screen design** — do **not** reuse the A5 PDF card pagination.

Celine owns hub + note page layout / visual system. Beatrice owns facts / wording. Jessie builds after versioned brief. Celine does not invent BSE substance.

## Audience

- Justin studying on phone (primary); desktop Chrome secondary.
- HK BSE / MEP learning notes (Traditional Chinese heavy, same voice as PDF notes).
- Mobile-first; readable outdoors; few taps to open a note.

## Key screens

1. **Hub home** — site title + notes list (title clear; creation date visible; link per note).
2. **Note page** (first: OM-Knowledge) — long-scroll / section nav for phone; diagrams + four-tier cards redesigned for web (separate brief after Beatrice substance).
3. **Empty / soon** — hub can show “first note coming” until OM-Knowledge has a preview/live URL.

Out of this direction: rewriting OM PDF; inventing note titles/dates Beatrice hasn’t set; redesigning `bse-tools`.

## Constraints

- Free tools only.
- Phone **320–430px**, **desktop Chrome + iPhone WebKit** (Safari and iOS Chrome); no sideways scroll; Chinese line-break safe.
- Tap targets ≥44px; contrast AA+.
- Versioned `briefs/` in repo; one punch list per preview; live only after Justin OK.
- Visual kinship with BSE Tools / psychart tokens where useful: ink `#1E2A50`, accent `#C45C26`, canvas `#EEF1F4` — notes feel like study pages, not a vendor brochure.
- PDF notes stay on the PDF pipeline (Chrome/Skia; CURRENT pointer). This repo is **web Pages only**.

### Hard ban — public Pages (Justin 2026-10-28)

On **hub, note pages, layout copy, footer, and meta** (title / description / og), do **not** show item- or site-related identifiers. Align with Beatrice brief bans. Typical bans (non-exhaustive until Beatrice locks the list):

- Hospital / institution names  
- Block / floor / room / plant identifiers (e.g. Block, 8F, OT codes tied to a site)  
- Site-specific or project names  
- Paths or labels that would identify a real job or workplace  

Internal working titles (e.g. OM-Knowledge) stay off public chrome unless Beatrice supplies a **public** title. Acceptance will `rg` banned strings before share.

## Proposed direction (need Justin picks)

### A. Hub list layout

**Recommend A1.** One-column **stacked note cards** on phone: **title** (primary) · optional one-line subtitle · **creation date** · whole card or clear **Open** link. Newest creation date at top.

| Option | Layout | Tradeoff |
|---|---|---|
| **A1 (rec)** | Full-width cards, title + date + Open | Titles stay clear at 320; easy to add notes |
| A2 | Compact list rows (title left, date right, chevron) | More notes above the fold; less room for subtitle |
| A3 | Group by topic / tag, then date within group | Better when many notes; needs Beatrice tags first |

### B. Sort default

**Recommend B1.** Sort by **creation date, newest first**. Note pages keep a stable URL; renaming title does not reshuffle if date is fixed at publish.

| Option | Sort | Tradeoff |
|---|---|---|
| **B1 (rec)** | Creation date ↓ | Matches Sua brief; predictable |
| B2 | Last updated ↓ | Surfaces edits; “creation” less visible |
| B3 | Manual / pinned order | Full control; more editor work |

### C. Date display

**Recommend C1.** Show creation as `YYYY-MM-DD` (Asia/Hong_Kong) under the title; no relative “3 days ago” only.

| Option | Display | Tradeoff |
|---|---|---|
| **C1 (rec)** | Absolute date under title | Clear for study archive |
| C2 | Absolute + relative | Friendlier; noisier |
| C3 | Date only in metadata / omit on card | Cleaner cards; weaker “sort by date” cue |

### D. First-note empty state

**Recommend D1.** Hub ships with one **Coming soon** card using Beatrice’s **public** note title (bans-safe) until preview/live URL exists; then swap to Open. No fake body content on hub; no internal/site names on the card.

### E. Note page shell (high level only)

**Recommend E1.** Sticky top bar: site name → Hub · note title. In-page **section jump** (TOC) for long notes. Body = mobile long-scroll sections (not A5 page breaks). Detail layout waits for Beatrice OM web substance + `CELINE-BRIEF-…`.

## Out of this direction

Mockups, `briefs/brief-hub-v1.md`, Jessie build, OM-Knowledge web layout — **after** Justin yes on A–E (and Beatrice substance for the note).

## Ask Justin (via Sua)

Please pick (or say “go with Celine’s recs”):

1. **A** — Hub list (A1 / A2 / A3)  
2. **B** — Sort (B1 / B2 / B3)  
3. **C** — Date display (C1 / C2 / C3)  
4. **D** — Coming-soon card for first note OK? (yes / tweak)  
5. **E** — Note shell E1 OK as starting point? (yes / tweak)  
6. Optional: preferred site title — e.g. **BSE Notes** / **BSE 學習筆記** / other  

Then Celine → hub mockup + `briefs/brief-hub-v1.md` → Jessie preview → one punch list → live after Justin OK.  
In parallel: when Beatrice sends OM-Knowledge **web** substance + designer brief, Celine redesigns note 1 for screen (no PDF layout reuse) and reports via Sua.

## Infra

Repo `justinksw/bse-notes` + GitHub Pages scaffold exists (PREVIEW). Cursor GitHub App access may still need granting for cloud agents. Direction / mockups can proceed without cloud.
