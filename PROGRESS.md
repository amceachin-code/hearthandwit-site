# Progress

A dated log of the work, newest first.

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
