# site-assets

Static asset host for [Academic_Website](https://github.com/Schuetzen/Academic_Website), served via the **jsDelivr CDN**.

## Why

Offload large images / PDFs / videos out of the main Hugo repo so:
- Netlify bandwidth is only spent on HTML + small thumbnails
- Build time is faster (no giant images to process)
- Global CDN (jsDelivr) caches files edge-close to every visitor for free

## CDN URL pattern

```
https://cdn.jsdelivr.net/gh/Schuetzen/site-assets@main/<folder>/<file>
```

Pin to a specific commit for long-term stability:
```
https://cdn.jsdelivr.net/gh/Schuetzen/site-assets@<sha>/<folder>/<file>
```

## Folder layout

| Folder | For |
|---|---|
| `hero/` | site background / hero images |
| `pdf/`  | publication PDFs, posters |
| `video/` | project demo videos |
| `img/`  | general-purpose images (create as needed) |

## Add a new file

```bash
cd /path/to/site-assets
cp /source/path/your-file.jpg img/
git add . && git commit -m "add: your-file.jpg" && git push
```

CDN goes live in ~1 minute. URL:
`https://cdn.jsdelivr.net/gh/Schuetzen/site-assets@main/img/your-file.jpg`

## Limits

- Single file < 20 MB (jsDelivr hard cap)
- Repo < 1 GB (soft)
- Public only (GitHub public repos)
