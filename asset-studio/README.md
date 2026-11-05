# Asset Studio: Stylized 3D Asset Business

Working folder for a game-asset business modeled on how Synty Studios works.
This folder is **staged here for now** and is meant to move into its own private
repository (see "Moving to a private repo" below).

| File | What it covers |
|---|---|
| [`00-source-blueprint.md`](00-source-blueprint.md) | The original Google Doc, imported verbatim |
| [`01-business-blueprint.md`](01-business-blueprint.md) | How Synty's business works, what to copy, what to avoid, revenue model, roadmap |
| [`art-direction/02-style-options.md`](art-direction/02-style-options.md) | Candidate styles scored against the source doc's test |
| [`art-direction/03-style-bible.md`](art-direction/03-style-bible.md) | "Ordo PSX" style bible: production rules |
| [`04-first-pack-plan.md`](04-first-pack-plan.md) | Shader kit + Core pack + micro-expansion plan |

## Status

- [x] Original blueprint merged in (`00-source-blueprint.md`)
- [ ] Art style locked (recommendation: **PS1-era retro, "Ordo PSX"**; Gilded Facet parked as a second line)
- [ ] Moved into its own private repo

## Moving to a private repo

1. On github.com: **New repository → Private**, e.g. `asset-studio`.
2. `git subtree split --prefix=asset-studio -b asset-studio-export`
3. `git push git@github.com:<you>/asset-studio.git asset-studio-export:main`
