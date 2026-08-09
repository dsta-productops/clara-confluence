# CLARA — Confluence

CLARA for programmes whose knowledge base lives in **Confluence**.

This repo is a thin platform build. All of CLARA's shared logic — her persona,
the 12 artefact briefs, and the Knowledge Base path/cascade policy — lives in
[`clara`](https://github.com/dsta-productops/clara), vendored here
under [`core/`](core/) via `git subtree`. Only the Confluence-specific filing
mechanics (`core/platform/confluence/`) differ from the Plane build.

## Build

```bash
pnpm install
pnpm build          # → dist/  (Confluence distribution)
```

Emits `dist/SKILL.md`, `dist/system-prompt.md`, and `dist/portal/*.mdx`.

## Updating the shared core

```bash
pnpm core:pull      # git subtree pull from dsta-productops/clara
```

Never edit `core/` here for shared behaviour — make the change in
[`clara`](https://github.com/dsta-productops/clara) so the Plane build inherits
it too. Confluence-only filing mechanics live in `core/platform/confluence/`.

See [`core/DEPLOYMENT.md`](core/DEPLOYMENT.md) for install guidance.
