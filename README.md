# RedLight Studio Kit docs (MkDocs site)

The RedLight Studio Kit manual.

## Preview locally

```bash
pip install -r docs/requirements.txt
mkdocs serve            # http://127.0.0.1:8000
```

## Before first deploy

1. Create the public repo `redengineanimation/redlight-studio-kit` and push
   this folder to it (markdown and images only; the add-on source stays out).
2. Check `site_url` and `repo_url` in `mkdocs.yml`.
3. Push to `main`/`master`. `.github/workflows/docs.yml` builds with `mike`
   and publishes to the `gh-pages` branch.
4. In the GitHub repo: **Settings > Pages > Source = Deploy from a branch >
   gh-pages**.

## Manual deploy

```bash
mike deploy --push --update-aliases latest
mike set-default --push latest
```

## Notes

- `kit-list.md` is generated from the add-on's kit JSON by
  `tools/build_kit_list.py` in the product repo. Regenerate it when kits
  change.
- Screenshots come from the product repo's `tools/capture_ui.py`.
