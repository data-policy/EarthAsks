# Cardnews images

Put your high-resolution cardnews image files **in this folder** (PNG or JPG).
600-dpi exports are welcome — they're shown scaled on the page and open at full
resolution when a visitor taps a card.

## Naming (recommended)
Prefix the date so files stay in order, e.g.:

    2026-06-14-gdp-growth.png
    2026-05-30-steel-production.png

## Show it on the site
Open `index.html`, find the **EDIT THIS SECTION** block near the bottom, and add
an entry to `CARDNEWS` with the newest first:

    {
      title:  "Your cardnews title",
      image:  "cardnews/2026-06-14-gdp-growth.png",
      link:   "https://your-source-or-post-link",
      source: "Author/Org (Year). Title. Publisher.",
      date:   "2026-06-14"
    },

Referencing a file in this folder (rather than a shortened link) is the most
reliable way to make the image display.
