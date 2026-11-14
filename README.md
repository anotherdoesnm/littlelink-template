# littlelink-template

A link-in-bio page where this repository holds **only configuration**. The build is
done by [`anotherdoesnm/action-littlelink`](https://github.com/anotherdoesnm/action-littlelink),
which pulls the upstream LittleLink styles at a pinned commit and renders one
self-contained HTML file.

## Quick start

1. **Use this template** to create your own repository.
2. Edit `site.json` (name, subtitle, footer) and `links.json` (the links).
3. Drop a square `assets/avatar.png`.
4. Settings → Pages → Source: **GitHub Actions**.
5. Push to `main` — a minute later the page is at `https://<user>.github.io/<repo>/`.

## Adding your own icon

```
assets/icons/myservice.svg     ← any SVG; a 0 0 24 24 viewBox works best
```

```json
{ "label": "My service", "url": "https://example.org",
  "brand": "myservice", "icon": "myservice", "color": "#123456" }
```

`icon` is the file name without `.svg`. If `brand` has no rule in the upstream
`brands.css` files and none in the action's `local.css`, the renderer takes `color`
from the config and derives a readable text colour. That is exactly how the
"My service" entry in `links.json` works.

If an icon was not picked up, the build log says `icon "…" missing — using a letter
badge` and the page shows a letter in a circle instead of the image.

## What you may change

| file | editable |
|---|---|
| `site.json`, `links.json` | yes — this is the content |
| `assets/icons/*.svg`, `assets/avatar.png` | yes |
| `.github/workflows/build.yml` | usually not |
| layout and button styling | lives in the action repository, not here |
