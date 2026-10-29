# ByteBoost Cybertraining website

Static site for ByteBoost 2.0, served by GitHub Pages at https://byteboost-tech.org.

Supported by NSF awards OAC-2519578, OAC-2519579, and OAC-2519580.

## Structure

```
index.html          single-page site
styles.css          brand styles
CNAME               custom domain for GitHub Pages (byteboost-tech.org)
.nojekyll           serve files as-is, no Jekyll build
         logo, favicon, platform logos, participant photos
```

## Brand palette

Sampled from the ByteBoost Cybertraining logo.

| Token       | Hex       | Use                                   |
|-------------|-----------|---------------------------------------|
| `--wine`    | `#5E0F26` | Wordmark, headings, primary buttons   |
| `--oxblood` | `#3A0410` | Footer, darkest hero tone             |
| `--garnet`  | `#8A1A33` | Links, hero highlight                 |
| `--crimson` | `#C43139` | Accents, hover, bullets, focus rings  |
| `--cream`   | `#F2E6D2` | Accents on dark backgrounds           |
| `--stone`   | `#BEB3B1` | Neutral, matches the logo divider     |

Typography: Saira (display, uppercase with letter spacing to echo the wordmark) and Inter (body).
Motif: hexagons, taken from the logo sphere.

## Images still needed

Add these next to index.html (pages hide missing images automatically):

- `nsf-logo.png` (official NSF logo from nsf.gov/policies/logo, shown in the header left of the ByteBoost logo)
- `ACES.png`
- `Neocortex.png`
- `Ookami.png`
- `AtharvaJoshi.jpeg` (confirm consent to reuse)

## Deploy on GitHub Pages

1. Create a repository (for example `byteboost-site`) under your account or an org.
2. Push this folder:
   ```
   git remote add origin git@github.com:<owner>/byteboost-site.git
   git push -u origin main
   ```
3. In the repo: Settings > Pages > Build and deployment > Source: "Deploy from a branch", Branch: `main`, folder `/ (root)`.
4. Under Custom domain, enter `byteboost-tech.org` and save (the CNAME file already sets this).
5. At your domain registrar, add DNS records:
   - Apex `byteboost-tech.org`, type A: `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - Apex, type AAAA (optional): `2606:50c0:8000::153`, `2606:50c0:8001::153`, `2606:50c0:8002::153`, `2606:50c0:8003::153`
   - `www`, type CNAME: `<owner>.github.io`
6. Recommended: verify the domain for your account or org (Settings > Pages > Verified domains) to prevent takeover.
7. Once DNS resolves (minutes to a few hours), check "Enforce HTTPS" in Settings > Pages.

## Editing

Edit `index.html` directly and push to `main`; GitHub Pages redeploys in about a minute.
