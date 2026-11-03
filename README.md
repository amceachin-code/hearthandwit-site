# hearthandwit-site

The home page of Hearth & Wit, served by GitHub Pages at https://hearthandwit.com. Plain HTML and one stylesheet, with no build step and no outside requests.

The page gives the philosophy behind the apps, one short description and link for each, and the support address, so it also serves as the App Store support and marketing page.

The apps themselves live in their own repositories and subdomains:

- Times Tables Games: https://timestables.hearthandwit.com/
- Printable worksheets: https://worksheets.hearthandwit.com/
- Flip Wits: https://flipwits.hearthandwit.com/

## DNS

The domain's DNS is at Squarespace. The apex has four A records pointing at GitHub Pages and `www` is a CNAME to `amceachin-code.github.io`; the three app subdomains are CNAMEs to the same host. The MX, SPF, and DKIM records carry the company email and must stay as they are.

## Checking a change

Open `index.html` in a browser, or serve the folder with `python3 -m http.server`. Every link on the page should answer 200:

```
grep -o 'href="https://[^"]*"' index.html | cut -d'"' -f2 | sort -u | xargs -I{} curl -s -o /dev/null -w "%{http_code} {}\n" {}
```
