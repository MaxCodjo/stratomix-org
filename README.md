# stratomix.org

Static site for **Stratomix**, rebuilt from masterstrategos.com (GoDaddy Website Builder) as plain HTML/CSS. No build step, no dependencies.

| Path | Page |
|---|---|
| `/` | Home |
| `/about/` | About |
| `/blog/` | Blog index + 3 posts |
| `/contact/` | Contact |
| `/privacy-policy/` | Privacy notice |

- `_archive/masterstrategos.com/` holds raw HTML snapshots of the original site (2026-09-13), the original logo, and each post's extracted body. GitHub Pages' Jekyll build skips `_`-prefixed folders, so it is never served.
- Contact and subscribe forms open the visitor's mail app (`mailto:`). Add a form backend (Formspree, Buttondown) when volume warrants it.
- Not carried over: Getty stock photos (licensed to the GoDaddy site only), the empty Products page, GoDaddy accounts/bookings/orders.

## Preview

```bash
python3 -m http.server 8765
```

## Deploy (GitHub Pages)

1. Settings → Pages → Deploy from branch `main`, folder `/`. `CNAME` already sets `stratomix.org`.
2. At GoDaddy DNS for stratomix.org, replace the parked A records with GitHub's: `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`, plus `CNAME www → maxcodjo.github.io`.
3. Once the certificate issues, tick "Enforce HTTPS".
