# EarthAsks

Source for **[earthasks.com](https://earthasks.com)** — a static site hosted on GitHub Pages.

## What updates itself, and what you edit

- **Cardnews** is pulled live from Bluesky. Post on the **[@climate-nature.bsky.social](https://bsky.app/profile/climate-nature.bsky.social)** account and it appears on the site automatically.
- **Latest videos** are pulled live from the EarthAsks **[YouTube channel](https://www.youtube.com/@EarthAsks)**. Upload there and the newest video shows up on its own.
- **Documents** is the one section you maintain by hand — and it now lives in its own file, **`Documents.html`**. The homepage shows the latest few by reading that same file, so you never edit `index.html` to add a document.

## Adding or editing a document

1. Open **`Documents.html`**.
2. Find the block marked `EDIT YOUR DOCUMENTS HERE` (near the bottom of the file).
3. Add a new entry to the list, **newest first**, then save.

An entry looks like this:

```json
{
  "kind": "Report",
  "title": "State of the Global Climate 2026",
  "titleAlt": "",
  "link": "https://example.org/report",
  "citation": "World Meteorological Organization (2026). State of the Global Climate 2026.",
  "date": "2026-06"
}
```

That one block feeds both the standalone Documents page and the homepage preview.

### Fields

| Field | Required | What it does |
| --- | :---: | --- |
| `title` | yes | The document title — the main line. (An entry with no title is skipped.) |
| `kind` | no | The small colored label, e.g. `Report`, `Manuscript`, `Paper`, `Assessment`. Defaults to `Document`. |
| `link` | no | Where the entry opens, in a new tab. Use `""` for no link. |
| `citation` | no | A full citation, shown in italics beneath the title. |
| `titleAlt` | no | A second line under the title — used here for the Korean title. Use `""` if not needed. |
| `date` | no | Shown on the right side. Formats below. |

### Date formats

Write the date as `YYYY`, `YYYY-MM`, or `YYYY-MM-DD`; it's formatted for display automatically:

| You write | Page shows |
| --- | --- |
| `2026` | 2026 |
| `2026-06` | Jun 2026 |
| `2026-06-14` | Jun 14, 2026 |

(Slashes also work, e.g. `2026/06/14`.)

### A few JSON rules

The list is JSON, which is strict about punctuation. If the page ever shows a "needs a small fix" message, check these:

- **Double quotes** around every name and value — not 'single quotes'.
- **A comma between entries, but not after the last one.**
- To include a `"` inside a value, write it as `\"`.

The page will point you to the spot if something is off.

### Good to know

- **Order is exactly as written**, top to bottom — so add new documents at the top.
- The homepage shows the **latest 4**; the full list always lives on `Documents.html`.
- **To remove a document**, delete its whole `{ … }` block.
- **Card colors are automatic** — nothing to set.

## Publishing your change

Commit and push to the `main` branch. GitHub Pages rebuilds automatically, usually within a minute. If the change doesn't show up, hard-refresh or open the page in a private window — browsers cache aggressively.
