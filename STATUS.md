# Côn Bằng: Kình Ngư Cuối Cùng — project status

Last updated: 2026-10-29

## What this is
A single-page scrollytelling lore site for a friend's Vietnamese fantasy world: Côn Bằng, the last
sky leviathan, the five whale falls (Kình Lạc) that reversed Earth's five mass extinctions, the Seven
Super Beasts (Thất Thú), the purple crystal seals, and the citadel on his back. Vietnamese and English
only (JA/FR/DE were considered and dropped by Mark on 2026-10-29).

Live site (GitHub Pages, public): https://mtritaris.github.io/con-bang/ — repo https://github.com/mtritaris/con-bang (master, serves /docs)
Claude artifact (private, Mark's account): https://claude.ai/artifact/HgYvpJBCB2VCNsYuB8NHuf

## Files
- `index.html` — the whole page (CSS, markup, content data, behaviour). Authored for the Claude
  artifact wrapper, so it has no doctype/html/head/body tags of its own. ~89 KB, no build step, no
  dependencies beyond Google Fonts (Cormorant Garamond, Be Vietnam Pro, JetBrains Mono, Noto Serif JP).
- `build.sh` — wraps `index.html` into a complete standalone document at `docs/index.html`
  (adds doctype, viewport, iOS web-app metas). Run `./build.sh` after any edit before hosting.
- `docs/index.html` — generated; do not edit by hand. Served by GitHub Pages (legacy mode only allows `/` or `/docs`).
- `STATUS.md` — this file.

Own git repo since 2026-10-29, pushed to GitHub; Pages deploys from master:/docs automatically on push.

## Page structure (ids used by nav)
`#top` hero · `#story` original text + key terms · `#chronicle` five extinctions timeline ·
`#whalefall` real whale-fall stages vs myth · `#beasts` Thất Thú grid + canon meters ·
`#seals` ring of 7 seals · `#citadel` castle cross-section with 6 hotspots · `#vow` closing quote ·
`#bible` canon vs open questions · footer.

All editable copy lives in the `D` object in the first `<script>`: `epochs`, `stages`, `beasts`,
`seals`, `rooms`, `canon`, `open`, and `ui` (EN strings; VI defaults are captured from the markup
via `data-i` attributes at load). To change Vietnamese UI text, edit the markup; to change English,
edit `D.ui.en`.

## Canon decisions taken (flagged on the page)
- Kept the original Vietnamese text verbatim (light punctuation only) in `#storyCard`.
- Read "siêu thú yêu nhất" as "yếu nhất" (weakest); sentence structure supports it. Confirm with author.
- Seal count is not in the source. Page proposes 7 (one per super beast); the seventh "Ấn Thệ" is
  the vow itself. Tagged as design proposal.
- Generation names for the five mothers (Mẹ Ordovic … Mẹ Phấn Trắng) are suggestions, tagged `ext`.
- Citadel rooms: Hall of the Vow and Seal Core tagged canon-derived; the other four are extensions,
  including a Lodgings wing left open for the friend's hospitality angle.
- Six beast slots deliberately blank ("???") per the source.
- Real-world figures (dates, % species lost, whale-fall stage durations) are rounded and labelled
  estimates.

## Delivering to the friend's iPhone (resolved 2026-10-29: GitHub Pages, option 2)
Options, in order of ease:
1. Share the artifact from its Share menu, text the link; Safari → Share → Add to Home Screen.
2. Host `docs/index.html` (GitHub Pages / Netlify / Cloudflare Pages), then Add to Home Screen.
   Standalone build already carries the iOS web-app metas.
3. AirDrop `docs/index.html`; opening from Files uses Quick Look, which may not run the scripts.

## Next ideas (not started)
- Apple touch icon (PNG, 180×180) and a web manifest for a proper home-screen install.
- Fill in the six beasts and the "brutal battle" once the author decides them.
- Possible second artifact: hospitality sim / guest-house angle on the Lodgings wing.
- Vietnamese voice or whale-song audio samples instead of synthesised ambience.
- Author review of all EN translations and the eight open questions in `#bible`.
