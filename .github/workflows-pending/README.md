# Pending workflow — GitHub Pages deploy

`pages.yml` here deploys the `docs/` landing page to GitHub Pages.

It lives in `workflows-pending/` (not `workflows/`) because the token used to push this repo
didn't carry the `workflow` scope, and GitHub blocks adding workflow files without it.

## To activate it (one step)

```bash
mkdir -p .github/workflows
git mv .github/workflows-pending/pages.yml .github/workflows/pages.yml
git commit -m "Enable GitHub Pages deploy workflow"
git push
```

Push that from a client whose token has the **Workflows** permission (fine-grained PAT) or
the **workflow** scope (classic PAT). Then in the repo: **Settings → Pages → Build and
deployment → Source: GitHub Actions**. The landing page will publish at
`https://storitellah.github.io/zineit/`.

Alternatively, without any workflow at all: **Settings → Pages → Source: Deploy from a
branch → `main` / `docs`** publishes the same folder directly.
