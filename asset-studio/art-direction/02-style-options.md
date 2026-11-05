# Art Style Options

## The selection test (from the source blueprint)

> "It must be a style that is **technically easy for your team to produce fast**, but
> **hard for a solo programmer to make look cohesive on their own**." It also has to be one
> that indie developers want and that **no one is standardizing into massive modular libraries**.

So each candidate is scored on four things (1 = poor, 5 = strong):
- **Fast to make:** cost per asset for us
- **Hard to DIY:** how hard it is for a coder to get it looking consistent alone. This is why people pay.
- **Demand:** how many indie projects want this look right now
- **Open lane:** no Synty-scale modular library exists for it yet

| # | Style | Source | Fast to make | Hard to DIY | Demand | Open lane | Total |
|---|---|---|---|---|---|---|---|
| 1 | **PS1-era retro (PSX)**, occult/horror themes | Source doc | 5 | 4 | 5 | 4 | **18** ✅ |
| 2 | Gilded Facet: bevelled low-poly, toon-lit, jewel + gold | Our earlier draft | 4 | 3 | 4 | 4 | 15 |
| 3 | Ghibli-esque hand-painted 3D | Source doc | 2 | 5 | 5 | 3 | 15 |
| 4 | Vector-style isometric sci-fi | Source doc | 4 | 3 | 2 | 4 | 13 |
| 5 | HD-2D (pixel sprites in 3D dioramas) | Source doc | 2 | 5 | 3 | 3 | 13 |
| — | Clean flat low-poly | Synty's own | 5 | 1 | 5 | 1 | 12 ❌ |

## Why PSX wins

- **Fast to make:** about 100–800 tris per prop, 64–256 px textures, no normal maps, no PBR. A prop takes roughly 1–3 hours, faster than any other option except plain flat low-poly.
- **Hard to DIY:** the "authentic PS1 look" takes vertex snapping, affine texture warping, colour quantisation, dithering, fog and consistent texel density all at once. Solo developers usually end up with a mix of mismatched free assets. **The shader kit plus one texel/palette standard is the product.**
- **Demand:** the indie horror and retro scene (itch.io, Steam "PSX horror", Haunted PS1-type jams) is large and keeps growing.
- **Open lane:** PSX assets exist mostly as small one-off packs from many different creators with no shared standard. Nobody runs a "Synty of PSX".
- **Brand fit:** *Ordo Caelum* ("Order of the Heavens") suits occult orders, abbeys, cults and cosmic horror.
- **Doesn't fight Synty:** Synty's clean, bright look is the opposite. Their buyers are potential customers, not their loyal fans.

## Runners-up and how to use them

- **Gilded Facet** stays on file as a possible *second product line* (non-horror mythic fantasy) once PSX is established.
- **Ghibli hand-painted** has the highest demand, but costs about 3–5× as much per asset. Revisit when there's revenue to hire painters.
- **HD-2D**: avoid as the first line. It's slow to make, and the look is strongly tied to one publisher's games.
