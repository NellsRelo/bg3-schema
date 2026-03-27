# Node: `GameColor` (root-level attributes)

> **Region**: [Color](_REGION.md)
> **Folder**: `Lists/`
> **Source**: `Shared/Public/Shared/Lists/GameColors.lsx` (also Deuteranopia, Protanopia, Tritanopia variants)
> **Structure**: Non-standard — 76 attributes directly on root node, no child nodes

---

## Attributes (on root)

Unlike most regions, `Color` has **no child nodes**. All 76 attributes are `fvec4` (RGBA float4) directly on the `root` node.

| Attribute Prefix | Type | Count | Examples | Notes |
|-----------------|------|-------|----------|-------|
| `GameColor_*` | fvec4 | 76 | `GameColor_ActiveCharacter`, `GameColor_Ally_Base`, `GameColor_Ally_Light` | Each is a 4-component float vector (x,y,z,w = R,G,B,A; 0-255 range) |

### Sample Attributes

| Attribute | R | G | B | A | Purpose |
|-----------|---|---|---|---|--------|
| `GameColor_ActiveCharacter` | 255 | 255 | 255 | 255 | Active character highlight |
| `GameColor_Ally_Base` | 41 | 205 | 87 | 255 | Ally base color (green) |
| `GameColor_Ally_Light` | 82 | 255 | 174 | 255 | Ally light variant |
| `GameColor_AoO` | 255 | 2 | 0 | 255 | Attack of Opportunity (red) |
| `GameColor_AoOSecondary` | 179 | 0 | 0 | 255 | AoO secondary color |

## Child Nodes

None — all data is root-level attributes.

## Patterns of Use

- Defines the game's UI color palette used for character outlines, surfaces, damage types, schools, etc.
- Colorblind variants exist: `GameColors_Deuteranopia.lsx`, `GameColors_Protanopia.lsx`, `GameColors_Tritanopia.lsx`
- Color names follow patterns: `GameColor_<Category>_<Variant>` (e.g., `Ally_Base`, `Ally_Light`, `Enemy_Base`)
- Categories include: Ally, Enemy, Neutral, School (magic schools), Surface, AoO, etc.

## Caveats & Gotchas

- **Non-standard structure**: No child `GameColor` nodes — attributes directly on root. Scanner cannot process this.
- `fvec4` uses `<float4 x="R" y="G" z="B" w="A"/>` child element, not `value="..."` attribute
- Values are 0-255 integers stored as floats
- Must handle 4 variant files for accessibility support

## Similarities to Other Nodes

None — unique flat-attribute structure.

*(To be documented)*
