# EarthAsks

Source for **[earthasks.com](https://earthasks.com)** — a static site hosted on GitHub Pages.

## What updates itself, and what you edit

- **Cardnews** is pulled live from Bluesky. To add a card, just post it on the **[@climate-nature.bsky.social](https://bsky.app/profile/climate-nature.bsky.social)** account and it appears on the site on its own. (A small built-in list acts as a fallback if the feed is ever unreachable — you don't need to maintain it.)
- **Latest videos** are pulled live from the EarthAsks **[YouTube channel](https://www.youtube.com/@EarthAsks)**. Upload there and the newest video shows up automatically.
- **Documents** is the one section you maintain by hand, in `index.html`. Instructions are below.

## Updating the Documents section

1. Open `index.html`.
2. Search for `const DOCUMENTS` — it's in the `<script>` block near the bottom of the file.
3. Add a new entry to the list, **newest first**, then save.

A single entry looks like this:

```js
{
  kind:     "Report",
  title:    "State of the Global Climate 2026",
  titleAlt: "",
  link:     "https://example.org/report",
  citation: "World Meteorological Organization (2026). State of the Global Climate 2026.",
  date:     "2026-06"
},
```

### Fields

| Field | Required | What it does |
| --- | :---: | --- |
| `title` | yes | The document title — the main line. (An entry with no title is skipped.) |
| `kind` | no | The small colored label, e.g. `Report`, `Manuscript`, `Paper`, `Assessment`. Defaults to `Document`. |
| `link` | no | Where the entry opens, in a new tab. Omit for no link. |
| `citation` | no | A full citation, shown in italics beneath the title. |
| `titleAlt` | no | A second line under the title — used here for the Korean title. Leave as `""` if not needed. |
| `date` | no | Shown on the right side. Formats below. |

### Date formats

Write the date as `YYYY`, `YYYY-MM`, or `YYYY-MM-DD`; it's formatted for display automatically:

| You write | Page shows |
| --- | --- |
| `2026` | 2026 |
| `2026-06` | Jun 2026 |
| `2026-06-14` | Jun 14, 2026 |

(Slashes also work, e.g. `2026/06/14`.)

### Good to know

- **Order is exactly as written**, top to bottom — so add new documents at the top of the list.
- **Put a comma after each entry's closing `}`.** A trailing comma after the very last entry is fine too, so when in doubt, add one.
- **To remove a document**, delete its whole `{ … }` block.
- **Card colors are automatic** — they cycle on their own; there's nothing to set.

## Publishing your change

Commit and push to the `main` branch. GitHub Pages rebuilds the site automatically, usually within a minute. If the change doesn't show up, hard-refresh or open the page in a private window — browsers cache aggressively.
