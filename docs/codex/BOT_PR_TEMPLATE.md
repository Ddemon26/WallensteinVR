## Summary

* **Docs‑Only PR** – updates Markdown or GitHub Actions *only*; no application source files were
  touched.
* Describe pages added/modified and any changes to `docs/index.md`, navigation, or changelog.

## Validation

1. Rendered docs locally (`npm run docs:serve` or equivalent) and verified output.
2. Ran workflow tests (`act`, `npm test-docs`, etc.) and ensured they pass.

## Checklist

* [ ] I confirmed no source code outside `/docs` or `.github/workflows` was modified.
* [ ] Docs build cleanly without warnings.
* [ ] Workflows pass in a dry‑run and on CI.
