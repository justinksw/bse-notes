# Notes folder convention

## Layout

```
notes/
  <slug>/                 # kebab-case, stable URL segment
    note.json             # metadata (required)
    index.html            # note page (required when published)
    assets/               # optional note-local images/files
```

## `note.json`

```json
{
  "slug": "note-01",
  "title": "Note 1",
  "titleZh": "筆記 1",
  "created": "2026-10-28",
  "updated": "2026-10-28",
  "status": "draft",
  "summary": "One-line description for the hub listing."
}
```

| Field | Rules |
| --- | --- |
| `slug` | Must match folder name; generic (e.g. `note-01`), not a site/project code |
| `title` | Clear **public** English title for hub — bans-safe |
| `titleZh` | Optional Chinese title — bans-safe |
| `created` | ISO date `YYYY-MM-DD` — hub sorts by this **descending** (newest first) |
| `updated` | ISO date when content last changed |
| `status` | `draft` \| `preview` \| `published` |
| `summary` | One line for the index card — bans-safe |

## Hub

`index.html` at repo root lists every note under `notes/*/note.json` (via `notes/manifest.json`), sorted by `created` descending. Titles must stay clear and scannable.

## Public-name ban (Pages + public repo)

Do **not** put any of the following in README, hub/note HTML, meta, preview banners, commit messages, or other public chrome:

- Hospital / institution names
- Block / floor / room / plant identifiers tied to a real site
- Customer, project, or workplace names
- Paths or labels that would identify a real job

Internal working titles stay off public chrome until a bans-safe **public** title is set. Before share, `rg` for known banned strings.

## Do not

- Create a new GitHub repo for each note
- Put calculator/tool apps here (those belong in bse-tools / sibling tool repos)
