# Node: `TextureAtlasInfo` (singleton)

> **Region**: [TextureAtlasInfo](_REGION.md)
> **Exists in**: Embedded within GUI/CharacterCreation icon atlas files (not standalone)
> **Note**: Always paired with an [IconUVList](../IconUVList/IconUV.md) region in the same file.
> **Structure**: Non-standard — contains exactly 3 fixed child nodes, NOT a repeating collection.

---

## Structure

Each `TextureAtlasInfo` region contains a root node with exactly 3 children:

### TextureAtlasIconSize

Individual icon dimensions within the atlas:

| Attribute | Type | Examples | Notes |
|-----------|------|----------|-------|
| `Height` | int32 | `64`, `100`, `150` | Single icon height in pixels |
| `Width` | int32 | `64`, `80`, `150` | Single icon width in pixels |

### TextureAtlasPath

Path to the DDS texture atlas file:

| Attribute | Type | Examples | Notes |
|-----------|------|----------|-------|
| `Path` | string | `Assets/Textures/Icons/Icons_Skills.dds` | Relative path to atlas DDS |
| `UUID` | FixedString | *(guid)* | Atlas resource UUID |

### TextureAtlasTextureSize

Total atlas texture dimensions:

| Attribute | Type | Examples | Notes |
|-----------|------|----------|-------|
| `Height` | int32 | `512`, `1024`, `2048`, `4096` | Full atlas height |
| `Width` | int32 | `512`, `1024`, `2048`, `8192` | Full atlas width |

## Observed Dimensions

| File | Icon Size | Atlas Size |
|------|-----------|-----------|
| Generated_CCIcons (Gustav) | 150×150 | 8192×4096 |
| Generated_CCIcons (Shared) | 150×150 | 8192×4096 |
| Icons (GustavX) | 64×64 | 1024×512 |
| Portraits_Gustav | 80×100 | 512×512 |
| Icons_Skills | 64×64 | 2048×2048 |
| Icons_Items (×6 files) | 64×64 | 512–2048 (varies) |

## Source Files

Same 11 files as [IconUVList](../IconUVList/IconUV.md) — each atlas file contains both regions.

## Similarities to Other Nodes

*(To be documented)*
