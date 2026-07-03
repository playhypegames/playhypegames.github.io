# playhypegames.github.io

The PlayHype Games website — marketing homepage + support/legal pages for every game.
Live at **https://playhypegames.github.io/** (GitHub Pages, auto-deploys from `main`).

## Layout

```
index.html          ← homepage (logo, game cards, SEO meta, structured data)
logo.svg            ← brand logo lockup (for socials / press)
og-image.png        ← 1200×1200 social share image
apple-touch-icon.png
robots.txt          ← allows crawlers, points to the sitemap
sitemap.xml         ← every indexable URL
ballup/  swarmly/  freedembirdz/   ← each game's support + privacy + terms
```

⚠️ The per-game folders are **live URLs referenced inside the shipped apps** — don't
rename or delete them.

## How to add a game

The homepage cards are **static HTML** (deliberately — it's better for SEO than
JS-generated content: crawlable, no layout shift). To add a game:

1. **Card** — in `index.html`, copy one `<article class="card">…</article>` block inside
   `<div class="grid">` and edit it: name, tagline, description, the two accent colors
   (`--a` / `--b` in the `style`), and the App Store link. Use the **live** badge +
   `<a class="btn store">` for shipped games, or the **soon** badge +
   `<span class="btn store disabled">Coming Soon</span>` for upcoming ones.
2. **Structured data** — copy one `"@type": "VideoGame"` object in the JSON-LD `@graph`
   in `<head>` and edit name / description / url.
3. **Sitemap** — add the game's `/support/` `<url>` entries to `sitemap.xml`.
4. **Support pages** — copy an existing game folder (e.g. `ballup/` → `newgame/`) and edit
   its privacy / terms / support HTML.
5. **Nice-to-have** — add the name to the `.marquee` strip and the footer "Support & Legal"
   list (both static in `index.html`).

Commit + push — Pages redeploys in ~a minute.

## Updating the App Store links

The two live games use placeholder links. Search `index.html` for **`id0000000000`** and
replace each with the real App Store URL (`https://apps.apple.com/app/id…`).

## SEO notes

- Title, meta description, canonical, Open Graph, Twitter card, and `theme-color` are all set.
- Structured data: `Organization` + `WebSite` + one `VideoGame` per game (JSON-LD).
- `robots.txt` + `sitemap.xml` are served at the root.
- **After deploying**, submit the site + sitemap in
  [Google Search Console](https://search.google.com/search-console) to get indexed faster.
