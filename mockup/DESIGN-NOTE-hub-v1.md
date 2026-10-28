# DESIGN NOTE — hub-v1

**Designer:** Celine · **Date:** 2026-10-28 (Asia/Hong_Kong)  
**Mockup:** `mockup/hub-v1.html` · **Brief:** `briefs/brief-hub-v1.md` · **Logo:** `logos/bse-notes.svg`

## Tokens (psychart / BSE Tools kinship)

| Token | Value |
|---|---|
| `--canvas` | `#EEF1F4` |
| `--panel` | `#FFFFFF` |
| `--ink` | `#1E2A50` |
| `--muted` | `#5A6178` |
| `--line` | `#C8CDD8` |
| `--accent` | `#C45C26` |
| `--focus` | `#174A7C` |
| body bg | `#D8DCE2` |
| type | system + Noto Sans TC / PingFang TC |

Logo secondary stroke uses `#90A0C4` (not the tools hub’s near-identical slate that embeds the floor-ID digraph in hex) so a naive substring ban `rg` does not false-positive on color codes.

## Locks reflected

A1 stacked cards · B1 newest-first (copy in intro/footer) · C1 date under title (`—` until publish) · D1 Coming soon CTA not a link · E1 out of this mockup.

**Provisional** site title **BSE Notes** / **BSE 學習筆記**.  
**Card (Justin title A locked):** **OM-Knowledge｜屋宇裝備 O&M 原則** · EN *Building services O&M principles* · `2026-10-28` · system blurb · Coming soon. Visual OK pending. No hospital/OT chrome.

## Self-critique → actions

| Area | Finding | Action |
|---|---|---|
| Hierarchy | Appbar → intro → sheet label → card title → date → purpose → CTA reads clearly | Keep |
| Type | Matches tools hub scale (17/15/13/12/11) | Keep |
| Color | Same token set as tools; notebook mark uses accent spine | Keep; secondary stroke `#90A0C4` for ban-rg safety |
| Spacing | Sheet/card gaps match tools; one card leaves empty sheet (OK for D1) | Keep |
| a11y | Soon card is `<div>` not `<a>`; CTA `pointer-events: none`; card has `aria-label`; tap ≥44 | Keep |
| Ban | No hospital / Block / floor / internal-working-title strings in HTML / meta / footer / card | Verified clean on mockup HTML + logos SVG |
| ZH wrap | `overflow-wrap` + `keep-all` on ZH lines | Keep |
| Redundancy | Intro + footer both disclaim Code checker | Acceptable honesty (tools pattern); leave |

No further visual revision required before Justin review.

## Shots

Chromium headless only (WebKit not available on this box — note for Jessie: still prove iPhone WebKit on preview).

```bash
SHOTS=/workspace/bse-notes/mockup/shots
HTML=file:///workspace/bse-notes/mockup/hub-v1.html
for W in 320 390 430; do
  google-chrome --headless=new --disable-gpu --hide-scrollbars \
    --window-size=${W},900 \
    --screenshot="${SHOTS}/hub-${W}.png" \
    "${HTML}"
done
```

Outputs: `mockup/shots/hub-320.png`, `hub-390.png`, `hub-430.png`.

## Jessie hold

Do not build until Justin OK via Sua. Site name may still swap from provisional.
