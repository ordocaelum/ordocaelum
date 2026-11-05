# Asset Studio: Stylized 3D Asset Business

Working folder for a game-asset business modeled on how Synty Studios works.
This folder is **staged here for now** and is meant to move into its own private
repository (see "Moving to a private repo" below).

| File | What it covers |
|---|---|
| [`01-business-blueprint.md`](01-business-blueprint.md) | How Synty's business works, what to copy, what to avoid, revenue model, roadmap |
| [`art-direction/02-style-options.md`](art-direction/02-style-options.md) | Five candidate art styles, scored |
| [`art-direction/03-style-bible.md`](art-direction/03-style-bible.md) | The recommended style, written as production rules |
| [`04-first-pack-plan.md`](04-first-pack-plan.md) | Scope and checklist for pack #1 |

## Status

- [ ] Original "Replication Blueprint" (Google share link) merged in. It could not be fetched from the build environment, so paste its contents into `00-source-blueprint.md`.
- [ ] Art style locked (recommendation: **Option C, "Gilded Facet"**)
- [ ] Moved into its own private repo

## Moving to a private repo

1. On github.com: **New repository → Private**, e.g. `asset-studio`.
2. `git subtree split --prefix=asset-studio -b asset-studio-export`
3. `git push git@github.com:<you>/asset-studio.git asset-studio-export:main`
