# Node: `Resource`

> **Region**: [VirtualTextureBank](_REGION.md)
> **Child Depth**: 1 (flat — no child nodes)

---

## Attributes

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `ID` | FixedString | UUID primary key | `0a474694-...` |
| `Name` | LSString | Virtual texture name | `DEC_CEM_Tomb_A_Shar_Statue_A` |
| `GTexFileName` | FixedString | GTex hash filename | `96a33da0d8fd334745ec4d654e8bcaaa` |
| `Prefetch` | bool | Pre-fetch on load | `False` |
| `PrefetchMipLevel` | int8 | Mip level to prefetch (-1 = none) | `-1` |
| `ReferencedColorSpaces` | uint32 | Color space flags | `6` |
| `VirtualTextureLayerConfig` | uint32 | Layer configuration flags | `3` |
| `_OriginalFileVersion_` | int64 | Engine version stamp | `144115207403209023` |

## Child Nodes

_(None — flat resource structure)_

## Cross-References

| From | To | Via |
|------|----|-----|
| Resource.ID | [MaterialBank](../MaterialBank/_REGION.md) | `VirtualTextureParameters.ID` |

## Notes

- The `GTexFileName` is a content hash, not a human-readable name
- Almost always co-located with other banks in the same `_merged.lsx` file
