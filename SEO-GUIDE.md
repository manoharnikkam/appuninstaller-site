# SEO & Indexing Guide — appuninstaller.store

## Search Console Accounts

### Google Search Console
- URL: https://search.google.com/search-console
- Verification: CNAME record `vdwtj4ojbvzs` → `gv-exas3oeknjhglh.dv.googlehosted.com`
- Sitemap submitted: `https://appuninstaller.store/sitemap.xml`

### Bing Webmaster Tools
- URL: https://www.bing.com/webmasters
- Verification: CNAME record `521863e58ae186dead81aadace352154` → `verify.bing.com`
- Sitemap submitted: `https://appuninstaller.store/sitemap.xml`

---

## IndexNow (Instant Indexing)

IndexNow notifies Bing and Yandex to re-crawl your pages immediately after updates, instead of waiting days/weeks.

**API Key:** `d0acaaf6745745298200bb9ed96dc7fd`
**Key File:** `https://appuninstaller.store/d0acaaf6745745298200bb9ed96dc7fd.txt`

### Ping after site updates

Submit a single page:
```bash
curl "https://api.indexnow.org/indexnow?url=https://appuninstaller.store/&key=d0acaaf6745745298200bb9ed96dc7fd"
```

Submit multiple pages:
```bash
curl -X POST "https://api.indexnow.org/indexnow" \
  -H "Content-Type: application/json" \
  -d '{
    "host": "appuninstaller.store",
    "key": "d0acaaf6745745298200bb9ed96dc7fd",
    "keyLocation": "https://appuninstaller.store/d0acaaf6745745298200bb9ed96dc7fd.txt",
    "urlList": [
      "https://appuninstaller.store/",
      "https://appuninstaller.store/privacy.html",
      "https://appuninstaller.store/terms.html",
      "https://appuninstaller.store/refund.html"
    ]
  }'
```

**Expected response:** HTTP 202 (Accepted)

---

## Sitemap

**File:** `sitemap.xml` in the site root
**URL:** `https://appuninstaller.store/sitemap.xml`

Update `<lastmod>` dates in sitemap.xml whenever you make content changes.

---

## Structured Data (JSON-LD)

The following schemas are embedded in `index.html`:

| Schema | Purpose |
|--------|---------|
| `SoftwareApplication` | Rich results with price, rating, OS in Google |
| `FAQPage` | Expandable FAQ snippets in search results |
| `WebSite` | Sitelinks search box |

Validate at: https://search.google.com/test/rich-results

---

## Checklist After Major Site Updates

1. Update `<lastmod>` in `sitemap.xml`
2. Ping IndexNow (see command above)
3. Check Google Search Console for crawl errors
4. Validate structured data at rich results test
5. Test social sharing preview at https://www.opengraph.xyz/

---

## Launch Pricing

- Base price: **$14.99**
- Launch sale price: **$9.99** (33% off)
- Paddle is set to $9.99 during the promotion
- When ending the sale: update Paddle to $14.99 and remove sale badges from `index.html`
