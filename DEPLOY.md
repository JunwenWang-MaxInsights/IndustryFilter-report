# Public report (GitHub Pages)

The **repository stays private**. Only the static site under `docs/` is published.

## One-time setup

**Private repo (code):** [JunwenWang-MaxInsights/IndustryFilter](https://github.com/JunwenWang-MaxInsights/IndustryFilter)

**Public report (Free tier):** use a separate public repo — GitHub Free does **not** support Pages on private repos.

1. Public report repo: [JunwenWang-MaxInsights/IndustryFilter-report](https://github.com/JunwenWang-MaxInsights/IndustryFilter-report)
2. After first publish, enable **Settings → Pages → Deploy from branch `main` / `/ (root)`**

**Public URL:** `https://junwenwang-maxinsights.github.io/IndustryFilter-report/`

## Update the report

```bash
# Regenerate from local CSV (data/outputs is not committed)
python3 scripts/build_b16_report.py

git add docs/
git commit -m "Update B/16 evaluation report"
git push
```

## What gets published

| Included | Not included |
|----------|----------------|
| `docs/index.html` (interactive chart + summary) | Source code (private repo) |
| `docs/assets/siglip_b16_5000_dots.png` | Raw CSV in `data/outputs/` |
| episodeIds in hover (for drill-down) | Videos / frames |

## Fallback: separate public repo

If your plan cannot expose Pages from a private repo:

```bash
export PUBLIC_PAGES_REPO=git@github.com:YOUR_ORG/IndustryFilter-report.git
./scripts/publish_pages_public_repo.sh
```

That pushes **only** `docs/` to a **public** empty repo with GitHub Pages enabled on `main`.
