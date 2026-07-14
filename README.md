# toshihoo.com

The portfolio site of Toshi Anders Hoo, rebuilt as a plain static site from the
WordPress export of the original toshihoo.com. No CMS, no build step, no
dependencies: just HTML and one stylesheet.

All text, page structure, video embeds and image references come directly from
the WordPress export (`toshiandershoo.WordPress.20260714.xml`). Original URL
paths are preserved so existing links keep working.

| Path | Page |
| --- | --- |
| `/` | Home — full-bleed photo statements ("Seeking improbable moments of wonder") |
| `/work/` | Work overview (Production / Consulting / Art) |
| `/production/` | Production projects (Kepler, FireEye, Bella Gaia, Earth Portal, …) |
| `/consulting/` | Consulting services (Kurzweil, Project TimeLab, Museum of the Future, …) |
| `/artwork/` | Art projects (Evolution of Fire, Passages, Water Double, …) |
| `/blog/` | Blog index (8 published posts, each at its original slug, e.g. `/evolution-of-a-card/`) |
| `/contact/` | Contact |

## Editing

Every page is a standalone `index.html` in its folder. Shared styles live in
`css/style.css`. Edit the HTML, reload the browser — that's the whole workflow.

Preview locally with any static server:

```sh
python3 -m http.server 8000
# open http://localhost:8000
```

All internal links are **relative**, so the site works at a domain root
(toshihoo.com) and under a subpath (GitHub Pages project site) alike.

## Media

Images currently hotlink to the original server
(`toshihoo.com/wp-content/uploads/…`). `media-manifest.json` lists every
referenced file. **Before canceling Bluehost hosting**, download
`wp-content/uploads`, commit the needed files under `images/`, and rewrite the
URLs (a find/replace from the manifest). Until then the site depends on the
old host staying up. Video embeds are Vimeo/YouTube and are independent of
Bluehost.

## Deploying

Works on GitHub Pages (already live) and Vercel (`vercel.json` keeps
WordPress-style trailing slashes) — no build command, repo root as output.
