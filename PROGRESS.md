# Progress

A dated log of the work, newest first.

## 2026-11-05, A new brain tile

Later the same day as the new logo. Pushed to `main` on 2026-11-05 on the user's go-ahead, after they saw a local preview.

### Changes

- The brain tile of the logo is redrawn. Outside feedback said the first brain (seen from above, two mirrored halves with curly folds) looked like worms or noodles in a bowl, and suggested a side view.
- `logo.svg`: the brain is now a side view in cream lines on the green tile. It has an outlined bumpy silhouette, folds drawn as pairs of parallel lines that tuck under each other, a cerebellum and stem, and eleven short rays around it. Each fold is a wide cream stroke with a narrower green stroke on top, clipped to the inside of the brain by a clipPath (`inside-brain`). The outline is a `<use href="#cerebrum">` pair from `<defs>`.
- `favicon.svg`: at tab size the brain is a solid cream shape with one green groove, the cerebellum set off, and seven thicker rays.
- `index.html` and `404.html`: the `logo.svg` and `favicon.svg` links are bumped from `?v=3` to `?v=4`. `style.css` is unchanged and stays at `?v=3`.
- The design canvas (https://claude.ai/artifact/UZc7dp4b7V5o7L8tVmPri6) has two new boards, "G · Brain tile options" and "G · Brain, reference style", and board G now shows the new brain.

### Decisions

- A side view with outlined, interlocking folds and a ring of idea rays, option 4, "Bright idea" (the user, 2026-11-05). Two plain side views were rejected first. The user then shared a reference picture, a line drawing of a side-view brain with idea rays, and chose from three tiles drawn in that style. The drawing is original, in the reference's style, not a trace.
- The favicon gets its own simpler brain, because the folds turn to noise at 16 to 32 pixels. A version with three grooves was tried and dropped, because at 64 pixels it looked like a face.

### Files touched

- Changed: `logo.svg`, `favicon.svg`, `index.html`, `404.html`, `README.md`, `PROGRESS.md`.

### Checks

- Both SVGs rendered in headless Chromium: the logo at 200, 96, 40 and 28 pixels, the tab icon at 64, 32 and 16.
- In the browser on a local server at 1280 and 375 wide: both logo images load, the favicon link is `?v=4`, no horizontal overflow, no requests to outside hosts. The 404 page loads the new logo.
- Not run: axe-core. The outbound links were not re-checked, since they were not changed.

### Next steps

- None for the brain tile. The live check is recorded below.

### Live

- Commit fb3a545 was live at https://hearthandwit.com/ about 30 seconds after the push. The home page, `logo.svg?v=4` and `favicon.svg?v=4` answer 200 with the new drawings, and the custom 404 page shows the new logo.
- Checked with requests from the command line, not in a browser on the live address.

## 2026-11-05, The new logo

Pushed to `main` on 2026-11-05 on the user's go-ahead, after they saw a local preview.

### Changes

- A new logo, chosen by the user from a Claude design canvas (https://claude.ai/artifact/UZc7dp4b7V5o7L8tVmPri6, direction G, "Game tiles"): four rounded tiles, a flame (the hearth), a times sign (math), a die showing five (games), and a brain (thinking), with the name in rounded lowercase Fredoka lettering and an ember-colored ampersand. The user's steer was that the logo should balance the cosy hearth feeling with games, math, brains and thinking. The first round of ideas leaned too far toward cabin and fire.
- `logo.svg` is new and holds the full mark. It is shown at 28px in the top bar and at 200px in the hero, 152px on a phone. `favicon.svg` is replaced with a simpler version of the same tiles for browser-tab size: no brain folds, a heavier times sign and pips.
- A new `fonts/` folder holds `fredoka-600-latin.woff2` (16 KB, one weight, latin subset, downloaded from Google Fonts) and `OFL.txt`, its SIL Open Font License. The font is served from the site itself, so the page still makes no outside requests. It is used only for the name in the top bar (`.brand`) and the hero heading (`.wordmark`).
- `index.html`: the top bar brand is now the tile image plus the name. The hero's line-drawn flame in a grey circle is replaced by the tile mark. The hero h1 has the class `wordmark` and its ampersand is wrapped in `span.amp`.
- `404.html`: the same brand in the top bar. Its own h1 keeps the plain style.
- Both pages' stylesheet and favicon links are bumped from `?v=2` to `?v=3`, and `logo.svg` is linked with `?v=3` too.
- `style.css`: an `@font-face` rule for Fredoka, new `.brand` and `.brand img` rules, `.mark` without the circle, new `.wordmark` and `.wordmark .amp` rules (ampersand `#c2481a`, 4.9 to 1 on white), and phone sizes for `.wordmark` (42px) and `.mark` (152px).
- Left unchanged on purpose: the faint concentric-rings backdrop with its line flame, the navy accent, the app cards and their line icons, and the footer.

### Decisions

- The full logo G with a self-hosted font rather than the tiles alone (the user, 2026-11-05). Serving the one font file from the site keeps the promise of no outside requests.
- The favicon is a simplified cut of the tiles, not the full mark, because the brain folds and thin strokes do not hold up at browser-tab size.
- The name stays capitalised as "Hearth & Wit" in the markup and is shown lowercase by CSS, so screen readers and copied text keep the proper name.

### Files touched

- New: `logo.svg`, `fonts/fredoka-600-latin.woff2`, `fonts/OFL.txt`.
- Changed: `favicon.svg`, `index.html`, `404.html`, `style.css`, `README.md`, `PROGRESS.md`.

### Checks

- In the browser on a local server at 1280, 737 and 375 wide: no horizontal overflow, no console errors, Fredoka loads from the site's own folder, no requests to outside hosts. The brand link is 44px tall. The wordmark stays on one line at 375. The 404 page shows the new brand and keeps its plain heading.
- Not run: axe-core. The ten outbound links were not re-checked, since they were not changed.

### Next steps

- None for the logo. The live check is recorded below.

### Live

- Commit cddeb8c was live at https://hearthandwit.com/ about 35 seconds after the push. The home page, `logo.svg?v=3`, `favicon.svg?v=3`, `style.css?v=3`, the font file (served as `font/woff2`), and `fonts/OFL.txt` all answer 200. A missing path answers 404 with the custom page, which shows the new logo.
- Checked with requests from the command line, not in a browser on the live address.


## 2026-11-03, The modern look

### Changes

- The page was redesigned on a Claude design canvas (https://claude.ai/artifact/TTCScgfwjLVwmTNpnTZrmK, desktop and phone artboards) in the clean style of the user's personal site, which they named as the reference, and rebuilt from it as plain HTML and CSS: a sticky top bar with an uppercase wordmark and section links, a two-column hero with a line-drawn hearth mark in place of a photo, the philosophy, and an outlined email button; three white app cards with line icons; a Support section; a light footer band; a faint concentric-ring line drawing behind the hero. White ground, slate greys, one navy accent, a system sans typeface (Inter where installed) so the page still makes no outside requests. Light only, matching the reference; the earlier warm palette and dark mode are gone.
- A skip link, a visible focus ring, reduced-motion handling, and tap targets of at least 39px.

### Checks

- Headless Chromium at 1280, 768 and 375 wide (scratch script `hw-check.js`): no horizontal overflow, no console errors, only the page's own host requested, headings H1 > H2 > H3 in order, one each of header, nav, main and footer, the skip link first in the Tab order. Contrast of every text color at least 6.9 to 1. All ten outbound links answer 200.


## 2026-11-03, The home page goes live

### Changes

- First version of the page: `index.html`, `style.css`, `favicon.svg`, `404.html`, `CNAME`, `.nojekyll`, `README.md`. The house style is the Flip Wits site's (same palette, light and dark), widened to three app cards on a desktop and one column on a phone.
- Content: the headline "Wholesome games for families and classrooms."; the philosophy in the user's words (wholesome games, mindful focus, playing with peers, built with intention, age-appropriate, no ads, nothing addictive, progress not the point); one description and link per app, taken from each app's own page; a Support section and footer with ajm@hearthandwit.com. The page never names the personal site. It is the App Store support and marketing page for the Times Tables Games app.
- Hosting: GitHub Pages, legacy build from `main`, custom domain hearthandwit.com, HTTPS enforced.
- DNS at Squarespace, changed by the user: the "Squarespace defaults" group (four apex A records, the `www` CNAME, and an HTTPS record hinting Squarespace's addresses) deleted as a whole, since it cannot be edited; four apex A records to GitHub Pages and a `www` CNAME to amceachin-code.github.io added. The MX, SPF, and DKIM records and the three app CNAMEs were outside that group and are unchanged, confirmed from Squarespace's own nameservers before and after.

### Decisions

- GitHub Pages rather than Squarespace (the user, 2026-11-03): the apex showed only Squarespace's parking page, a Squarespace site would cost a plan and be edited by hand, and the three apps already serve from GitHub Pages in the same style.
- The philosophy's claims are limited to what the apps' own pages and privacy policies say; "free" is left out of the general text because the App Store apps' pricing is not stated anywhere.

### Checks

- Phone (375px) and desktop widths, light and dark, no horizontal overflow; contrast of every text color on every background at least 5.6 to 1; landmarks and heading order; every outbound link answers 200.

### Next steps

- Optional: verify hearthandwit.com for the GitHub account (Settings, Pages, Verified domains; one TXT record), so no other account can claim a subdomain whose CNAME still points at GitHub.
- Add an App Store badge for Times Tables Games when the app is listed.
