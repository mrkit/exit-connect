# Decisions

Each entry records a choice made among real alternatives: date, what was chosen,
why, and what was rejected. Add an entry in the same commit as the change.
Routine choices with no real alternative do not get entries.

## 2026-09-30: Site files at the repo root; handoff PDF not committed

**Chosen:** the website files sit at the repo root. The handoff PDF stays in a
gitignored `docs/` folder.

**Why:** the host turned out to be decided already. Cloudflare Pages project
`exit-connect` deploys this repo's root to exitconnect.me on every push. Commit
`7971bc9` put the site in `site/`, and the live root returned 404 until this
change. Because Pages publishes every committed file, the handoff PDF (internal
notes and private links) is kept out of git.

**Rejected:** keeping `site/` and changing the Pages build output directory to
`site` in the Cloudflare dashboard. It keeps internal files unpublished, but needs
dashboard access this session did not have, and the site was down in the
meantime. Worth revisiting if more internal files need to live in the repo.

## 2026-09-30: Keep the first site version in `_Archive/` in the repo

**Chosen:** commit the old `index.html`, `favicon.svg` and `images/` as moves into
`_Archive/`, with a `noindex` header from `_headers`.

**Why:** git stores the moved files as renames of the same content, so the repo does
not grow, and the old version stays browsable without checking out history. It was
already public, so serving it at `/_Archive/` exposes nothing new.

**Rejected:** deleting them and relying on git history (commit `d9804b6`) alone.
