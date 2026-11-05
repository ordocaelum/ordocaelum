# Business Blueprint: Replicating the Synty Model

> Figures marked *(est.)* are approximate public information or industry estimates.
> Check them before you rely on them for financial planning.

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
- Themed packs, plus cheaper "mini" packs that work as entry products.
- Publishing on several marketplaces, plus your own store to own the customer relationship.
- Demo scenes and screenshots that sell the fantasy of a finished game.

**Don't copy (legal and positioning):**
- Synty's exact look: flat-shaded POLYGON proportions and their palette texture.
- Their pack names, themes in the same order, or any of their meshes or textures.
- Competing head-on in their strongest genres (generic fantasy town, modern city, sci-fi base) at launch.

**Positioning:** pick a **distinct style + an underserved niche** so buyers who already
own Synty still have a reason to buy from you. See `art-direction/`.

## 3. Revenue model

| Stream | Phase | Notes |
|---|---|---|
| Themed packs ($40–$90 list) | 1 | Main product; 300–800 assets each |
| Mini packs ($10–$25) | 1 | Entry product, sale bait, tests demand for a niche |
| Bundles (marketplace and Humble-style) | 2 | Volume and new customers |
| Own storefront (itch.io → own site) | 2 | Better margin, email list |
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
| 0: Foundation | Weeks 1–3 | Lock the art style, write the style bible, build the palette atlas, base character rig, export scripts |
| 1: Proof | Weeks 4–12 | Ship 1 mini pack + 1 full themed pack on 2 marketplaces |
| 2: Catalogue | Months 4–12 | 3–5 more packs in the same style; packs that build on each other; own store and email list |
| 3: Ecosystem | Year 2 | Bundles, subscription pass, character customizer, community showcase |

## 6. Key risks

| Risk | Mitigation |
|---|---|
| Looks like a Synty clone | Distinct shape language and shader; see the style bible |
| Marketplace saturation in low-poly | Niche-first themes; strong demo scenes |
| Burnout from oversized packs | Mini pack first; strict asset lists |
| Style drift as the catalogue grows | Style bible + reference "golden" assets + QA checklist |
| Engine version churn | Packaging scripts; test every pack on the current LTS releases |
