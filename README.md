# mhzgames.com

The studio's front door, served by GitHub Pages at `https://mhzgames.com`.
`.nojekyll` keeps Pages from injecting a theme, and `CNAME` pins the custom
domain (Pages clears the setting if this file goes).

## Design

The look is the portfolio's, at `hazki.vercel.app` — same oklch neutral
tokens, same Geist / Geist Mono / Geist Pixel typography, same 1300px column
with hairline rules down both edges. That site is Next.js + Tailwind v4; this
one is three static files, so `styles.css` transcribes those tokens by hand
and writes the Tailwind utilities out as plain classes. **If the portfolio's
palette moves, `styles.css` has to be updated to match — there is no build
step to do it.**

Monochrome throughout. The old `#ECAE2C` yellow is gone; emphasis comes from
opacity and the white hover glow. The one deliberate exception is the Google
Play badge, which stays full-colour because Google's guidelines forbid
recolouring it.

Geist and Geist Mono load from Google Fonts. Geist Pixel is not on the CDN, so
`fonts/GeistPixel.woff2` travels with the repo and every page preloads it.

The portfolio's custom cursor, scramble text and scroll animations are
deliberately **not** ported — a three-page brochure site does not need them,
and leaving them out keeps the site at zero JavaScript.

## Pages

`support/index.html` is the **Support URL** both stores require on the app
listing (App Store Connect makes it mandatory). It is publisher-level with a
per-game section, so a second game adds a heading rather than a second page.
Apple checks the URL resolves and is about the app — a 404 or a bare mailto is
a metadata rejection.

`driftversus/` is the game's page: banner, icon, screenshots and the store
copy, with its images in `driftversus/img/` (web-sized exports of the Play
Store assets). Its copy follows `STORE_LISTING.md` in the TRV repo, so update
both together, and never claim something the shipped build does not do.

`highwayversus/` holds only `img/` for now. The game is a **Play Console
draft** (`id.mhz.highwayversus`, entered 2026-09-06), not a release, so the
front door lists it under "Next up" as a non-clickable card with an
"In development" pill — no store link, because there is no store page to
link to. Its one line of copy is the approved short description from
`STORE_LISTING.md` in the THS repo, where every claim is checked against the
endless build. **When the listing goes live**, the card becomes a link, the
pill changes, and this page gets a `/highwayversus/index.html` of its own —
the icon, feature graphic and three screenshots are already in `THS/store/`.

Per-game privacy policies live in the sibling `mhazki/privacy` repo at
`privacy.mhzgames.com`; these pages only link to them.

`app-ads.txt` authorises AdMob to sell inventory and must keep resolving at
the domain root — AdMob crawls it.
