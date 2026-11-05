# Style Bible: "Gilded Facet" (draft v0.1)

> One sentence: **Chunky mythic shapes, bevelled facets, a toon-lit jewel palette, and a touch of gold.**

## 1. Pillars

1. **Silhouette first.** Every asset reads as a black shape at 64 px.
2. **Facets with a bevel.** Hard planar faces, but every outer edge gets a narrow bevel that catches a highlight. This is the main visual difference from flat low-poly.
3. **Exaggerated proportions.** Tops are wider than bases, tall things lean or taper, ornaments are oversized. Roughly 15–25% stylization away from realism.
4. **Jewel and gold.** Deep saturated base colours. Gold/brass is the only "metal", used sparingly as an accent (≤10% of the surface).
5. **Celestial motifs.** Stars, crescents, orbits, sigils and halos appear as trims and decals in every theme, so even a "tavern" pack feels like part of the same world.

## 2. Shape language

| Element | Rule |
|---|---|
| Primary forms | Tapered boxes, faceted cylinders (6–12 sides), wedges |
| Bevels | Outer edges get a single-segment bevel of ~2–4% of the object's size; inner edges stay hard |
| Curves | Faceted, never smooth; arches use 6–10 segments |
| Ornament | Built from geometry, not texture; chunky, few parts |
| Wear | Only through shape (chips, tilted stones). No grunge textures |

## 3. Colour and texturing

- **One master atlas**: 1024×1024 PNG made up of swatch blocks with a vertical light-to-dark gradient in each block (8 hue families × 8 values), plus a **gold strip** and an **emissive strip**.
- UVs snap to swatches. No unique textures except hero props (≤5% of a pack).
- **Base palette families:** Midnight Blue, Royal Violet, Garnet, Verdigris, Ivory Stone, Umber Wood, Ash Grey, Starlight Gold. (Exact hex values come from the concept phase. Keep everything WCAG-agnostic, but test it under day/dusk/night lighting.)
- **Variants:** recolour by swapping the atlas (e.g. `Atlas_Celestial_A`, `Atlas_Infernal_B`). Never by editing UVs.

## 4. Shading (sold as part of the pack)

- **Toon ramp**: 3-step diffuse ramp, soft terminator.
- **Rim light**: thin, tinted by the sky colour.
- **Bevel highlight**: picked up naturally by the rim/specular, or by a baked vertex-colour edge mask.
- **Height/distance gradient fog**: the signature mood, with deep blue to violet falloff.
- Ship it as: Unity URP Shader Graph + Built-in fallback, Unreal material instance, Godot shader. **Assets still look correct with a plain lit material**, because the shader adds polish and isn't required.

## 5. Technical specs

| Item | Spec |
|---|---|
| Scale | 1 unit = 1 m; humanoid character ≈ 1.8 m |
| Modular grid | 1 m base; walls 4 m wide × 4 m tall × 0.5 m thick |
| Pivots | Bottom-centre for props; bottom-corner on the grid for modules |
| Poly budgets (tris) | Small prop 50–300 · Medium prop 300–1.5k · Building module 200–1.5k · Hero prop ≤5k · Character ≤6k |
| LODs | LOD0 + LOD1 (~50%) for anything over 1k tris |
| Materials | 1 per asset (the atlas), max 2 with the emissive strip |
| Characters | One shared skeleton, Unity Humanoid + UE Mannequin retarget-ready; modular heads/torsos/legs/accessories |
| Naming | `SM_<Pack>_<Category>_<Name>_<Var>` e.g. `SM_Abbey_Wall_Arch_01`; `SK_` characters; `FX_` effects |
| Export | FBX (Unity/Unreal) + glTF (Godot/web), Y-up handled per engine, scale applied |

## 6. "Golden assets" (build these first as the reference set)

1. A 4 m stone wall module with an arch
2. A lectern with an open star-chart book (hero ornament test)
3. A crescent-moon lantern (emissive + gold test)
4. A robed scholar character (rig + proportion test)
5. A tree (organic faceting test)

Every future asset is compared side by side with these five before it ships.

## 7. Do / Don't

| Do | Don't |
|---|---|
| Exaggerate tapers and lean | Use straight, realistic proportions |
| Bevel outer edges | Leave everything razor-flat (reads as Synty) |
| Use gold as a highlight | Make whole objects metallic |
| Put a celestial motif in every pack | Use photo textures or grunge |
| Test the silhouette at 64 px | Add detail that only shows up close |

## 8. Launch niches (where Synty is thin)

1. **Celestial Abbey / Astronomer's Observatory**: interiors, libraries, orreries, monks. *(Recommended first full pack.)*
2. **Occult Order / Secret Society**: ritual chambers, sigils, cultists.
3. **Sky Islands / Heavenly Ruins**: floating stone, broken halos, angelic statues.
4. **Infernal Counterpart**: the same kits recoloured with `Atlas_Infernal`, a cheap second SKU.
