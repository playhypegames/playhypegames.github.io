# playhypegames.github.io

The PlayHype Games website — marketing homepage + support/legal pages for every game.
Live at **https://playhypegames.github.io/** (GitHub Pages, auto-deploys from `main`).

## Layout

```
index.html          ← homepage (logo, game cards, everything)
logo.svg            ← standalone brand logo (reuse for socials/press)
ballup/             ← Ball Up support + privacy + terms
swarmly/            ← Swarmly support + privacy + terms
freedembirdz/       ← Freedem Birdz support + privacy + terms
```

⚠️ The per-game folders are **live URLs referenced inside the shipped apps** —
don't rename or delete them.

## How to add a game

Everything on the homepage (card, marquee, footer links) is generated from the
`GAMES` array at the top of the `<script>` in `index.html`.

1. Copy an existing game's folder (e.g. `ballup/` → `newgame/`) and edit the
   privacy/terms/support HTML for the new game.
2. In `index.html`, copy one object in the `GAMES` array and edit:
   - `name`, `tagline`, `desc` — the card copy
   - `status` — `"live"` (green badge + App Store button) or `"soon"` (amber badge)
   - `appStore` — the real App Store link (`https://apps.apple.com/app/id…`)
   - `pages` — the folder name from step 1
   - `accent` / `accent2` — two colors for the card's gradient
   - `art` — optional inline SVG icon; or delete it and set `icon: "🚀"` (any emoji)
3. Commit + push. Pages redeploys automatically in ~a minute.

## Updating App Store links

Search `index.html` for `PASTE` — each game's `appStore` field has a marked
placeholder. Replace with the real link and push.
