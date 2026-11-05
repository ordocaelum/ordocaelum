# Style Bible: "Ordo PSX" (draft v0.2)

> One sentence: **Late-90s console 3D (chunky geometry, crunchy low-res textures, wobbling vertices, thick fog) applied to occult, gothic and cosmic-horror worlds.**

Every pack for the next five years follows this document. Changes need a version bump.

## 1. Pillars

1. **Authentic, not ironic.** Match what period hardware could actually do (texture sizes, colour depth, fog distances). No modern PBR sneaking in.
2. **One texel density.** Everything in the catalogue shares the same pixels-per-metre, so packs kitbash together (the "Lego" pillar).
3. **Fog is part of the art.** Assets are designed to be read through fog. Silhouettes have to work at 15 m in dark grey.
4. **The shader is the glue.** The included PSX shader kit makes *any* of our assets, and the buyer's own, look consistent.
5. **Dread through restraint.** Desaturated palette, one accent colour per scene (sickly green, votive red or gold leaf).

## 2. Geometry

| Item | Spec |
|---|---|
| Small prop | 50–300 tris |
| Medium prop | 300–500 tris (source-doc cap: **500 per prop**) |
| Hero prop | ≤1,000 tris (≤5% of a pack) |
| Building module | 100–600 tris |
| Character | 600–1,500 tris, single mesh plus swappable heads |
| Shading | Flat or simple smooth groups; detail lives in the texture, not the mesh |
| Scale / grid | 1 unit = 1 m; modular grid 1 m, walls 3 m tall × 2 m wide (tight, claustrophobic corridors) |
| Pivots | Props bottom-centre; modules bottom-corner on grid |

## 3. Textures

- **Texel density: 64 px per metre** for the whole catalogue (hero close-ups may use 128).
- Sizes: 32, 64, 128 or 256 px squares. **Nothing above 256.**
- **Point filtering**, no mipmaps by default (the shader kit has an option for them).
- Colour: painted or photo-sourced, then **quantised to 15-bit colour**, with 4×4 ordered dithering in shadowed areas.
- **Shared atlases** per pack family (e.g. `T_Abbey_Stone_Atlas_256`) so one material covers many props. This is the source doc's "locked texture atlases" rule.
- Baked lighting/AO is painted into the texture, PS1-style (vertex colour for extra tinting).
- Sourcing: hand-painted or from CC0 photo libraries only (Poly Haven/ambientCG style). **Never** textures ripped from games.

## 4. Shader kit (ships with every pack and is the selling point)

| Feature | Default | Toggle |
|---|---|---|
| Vertex snapping (jitter) | On, 160×120 virtual grid | Strength slider |
| Affine texture warping | On | Off / amount |
| Colour quantisation + dither | 15-bit, 4×4 Bayer | Bit depth |
| Distance fog | Linear, ~8–25 m, dark grey/green | Colour, start/end |
| Vertex lighting (Gouraud) | On | Per-pixel fallback |
| Draw-distance cutoff | Off | Distance |
| Post: low-res render target | 320×240 upscale | Resolution |

Targets: **Unity 6 (URP + Built-in), Unreal 5 (material functions + post-process), Godot 4.**
Assets still look acceptable with a standard unlit material, so they never break without the kit.

## 5. Characters and rigging

- Every humanoid maps to **Unity Humanoid (Mecanim)** and **Unreal Manny/Quinn** without retarget tweaks (source-doc requirement).
- One shared skeleton across all packs; modular heads, robes/bodies and hands.
- Low bone count (period-accurate feel), but compatible with the standard skeletons above.
- Animation set per core pack: idle, walk, run, shamble, attack, death, interact, chant.

## 6. Naming and export

- `SM_<Pack>_<Category>_<Name>_<Var>` e.g. `SM_Abbey_Prop_Censer_01`; `SK_` skinned; `T_` textures; `M_` materials.
- FBX (Unity/Unreal) + glTF (Godot), scale applied, one prefab or blueprint per asset, colliders included.

## 7. Palette families

| Family | Use |
|---|---|
| Wet Stone (grey-greens) | Walls, crypts, exteriors |
| Old Wood (umber/black) | Pews, beams, furniture |
| Candle & Rust (ochres) | Light sources, metal |
| Votive Red | Accent: blood, cloth, sigils |
| Gold Leaf | Accent: reliquaries, icons, celestial motifs |
| Cosmic Teal | Accent: otherworldly / "heavens" elements |

## 8. Golden assets (reference set, built first)

1. Stone corridor module with arch and torch sconce
2. Altar with candles and an open grimoire
3. Hooded cultist character (rig + proportion test)
4. Iron gate (alpha-cutout test)
5. Celestial orrery (accent-colour + hero-prop test)

Every new asset is checked side by side against these five, under the shader kit, in fog.

## 9. Do / Don't

| Do | Don't |
|---|---|
| Paint detail into 64–256 px textures | Use normal maps, PBR or 2K textures |
| Design for fog and darkness | Rely on fine detail up close |
| Keep one accent colour per scene | Use saturated rainbow palettes |
| Use the shared texel density | Scale a texture up "because it looks fine" |
| Use CC0 or hand-made sources | Rip or trace from existing games |

---

## Appendix: Gilded Facet (parked second line)

Bevelled faceted low-poly, 3-step toon ramp + rim light, deep jewel palette with gold accents
(≤10% of the surface), celestial motifs, one 1024² swatch atlas. Possible non-horror mythic-fantasy line after PSX is established.
