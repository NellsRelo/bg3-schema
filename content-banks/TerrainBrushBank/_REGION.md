# Region: `TerrainBrushBank`

> **Category**: Environment
> **Primary Node**: [Resource](Resource.md)
>
> Defines terrain painting brushes — material configurations used by the world editor's
> terrain painting tools. Approximately 25 attributes per brush.

---

## File Inventory

| Source | Path Pattern | Content |
|--------|-------------|---------|
| Shared | `Content/Assets/Terrain/[PAK]_TerrainBrushes/_merged.lsx` | Terrain brush definitions |

**1 file in Shared** containing TerrainBrushBank regions.

## Region Structure

```xml
<region id="TerrainBrushBank">
  <node id="TerrainBrushBank">
    <children>
      <node id="Resource"> ... </node>
    </children>
  </node>
</region>
```

## Node Types

| Node | File | Description |
|------|------|-------------|
| Resource | [Resource.md](Resource.md) | One per terrain brush — flat (no child nodes), ~25 material attributes |

## Cross-Region References

| From | To | Via |
|------|----|-----|
| TerrainBrushBank.VirtualTextureGUID | [VirtualTextureBank](../VirtualTextureBank/_REGION.md) | Terrain virtual texture |

## Notes

- Single-file bank — all terrain brushes in one `_merged.lsx`
- Flat structure — no child nodes, but attribute-rich (~25 per brush)
- Material properties include layered PBR textures (base, layer0, layer1) with tiling, color, roughness, metallic
