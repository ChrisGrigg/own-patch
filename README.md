# Own Patch — landing page

Static landing page for **ownpatch.co.uk**, exported from the Claude Design project and served with GitHub Pages.

## Publish

```bash
gh repo create ChrisGrigg/own-patch --public --source=. --push
gh api -X POST repos/ChrisGrigg/own-patch/pages -f "source[branch]=main" -f "source[path]=/"
```

Live in a minute or two at https://chrisgrigg.github.io/own-patch/

## Custom domain (optional)

1. `echo ownpatch.co.uk > CNAME && git add CNAME && git commit -m "Add custom domain" && git push`
2. At your DNS provider: `A` records for the apex → 185.199.108.153, 185.199.109.153, 185.199.110.153, 185.199.111.153, and a `CNAME` for `www` → `chrisgrigg.github.io`.
3. Repo → Settings → Pages → tick **Enforce HTTPS** once the certificate is issued.

## Files

- `index.html` — the page (both the Home and Free video audit views)
- `chris-grigg.jpg` — About section photo
- `support.js`, `image-slot.js` — page runtime
- `vendor/` — React 18.3.1 served locally (same files the runtime would fetch from unpkg)
- `_ds/` — design-system styles
- `.nojekyll` — serve files as-is (needed for the `_ds` folder)
