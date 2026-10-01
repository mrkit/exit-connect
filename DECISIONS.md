# Decisions

Each entry records a choice made among real alternatives: date, what was chosen,
why, and what was rejected. Add an entry in the same commit as the change.
Routine choices with no real alternative do not get entries.

## 2026-09-30: Keep the website in `site/`, not at the repo root

**Chosen:** the deployable site lives in `site/`. The repo root holds the README,
this log, `docs/` and `_Archive/`.

**Why:** the handoff PDF already tells whoever hosts it to upload the contents of
`site/`. A separate folder also keeps the handoff PDF and the old site out of the
public upload. Netlify, Cloudflare Pages and Vercel all accept a publish directory.

**Rejected:** moving `site/*` to the root, as the first version was. It works
with GitHub Pages' root option without a workflow, but then `docs/` and `_Archive/`
would be served publicly unless each host is configured to exclude them.

## 2026-09-30: Keep the first site version in `_Archive/` in the repo

**Chosen:** commit the old `index.html`, `favicon.svg` and `images/` as moves into `_Archive/`.

**Why:** git stores the moved files as renames of the same content, so the repo does
not grow, and the old version stays browsable without checking out history.

**Rejected:** deleting them and relying on git history (commit `d9804b6`) alone.
