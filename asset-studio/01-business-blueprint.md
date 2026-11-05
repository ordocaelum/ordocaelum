# Business Blueprint: Replicating the Synty Model

> Built on the source blueprint (`00-source-blueprint.md`). Figures marked *(est.)* are
> approximate public information or industry estimates. Check them before you rely on them for financial planning.

**Source model in one line:** a *"modular, hyper-standardized micro-transaction"* B2B model.
Cheap, mass-market building blocks sold to hundreds of thousands of indie developers instead of
custom 3D work for a few clients.

**The four pillars (source doc):** the "Lego" ecosystem · engine-ready, no setup work ·
huge thematic coverage · loss-leader pricing plus bundles.

## 1. How Synty works

Synty Studios (Auckland, NZ) built a large indie-asset business around a single,
consistent idea: **low-poly, flat-shaded, modular 3D packs that all look like they
belong together.**

| Lever | What Synty does | Why it works |
|---|---|---|
| **One shared look** | Every POLYGON pack uses the same proportions, scale and texture approach | Buyers can mix packs freely, so each new pack makes the earlier ones more valuable |
| **Palette-atlas texturing** | Most meshes are UV-mapped onto a small gradient/colour-swatch texture instead of unique textures | Very cheap to make, tiny file size, one material for a whole scene, easy recolouring |
| **Themed, huge packs** | "Fantasy Kingdom", "City", "Sci-Fi", "Western"... hundreds to thousands of prefabs, including characters | High perceived value; a solo developer can build a whole game from one pack |
| **Multi-marketplace** | Unity Asset Store, Unreal/Fab, its own store, Humble-style bundles | Reaches buyers wherever they shop; bundles bring in new customers |
| **Sales-calendar pricing** | List prices around $50–$150 *(est.)*, steep discounts during marketplace sales | Most volume comes during sales; list price anchors the value |
| **Ecosystem products** | Character creator tooling (Sidekick), subscription/"pass" access, UI and FX add-ons | Moves from one-off sales toward recurring revenue and lock-in |
| **Community and showcase** | Games built with the packs are promoted heavily | Every shipped game is free marketing |

**The core insight:** Synty doesn't sell models. It sells **a visual standard that
grows over time**. The style guide is the product, and the packs are what you buy into it with.

## 2. What to copy and what not to copy

**Copy (business mechanics):**
- One consistent style across every pack, set out in a written style bible.
- Palette-atlas workflow to keep cost per asset low.
- Modular kits (walls, floors, roofs, props) built on a strict grid.
- **Core pack, then fragment:** one big "Core" pack that's enough to prototype a whole game, then
  hyper-specific **micro-expansions** (e.g. Core Occult → Abbey Crypt add-on → Cult Ritual add-on).
- **Storefront traffic first:** Unity Asset Store and Fab (Epic's store that replaced the Unreal
  Marketplace in 2024). Your own website only after the catalogue exists.
- Demo scenes and screenshots that sell the fantasy of a finished game.

**Don't copy (legal and positioning):**
- Synty's exact look: flat-shaded POLYGON proportions and their palette texture.
- Their pack names, themes in the same order, or any of their meshes or textures.
- Competing head-on in their strongest genres (generic fantasy town, modern city, sci-fi base) at launch.

**Positioning:** the source doc's rule is *don't compete with Synty's low-poly look, because they own
that market.* Copy their mechanics in a different style. **Chosen direction: PS1-era retro
("Ordo PSX") with occult/cosmic-horror themes.** See `art-direction/`.

## 3. Revenue model

| Stream | Phase | Notes |
|---|---|---|
| Core packs ($40–$90 list) | 1 | Main product; enough for a full prototype |
| Micro-expansions ($10–$25) | 1–2 | Hyper-specific add-ons to a core; cheap to make, sold to existing buyers |
| Humble Bundle / Fanatical features | 2 (after 5–10 packs) | Source doc: a single bundle can move **50,000+ copies**, the main cash injection for growth |
| Own storefront (itch.io → own site) | 3 | Better margin, email list; not at launch |
| Subscription / "Studio Pass" | 3 | Only after there's a back catalogue of 8+ packs |
| Custom/outsourced art | any | Cash flow early on; don't let it crowd out pack work |

**Marketplace cuts *(est.)*:** Unity Asset Store ~30%, Fab (Epic) ~12%,
itch.io adjustable (0–30%), own store ~5% payment fees.

**Unit economics target (pack #1):** ~250 production hours. At a $60 list price and
roughly $25 average net per sale (after sale discounts and the platform cut), break-even
is about **10 sales per $250 of hourly cost**. Price your time realistically, then set a sales target.

## 4. Production pipeline

1. **Concept board.** Silhouettes and the palette for the theme, checked against the style bible.
2. **Blockout.** Grid-snapped modules in Blender.
3. **Model.** Follow the style bible's poly budgets and bevel rules.
4. **UV to atlas.** Snap UV islands to swatches. No unique textures except hero assets.
5. **Characters.** One shared base rig/skeleton across all packs (Humanoid / UE Mannequin compatible).
6. **Export.** FBX + glTF, naming convention, pivots, colliders, LODs.
7. **Engine packaging.** Unity (URP + Built-in), Unreal, Godot. One prefab/blueprint per asset.
8. **Demo scene and marketing.** Hero screenshots, a 30–60 s trailer, an overview sheet of every asset.
9. **QA.** Scale check, missing materials, naming, an import test in each engine.

**Tooling:** Blender (modelling, UV, rigging), Substance/Blender for the few hero bakes,
Unity + Unreal + Godot for packaging, Git LFS for source files, a Python batch-export script.

## 5. Roadmap

| Phase | Timeline | Goal |
|---|---|---|
| 0: Foundation | Weeks 1–4 | Style bible, PSX shader kit, texel/atlas standard, shared skeleton, export scripts, 5 golden assets |
| 1: Core | Weeks 5–14 | Ship **Core: Occult Abbey** on the Unity Asset Store + Fab; ship the shader kit standalone as an entry product |
| 2: Fragment | Months 4–9 | 3–5 micro-expansions + a second core pack; reach 5–10 packs |
| 3: Scale | Months 9–18 | Pitch Humble Bundle / Fanatical; own store + email list; subscription pass once the catalogue is 10+ packs |

## 6. Key risks

| Risk | Mitigation |
|---|---|
| Looks like a Synty clone | Different aesthetic altogether (PSX), per the source doc's rule |
| Small PSX creators already exist | Compete on *standardisation and scale* (shared texel density, shader kit, core + expansions), which the small packs lack |
| Burnout from oversized packs | Mini pack first; strict asset lists |
| Style drift as the catalogue grows | Style bible + reference "golden" assets + QA checklist |
| Engine version churn | Packaging scripts; test every pack on the current LTS releases |
