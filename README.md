# Foglio — Public Site

Static site hosted on GitHub Pages. Contains legal documents and
future ad-related files (e.g. `ads.txt`, `app-ads.txt`) referenced by
the Foglio app and Google Play submission.

## Pages

| Path | Purpose |
|------|---------|
| `/` | Landing page |
| `/privacy-policy.html` | Privacy Policy (for Google Play `Privacy Policy URL`) |
| `/terms-of-service.html` | Terms of Service |
| `/404.html` | Not-found page |

## Local preview

```bash
cd /Users/zhuxiao/StudioProjects/scanviopdf-site
python3 -m http.server 8000
# open http://localhost:8000
```

## Deploy

Any push to `main` will be published by GitHub Pages within ~1 minute.

Enable once in the repo settings:
**Settings → Pages → Source: Deploy from a branch → Branch: `main` / (root)**

`.nojekyll` disables Jekyll processing so files with leading underscores
are served as-is.

## Adding ad files later

Drop `ads.txt` (web) or `app-ads.txt` (Android) at the repo root:

```
google.com, pub-XXXXXXXXXXXXXXXX, DIRECT, f08c47fec0942fa0
```

The URL will then be:
`https://<user>.github.io/<repo>/app-ads.txt`

For AdMob's app-ads.txt requirement, the URL must match the
"Developer URL" configured on the Play Store listing.

## Updating legal docs

Edit `privacy-policy.html` or `terms-of-service.html`, bump the
"Last updated" date at the top, commit, push. GitHub Pages picks it up
automatically.
