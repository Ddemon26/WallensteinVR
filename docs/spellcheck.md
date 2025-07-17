# Spell Check

This project uses a GitHub Actions workflow to catch spelling mistakes in documentation. The workflow runs `codespell` on every pull request that touches files under `/docs`.

To run the check locally:

```sh
pip install codespell
codespell docs/
```

