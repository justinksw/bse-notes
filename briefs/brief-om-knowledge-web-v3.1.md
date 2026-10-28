# Brief — OM-Knowledge web note v3.1（layout pack）

**For:** Justin visual OK via Sua → then Jessie preview build  
**Designer:** Celine · **Content:** Beatrice (substance-v2 locked；substance PASS on v3)  
**Date:** 2026-10-28 (Asia/Hong_Kong)  
**Supersedes for layout review:** `brief-om-knowledge-web-v3.md`（keep v3 on disk）  
**Bump type:** v3.m layout-only — **in-text EN abbreviation popovers**

## Sources

| Doc | Path |
|---|---|
| Beatrice content brief | `briefs/CELINE-BRIEF-OM-knowledge-web-v3.md`（locked） |
| Substance | `/workspace/qeh_study/briefs/OM-KNOWLEDGE-web-substance-v2.md` |
| DESIGN-NOTE | `notes/om-knowledge/DESIGN-NOTE-om-web-v3.md`（header now v3.1） |
| Mockup HTML | `notes/om-knowledge/index.html` |
| Figures | `notes/om-knowledge/diagrams/`（unchanged from v3） |
| Previews | `notes/om-knowledge/previews/note-{320,390,430}-hero.png`, `note-390-upper.png`, **`note-390-abbr-popup.png`** |

## What changed vs v3

| Item | v3 | v3.1 |
|---|---|---|
| Substance／chrome A／figures／bans | locked | **unchanged** |
| First-mention parentheses | present | **kept** |
| Body EN abbrs | plain text（+ end table） | **tap／hover popover** → EN＋ZH from 縮寫卡 |
| Native `<abbr title>` | — | **not used**（iOS Safari weak） |
| Demo shot flag | — | `?demo=abbr` |

## Interaction summary

1. Glossary table（after `#abbr`）＝single source of truth；JS builds map on load.  
2. Whole-token wrap（word boundaries）for keys including `O&M`、`ΔP`／`DP`、`Novec`.  
3. Custom `<button class="abbr-term">` + fixed `#abbr-pop` panel；Escape／outside／re-tap closes.  
4. Keyboard＋live region for VoiceOver.  
5. Skip：glossary table、SVG／fid、h1／EN sub／eyebrow／topbar.  
6. Tokens：dotted `--accent` underline；popover uses `--panel`／`--ink`／`--muted`／`--line`／`--accent`；max-width ~280px.

## Acceptance（v3 checklist + v3.1）

All v3 items still apply, plus:

13. In-text abbr popover works at **320／390／430** without horizontal overflow.  
14. Popover copy matches glossary EN／ZH exactly.  
15. First-mention parentheses still in body（Beatrice text not stripped）.  
16. Ban `rg` still **0**.  
17. Preview **`note-390-abbr-popup.png`** shows open popover（captured with `?demo=abbr`).  
18. No substance wording edits beyond wrapping controls.

## Out of scope

- Hub layout／live merge  
- Inventing BSE facts  
- PDF／Ghostscript  
- Changing Beatrice opens（D0／D0d already KEEP）

## Ask Justin (via Sua)

OK note **v3.1** layout（abbr in-text popovers）→ Jessie preview?  
Hub live still holds until separate Justin live OK.
