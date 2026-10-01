# EXIT Connect website (exitconnect.me)

Static HTML site for EXIT Connect. No build step, database or server code.

## Layout

| Path | What it is |
| --- | --- |
| `site/` | The website. Upload the contents of this folder to the host root so `index.html` is at the top level. |
| `docs/EXIT Connect Website Handoff.pdf` | Handoff notes: hosting steps, lead forms, SEO, guides, brand rules, open items. |
| `_Archive/` | The first version of the site (single page, August 2026). Not deployed. |
| `DECISIONS.md` | Log of choices made among real alternatives. |

## Deploying

The host is not chosen yet. On any static host, set the publish directory to `site`
(or upload the contents of `site/`). Then follow "Connecting exitconnect.me" in the handoff PDF.

## Preview locally

```sh
cd site && python3 -m http.server 8000
```

Then open http://localhost:8000.
