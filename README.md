# IPTV Utomlands – Static SEO Site (Cloudflare Pages ready)

New content cluster targeting **"IPTV utomlands"** for https://iptvflick.com/ – pillar + 4 satellites,
built as **pure static HTML** (no build step) so Cloudflare Pages serves it directly.

## 📁 Structure

```
.
├── index.html                              # Homepage (pillar card + 4 satellite cards)
├── blog/
│   ├── iptv-utomlands-komplett-guide/      # ⭐ PILLAR (~3000 ord)
│   ├── svenska-kanaler-utomlands/          # Satellite (1500–1800 ord)
│   ├── iptv-vpn-utomlands/                 # Satellite (1500–1800 ord)
│   ├── iptv-pa-resande-fot/                # Satellite (1500–1800 ord)
│   └── iptv-for-expats/                    # Satellite (1500–1800 ord)
├── assets/css/style.css
├── sitemap.xml
├── robots.txt
├── 404.html
└── _headers                                # Cloudflare headers (security + caching)
```

## 🚀 Deploy to Cloudflare Pages (5 min)

1. Go to **https://dash.cloudflare.com → Workers & Pages → Create → Pages → Connect to Git**.
2. Authorize GitHub and select the repo containing this folder (or a new repo with these files at root).
3. **Build settings:**
   - **Framework preset:** *None* (or "Static HTML")
   - **Build command:** leave **empty**
   - **Build output directory:** `/` (root) — or the folder name if the files aren't at repo root
4. Click **Save and Deploy**. Live in ~1 minute at `https://<project>.pages.dev/`.

### Custom domain (recommended)
1. In the Pages project → **Custom domains** → **Set up a custom domain**.
2. Add `iptvflick.com` (or a subdomain like `blog.iptvflick.com`).
3. Cloudflare shows the DNS records to add (CNAME `@` → `*.pages.dev` or `A` records) – add them in your DNS provider (ideally Cloudflare DNS).
4. HTTPS is automatic.

## 🔗 Internal linking (wired)

| Link | Present |
|---|---|
| Pillar → all 4 satellites | ✅ |
| Every satellite → pillar | ✅ (intro + summary + footer) |
| Satellites cross-link 1–2 posts | ✅ |
| iptvflick.com recommendations | ✅ 2–4× per page |

## ✅ SEO per page

- Focus keyword in `<title>`, H1, meta description, first 100 words
- Canonical URL, robots meta `index, follow`, FAQ blocks (H3 Q&A)
- Citability block (`<section class="citability">`) for AI search engines
- External links: VLC, iptvflick.com

## 📝 Notes

- `sitemap.xml` currently uses `https://iptvflick.com/...` URLs – update to your actual
  domain/pages.dev URL after first deploy (or before if you already know it).
- All internal links are **relative** (`../`, `index.html`) so the site works from any subpath
  (pages.dev URL, custom domain, or local `file://` preview).
