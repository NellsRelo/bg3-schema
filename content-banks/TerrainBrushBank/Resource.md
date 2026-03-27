# Node: `Resource`

> **Region**: [TerrainBrushBank](_REGION.md)
> **Child Depth**: 1 (flat — no child nodes)

---

## Attributes

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `ID` | FixedString | UUID primary key | `0011b2e1-...` |
| `Name` | LSString | Brush name | `GRS_Grass_A` |
| `VirtualTextureGUID` | FixedString | UUID → [VirtualTextureBank](../VirtualTextureBank/_REGION.md) | `00f57e4e-...` |
| `MaterialType` | int32 | Material type code | `0` |
| `BaseColorMap` | FixedString | Base color texture path | `(empty)` |
| `NormalMap` | FixedString | Normal map texture path | `Public/Shared/.../Texture.dds` |
| `PhysicalMap` | FixedString | Physical properties texture | `Public/Shared/...` |
| `Tiling` | float | Base texture tiling | `0.5` |
| `HeightContrast` | float | Height blend contrast | `0.25` |
| `HeightOffset` | float | Height blend offset | `0` |
| `Roughness` | float | Base roughness | `1` |
| `Metallic` | float | Base metallic | `0` |
| `BaseColor` | fvec3 | Base color tint | `0.5 0.5 0.5` |
| `Layer0_BaseColor` | fvec3 | Layer 0 color tint | `0.5 0.5 0.5` |
| `Layer0_BaseColorMap` | FixedString | Layer 0 color texture | `(empty)` |
| `Layer0_NormalMap` | FixedString | Layer 0 normal texture | `(empty)` |
| `Layer0_PhysicalMap` | FixedString | Layer 0 physical texture | `(empty)` |
| `Layer0_Tiling` | float | Layer 0 texture tiling | `4` |
| `Layer0_Roughness` | float | Layer 0 roughness | `1` |
| `Layer0_Metallic` | float | Layer 0 metallic | `0` |
| `Layer1_BaseColor` | fvec3 | Layer 1 color tint | `0.5 0.5 0.5` |
| `Layer1_BaseColorMap` | FixedString | Layer 1 color texture | `(empty)` |
| `Layer1_NormalMap` | FixedString | Layer 1 normal texture | `(empty)` |
| `Layer1_PhysicalMap` | FixedString | Layer 1 physical texture | `(empty)` |
| `Layer1_Tiling` | float | Layer 1 texture tiling | `4` |
| `Layer1_Roughness` | float | Layer 1 roughness | `1` |
| `Layer1_Metallic` | float | Layer 1 metallic | `0` |
| `ForGameMaster` | bool | _(optional)_ Game Master visibility | `True` |
| `GMSubSection` | TranslatedString | _(optional)_ GM UI section | ... |
| `Localized` | bool | Localization flag | `False` |
| `_OriginalFileVersion_` | int64 | Engine version stamp | ... |

## Child Nodes

_(None — flat resource structure)_

## Cross-References

| From | To | Via |
|------|----|-----|
| Resource.VirtualTextureGUID | [VirtualTextureBank](../VirtualTextureBank/_REGION.md) | Terrain virtual texture |
