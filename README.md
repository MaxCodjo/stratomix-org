# stratomix.org

Static site for **Stratomix**, rebuilt from masterstrategos.com (GoDaddy Website Builder) as plain HTML/CSS. No build step, no dependencies.

| Path | Page |
|---|---|
| `/` | Home |
| `/about/` | About |
| `/blog/` | Blog index + 3 posts |
| `/contact/` | Contact |
| `/privacy-policy/` | Privacy notice |

- `public/` is the website. Railway (Railpack) detects the `public` folder and serves it with Caddy; nothing else in the repo is served.
- `_archive/masterstrategos.com/` holds raw HTML snapshots of the original site (2026-09-13), the original logo, and each post's extracted body. Not served.
- Contact and subscribe forms open the visitor's mail app (`mailto:`). Add a form backend (Formspree, Buttondown) when volume warrants it.
- Home hero video (`public/assets/hero.mp4`, poster `public/assets/hero.jpg`): "Mountains, Dolomites, Cadini Di Misurina" by ferrisdrone, [Pixabay](https://pixabay.com/videos/mountains-dolomites-137822/), Pixabay Content License (free commercial use, no attribution required). Fade-in/out trimmed and played forward then reversed for a seamless 11.6 s loop; 1080p H.264, no audio, 2 MB.
- Not carried over: Getty stock photos (licensed to the GoDaddy site only), the empty Products page, GoDaddy accounts/bookings/orders.

## Preview

```bash
python3 -m http.server 8765 --directory public
```

## Hosting

- **www.stratomix.org** — Railway service deployed from `main` (auto-deploys on push). GoDaddy DNS: `CNAME www → <service>.up.railway.app` plus Railway's `TXT` verification record.
- **stratomix.org** (apex) — GoDaddy can't CNAME the apex to Railway, so the apex keeps GitHub Pages A records (`185.199.108.153`–`185.199.111.153`) served by [MaxCodjo/stratomix-redirect](https://github.com/MaxCodjo/stratomix-redirect), which redirects to `https://www.stratomix.org`.
- MX records (Google, for max@stratomix.org) stay untouched.
