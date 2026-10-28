# BSE Notes hub — Direction note

**Designer:** Celine · **Coordinator:** Sua · **Substance:** Beatrice · **Builder (after brief):** Jessie  
**Repo:** `justinksw/bse-notes` · GitHub Pages  
**Status:** Justin locked public note title **OM-Knowledge｜屋宇裝備 O&M 原則** (2026-10-28). Site name provisional **BSE Notes**.  Justin locked **A1 / B1 / C1 / D1 / E1** (2026-10-28 via Sua). Site title **provisional: BSE Notes** / ZH **BSE 學習筆記** (Sua confirming final name). **Mockup + `briefs/brief-hub-v1.md` ready for Justin OK.** Jessie hold until Justin yes. **Public-name hard ban locked.**  
**Skills:** design-build-handoff (UI/repo) · substance-design-notes (study substance → design; web notes are redesigned for screen, not PDF paste)

## Goal

A GitHub Pages **notes index** for Justin’s BSE learning notes: one place to see every note and open it. Hub list shows a **clear title** per note, **sorted by creation date** (newest first), each row/card a link into that note’s page.

First note (when Beatrice ships web substance + brief): public title must be bans-safe (no hospital / Block / site / project names). Web layout is a **new screen design** — do **not** reuse the A5 PDF card pagination.

Celine owns hub + note page layout / visual system. Beatrice owns facts / wording. Jessie builds after versioned brief. Celine does not invent BSE substance.

## Audience

- Justin studying on phone (primary); desktop Chrome secondary.
- HK BSE / MEP learning notes (Traditional Chinese heavy, same voice as PDF notes).
- Mobile-first; readable outdoors; few taps to open a note.

## Key screens

1. **Hub home** — site title + notes list (title clear; creation date visible; link per note). ← **this pack**
2. **Note page** (first note) — long-scroll / section nav for phone; diagrams + four-tier cards redesigned for web (separate brief after Beatrice substance). ← later
3. **Empty / soon** — hub shows one **Coming soon** card until first note has a preview/live URL. ← in hub-v1 mockup

Out of this direction: rewriting PDF notes; inventing note titles/dates Beatrice hasn’t set; redesigning `bse-tools`.

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

Internal working titles stay off public chrome unless Beatrice supplies a **public** title. Acceptance will `rg` banned strings before share.

## Locked decisions (Justin 2026-10-28)

| Item | Lock |
|---|---|
| **A** Hub list | **A1** full-width stacked cards (title + date + Open / Coming soon) |
| **B** Sort | **B1** creation date newest-first |
| **C** Date display | **C1** `YYYY-MM-DD` under title |
| **D** First-note empty | **D1** Coming soon card → Open when published |
| **E** Note shell | **E1** back-to-Hub + long-scroll + section jump — **hub only in this pack**; note body = later brief |
| Site title | **Provisional:** **BSE Notes** / **BSE 學習筆記** (Sua confirming; swap when decided) |

## Provisional public card (v1 mockup)

| Field | Value |
|---|---|
| EN title | **O&M knowledge** |
| ZH title | **運作維修知識** |
| Date | `—` until publish metadata exists |
| CTA | Coming soon · 即將推出 (not a link) |
| Purpose | Generic teaching only — no site / Block / hospital |

## Deliverables (this pack)

- `mockup/hub-v1.html` · `logos/bse-notes.svg` · `briefs/brief-hub-v1.md` · `mockup/DESIGN-NOTE-hub-v1.md` · `mockup/shots/hub-{320,390,430}.png`

## Ask Justin (via Sua)

OK hub **v1** mockup + brief for Jessie preview build after site name final (or build with provisional title and swap)? Tweaks welcome as one punch list.

In parallel: when Beatrice sends first-note **web** substance + designer brief, Celine redesigns note 1 for screen (no PDF layout reuse) and reports via Sua.
