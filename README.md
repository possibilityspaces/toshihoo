# toshihoo.com

Rebuild of [toshihoo.com](https://toshihoo.com) — the portfolio of Toshi Anders
Hoo — as a plain static site. No build step, no framework, no dependencies:
just HTML and one stylesheet.

The previous site was a WordPress install on Bluehost. This rebuild preserves
the original information architecture and URL paths so existing links keep
working:

| Path | Page |
| --- | --- |
| `/` | Home — "Art, work and musings" |
| `/work/` | Work overview + research & prototyping projects |
| `/production/` | Immersive experiences, film and live events |
| `/consulting/` | Consulting services and advisory clients |
| `/artwork/` | Art practice |
| `/contact/` | Contact links |

## Editing

Every page is a standalone `index.html` in its folder. Shared styles live in
`css/style.css` (dark/light via `prefers-color-scheme`). Edit the HTML, reload
the browser — that's the whole workflow.

Preview locally with any static server, e.g.:

```sh
python3 -m http.server 8000
# open http://localhost:8000
```

## Deploying

Designed for Vercel (`vercel.json` keeps WordPress-style trailing slashes),
but works on any static host including GitHub Pages. On Vercel: import this
repo, no build command, output directory is the repo root.

## Still to restore

The original site's media (video embeds, image galleries, blog posts such as
"Evolution of a Business Card" and the Lytro posts) could not be recovered
from the live site, which is currently suspended, or from web archives. Once
the Bluehost/WordPress backup (export + `wp-content/uploads`) is in hand:

- [ ] Add images/video to `/production/` and `/artwork/` (placeholders are marked in the HTML)
- [ ] Restore blog posts and the `/category/ai/` + `/category/fulldome/` archives if wanted
- [ ] Verify text against the WordPress export and correct any drift
