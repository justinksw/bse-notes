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
| `slug` | Must match folder name; a generic teaching slug (e.g. `note-01`) |
| `title` | Clear public English title for the hub |
| `titleZh` | Optional Chinese title |
| `created` | ISO date `YYYY-MM-DD` — hub sorts by this **descending** (newest first) |
| `updated` | ISO date when content last changed |
| `status` | `draft` \| `preview` \| `published` |
| `summary` | One line for the index card |

## Hub

`index.html` at repo root lists every note under `notes/*/note.json` (via `notes/manifest.json`), sorted by `created` descending. Titles must stay clear and scannable.

## Public names (Pages + public repo)

Use generic teaching titles only. No site, client, workplace, or project identifiers in public chrome, docs, or commit messages.

That covers README, hub and note HTML, meta, titles, blurbs, preview banners, and other public text. Internal working titles stay off public chrome until a generic public title is set.

## Do not

- Create a new GitHub repo for each note
- Put calculator/tool apps here (those belong in bse-tools / sibling tool repos)
