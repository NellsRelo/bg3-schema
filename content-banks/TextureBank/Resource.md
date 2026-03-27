# Node: `Resource`

> **Region**: [TextureBank](_REGION.md)
> **Child Depth**: 1 (flat — no child nodes)

---

## Attributes

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `ID` | FixedString | UUID primary key | `71708c59-8bb5-2367-a76c-7b98b09029da` |
| `Name` | LSString | Texture name | `Planet_moon_A_BM` |
| `SourceFile` | LSString | DDS source path | `Generated/Public/Shared/Assets/.../Planet_moon_A_BM.DDS` |
| `Template` | FixedString | Template name | `Planet_moon_A_BM` |
| `Width` | int32 | Texture width in pixels | `1024`, `2048` |
| `Height` | int32 | Texture height in pixels | `2048`, `512` |
| `Depth` | int32 | Texture depth (1 for 2D) | `1` |
| `Type` | int32 | Texture type enum | `1` |
| `SRGB` | bool | sRGB color space | `True`, `False` |
| `Streaming` | bool | Supports texture streaming | `True` |
| `Localized` | bool | _(optional)_ Localization flag | `False` |
| `_OriginalFileVersion_` | int64 | Engine version stamp | `144115207403209020` |

## Child Nodes

_(None — flat resource structure)_

## Cross-References

| From | To | Via |
|------|----|-----|
| Resource.ID | [MaterialBank](../MaterialBank/_REGION.md) | `Texture2DParameters.ID` |
| Resource.ID | [LightCookieBank](../LightCookieBank/_REGION.md) | `TextureName` |
| Resource.ID | [TerrainBrushBank](../TerrainBrushBank/_REGION.md) | `BaseColorMap`/`NormalMap`/`PhysicalMap` |
