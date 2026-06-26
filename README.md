# Joe's Farm Meat Market — website

The website for Joe's Farm Meat Market (Leadmon's Farm Meat Market) in
Hurricane, West Virginia. A single, static page: hours, what's sold
(beef and pork), the master-butcher story, tap-to-call, and directions.

- **Live site:** https://joesfarmmeatmarket.com
- **GitHub Pages URL:** https://cmleadmon.github.io/Joe-s-Farm-Meat-Market/

## What's in here

```
index.html    the whole site (HTML + CSS inline, no build step)
Joe.png       the newspaper clipping shown on the page
CNAME         the custom domain, read by GitHub Pages
.nojekyll     tells GitHub Pages to skip Jekyll processing
```

It's plain HTML and CSS. There's nothing to compile or install — open
`index.html` in a browser and it works. Fonts (Bevan, Courier Prime)
load from Google Fonts, with system fallbacks if you're offline.

## Preview it locally

From this folder:

```bash
python3 -m http.server 8000
```

Then open <http://localhost:8000/>. Press `Ctrl-C` to stop.

To view on a phone on the same Wi-Fi, bind to all interfaces and visit
`http://<this-computer's-IP>:8000/`:

```bash
python3 -m http.server 8000 --bind 0.0.0.0
```

## Make a change

1. Edit `index.html` (and/or swap `Joe.png`).
2. Commit and push:
   ```bash
   git add -A
   git commit -m "Describe the change"
   git push
   ```
3. GitHub Pages redeploys automatically — live in about 30 seconds.

## How it's deployed

Hosted free on **GitHub Pages**, served from the `master` branch root.

**One-time setup (already partly done):**

1. **Repo → Settings → Pages → Build and deployment**
   - Source: *Deploy from a branch*
   - Branch: `master`, folder `/ (root)` → **Save**
2. **DNS** at the domain registrar:
   - Apex `@` — four `A` records:
     ```
     185.199.108.153
     185.199.109.153
     185.199.110.153
     185.199.111.153
     ```
   - `www` — one `CNAME` → `cmleadmon.github.io`
3. Back in **Settings → Pages**, once DNS propagates, tick **Enforce HTTPS**.

The `CNAME` file in this repo is what binds the site to
`joesfarmmeatmarket.com` — don't delete it.

## Shop details (keep these current)

- **Address:** 813 Hurricane Creek Rd, Hurricane, WV 25526
- **Phone:** (304) 562-6291
- **Hours:** Mon–Wed 8–5 · Thu 8–4 · Fri 8–5 · Sat & Sun closed
- **Since:** 1973

If any of these change, update them in `index.html` (hours live in the
`.hours` section; phone appears in the `tel:` link and the call button).
