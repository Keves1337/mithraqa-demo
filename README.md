# MITHRA live demo

Single static page: `index.html`, styled like mithraqa.com. It runs a **real passive scan** through the
`mithra-lite-scan` Cloudflare Worker (source: `portfolio/scan-worker`): one GET of the page plus one `http://` probe,
16 checks, 3 scans per visitor per day, public domains only. Top 3 findings are shown in full; the rest are locked.

- Publish at /demo on the site by copying `index.html` to `mithraqa-site/demo/index.html`.
- The scan Worker must list `https://mithraqa.com` in `ALLOWED_ORIGINS` (scan-worker/wrangler.toml), then redeploy it.
- Local: run the `scan-api` and `mithraqa-site` entries in `.claude/launch.json`, open http://localhost:5510/demo/
- UI without the API: http://localhost:5510/demo/?mock=1 (mock only works on localhost).
