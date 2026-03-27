# Node: `IconUV`

> **Region**: [IconUVList](_REGION.md)
> **Exists in**: Embedded within GUI/CharacterCreation icon atlas files (not standalone)
> **Note**: Always paired with a [TextureAtlasInfo](../TextureAtlasInfo/TextureAtlasInfo.md) region in the same file.

---

## Attributes

| Attribute | Type | Frequency | Examples | Notes |
|-----------|------|-----------|----------|-------|
| `MapKey` | FixedString | always | `Action_Attack`, `56c0c279-...` | Icon identifier (name or UUID) |
| `U1` | float | always | `0.0` – `1.0` | Left edge UV coordinate |
| `U2` | float | always | `0.0` – `1.0` | Right edge UV coordinate |
| `V1` | float | always | `0.0` – `1.0` | Top edge UV coordinate |
| `V2` | float | always | `0.0` – `1.0` | Bottom edge UV coordinate |

UV coordinates define the icon's bounding rectangle within the parent texture atlas.

## Child Nodes

*(None)*

## Source Files

| File | Pack | Context | Approx Nodes |
|------|------|---------|-------------|
| `GustavDev/CharacterCreation/Generated_CCIcons.lsx` | Gustav | Character creation icons | ~200+ |
| `SharedDev/CharacterCreation/Generated_CCIcons.lsx` | Shared | Character creation icons | ~200+ |
| `GustavX/GUI/Icons.lsx` | GustavX | Action/skill icons | ~100–120 |
| `Shared/GUI/Portraits_Gustav.lsx` | Shared | Portrait icons | ~30–35 |
| `Shared/GUI/Icons_Skills.lsx` | Shared | Skill/spell icons | ~1,000+ |
| `Shared/GUI/Icons_Items.lsx` | Shared | Item icons (set 1) | ~160–180 |
| `Shared/GUI/Icons_Items_2.lsx` | Shared | Item icons (set 2) | ~160–180 |
| `Shared/GUI/Icons_Items_3.lsx` | Shared | Item icons (set 3) | ~160–180 |
| `Shared/GUI/Icons_Items_4.lsx` | Shared | Item icons (set 4) | ~160–180 |
| `Shared/GUI/Icons_Items_5.lsx` | Shared | Item icons (set 5) | ~160–180 |
| `Shared/GUI/Icons_Items_6.lsx` | Shared | Item icons (set 6) | ~160–180 |

**Total**: 11 files across 3 packs, thousands of IconUV entries combined.

## Similarities to Other Nodes

*(To be documented)*
