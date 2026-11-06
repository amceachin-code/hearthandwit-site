# hearthandwit-site

The home page of Hearth & Wit, served by GitHub Pages at https://hearthandwit.com. Plain HTML, one stylesheet, and one font file, with no build step and no outside requests.

The page gives the philosophy behind the apps, one short description and link for each, and the support address, so it also serves as the App Store support and marketing page. Its look comes from a Claude design canvas (desktop and phone artboards), rebuilt here by hand so the page needs no build step and makes no outside requests.

The apps themselves live in their own repositories and subdomains:

- Times Tables Games: https://timestables.hearthandwit.com/
- Printable worksheets: https://worksheets.hearthandwit.com/
- Flip Wits: https://flipwits.hearthandwit.com/

## DNS

The domain's DNS is at Squarespace. The apex has four A records pointing at GitHub Pages and `www` is a CNAME to `amceachin-code.github.io`; the three app subdomains are CNAMEs to the same host. The MX, SPF, and DKIM records carry the company email and must stay as they are.

## The logo

The logo is four rounded tiles: a flame for the hearth, a times sign for math, a die showing five for games, and a brain for thinking. The brain is a side view in cream lines, with interlocking folds and a ring of short "idea" rays around it. The name sits beside it in rounded lowercase lettering with an ember-colored ampersand. The design came from a Claude design canvas (https://claude.ai/artifact/UZc7dp4b7V5o7L8tVmPri6, direction G, "Game tiles").

- `logo.svg` is the full mark. It is used in the top bar of both pages and in the hero.
- `favicon.svg` is a simpler version of the same tiles for a browser tab: a solid cream brain with one groove and fewer, thicker rays, a heavier times sign and pips. The folds of the full brain turn to noise at tab size.
- `fonts/fredoka-600-latin.woff2` is the lettering font, Fredoka, in one weight and the latin subset. `fonts/OFL.txt` is its SIL Open Font License. The font is served from the site itself, so the page still makes no outside requests. Only the name in the top bar (`.brand`) and the hero heading (`.wordmark`) use it.

The name is written "Hearth & Wit" in the markup and shown lowercase by CSS, so screen readers and copied text keep the proper name.

## Changing the stylesheet

GitHub Pages lets browsers cache files for ten minutes, so a page change and a stylesheet change can arrive apart. When `style.css`, `favicon.svg`, or `logo.svg` changes, bump the `?v=` tag everywhere that file is linked in `index.html` and `404.html` so both pages load the new file at once. `logo.svg` is linked twice in `index.html`, in the top bar and in the hero.

## Checking a change

Open `index.html` in a browser, or serve the folder with `python3 -m http.server`. Every link on the page should answer 200:

```
grep -o 'href="https://[^"]*"' index.html | cut -d'"' -f2 | sort -u | xargs -I{} curl -s -o /dev/null -w "%{http_code} {}\n" {}
```
