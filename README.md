# mhzgames.com

The studio's front door: one static page, served by GitHub Pages at
`https://mhzgames.com`. `.nojekyll` keeps Pages from injecting a theme, and
`CNAME` pins the custom domain (Pages clears the setting if this file goes).

Per-game privacy policies live in the sibling `mhazki/privacy` repo at
`privacy.mhzgames.com`; this page only links to them.

`support/index.html` is the **Support URL** both stores require on the app
listing (App Store Connect makes it mandatory). It is publisher-level with a
per-game section, so a second game adds a heading rather than a second page.
Apple checks the URL resolves and is about the app — a 404 or a bare mailto is
a metadata rejection.
