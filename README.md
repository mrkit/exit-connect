# EXIT Connect website (exitconnect.me)

Static HTML site for EXIT Connect. No build step, database or server code.

## Hosting

Cloudflare Pages, project `exit-connect`, connected to this GitHub repo.
Every push to `master` deploys the repo root to https://exitconnect.me.
Everything committed is publicly served, so keep internal files out of git
(`docs/` is gitignored for that reason).

## Layout

| Path | What it is |
| --- | --- |
| `index.html`, `blog.html`, `guides.html` | Home, blog list and free guides pages |
| `blog/` | The four article pages |
| `img/` | All photos and logos the pages use |
| `sitemap.xml`, `robots.txt` | Search engine files. Add each new article to the sitemap. |
| `404.html` | Page shown for unknown addresses (noindex) |
| `_headers` | Cloudflare Pages headers. Marks `_Archive/` as noindex. |
| `_redirects` | Cloudflare Pages redirects. Sends `/README.md` and `/DECISIONS.md` to the home page. |
| `_Archive/` | The first version of the site (single page, August 2026) |
| `docs/` | Local only, not committed. Holds the handoff PDF. |
| `DECISIONS.md` | Log of choices made among real alternatives |

## Preview locally

Internal links use clean addresses (`/blog`, `/guides`, `/blog/<slug>`) the way
Pages serves them, so preview with Cloudflare's local server, which resolves them
the same way:

```sh
npx wrangler pages dev .
```

Then open the address it prints. A plain `python3 -m http.server` also works for
looking at single pages, but links between pages will not resolve there.
