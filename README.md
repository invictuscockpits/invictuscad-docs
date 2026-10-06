# InvictusCAD documentation

Source for [docs.invictuscad.com](https://docs.invictuscad.com): MkDocs with the Material theme,
the same setup as docs.invictuscockpits.com.

```bash
pip install -r requirements.txt
mkdocs serve        # live preview at http://127.0.0.1:8000
mkdocs build --strict
```

Pushing to `main` publishes through GitHub Pages (`.github/workflows/deploy.yml`). One-time setup:
in the repo's Settings > Pages, set Source to "GitHub Actions", and add a DNS `CNAME` record for
`docs` pointing at `invictuscockpits.github.io`. `docs/CNAME` holds the custom domain.
