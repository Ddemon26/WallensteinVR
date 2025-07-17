# Continuous Integration

The project builds with GitHub Actions on every push and pull request. The workflow
installs Zig and system packages, then runs `zig build` and `zig build test`.

Documentation is linted separately by the **Docs Spell Check** workflow.
