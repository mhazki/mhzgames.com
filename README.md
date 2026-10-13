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
per-game section, so a second game adds a heading rather than a second page (Highway Versus does
not have its section yet).
Apple checks the URL resolves and is about the app — a 404 or a bare mailto is
a metadata rejection.

`driftversus/` is the game's page: banner, icon, screenshots and the store
copy, with its images in `driftversus/img/` (web-sized exports of the Play
Store assets). Its copy follows `STORE_LISTING.md` in the TRV repo, so update
both together, and never claim something the shipped build does not do.

`highwayversus/` is the second game's page, built on the same template as
`driftversus/`, with web-sized exports of `THS/store/` (icon, feature graphic,
and Play screenshots 1–6) in `highwayversus/img/`. It went live on Google Play
on 2026-10-13 (`id.mhz.highwayversus`, listed as *Highway Versus: Traffic
Racing*), so the front door now lists it under "Out now". Its copy follows the
live Play listing, which `STORE_LISTING.md` in the THS repo checks against the
endless build. The unused `.game-wip` / `.status` styles in `index.html` stay
for the next unreleased game.

Per-game privacy policies live in the sibling `mhazki/privacy` repo at
`privacy.mhzgames.com`; these pages only link to them.

`app-ads.txt` authorises AdMob to sell inventory and must keep resolving at
the domain root — AdMob crawls it.
