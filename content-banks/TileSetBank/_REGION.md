# Region: `TileSetBank`

> **Category**: Environment
> **Primary Node**: [Resource](Resource.md)
>
> Defines tile sets — collections of visual + physics tiles for modular level construction
> (walls, floors, pillars, etc.).

---

## File Inventory

| Source | Path Pattern | Content |
|--------|-------------|---------|
| Shared | `Content/Assets/Tilesets/.../_merged.lsx` | Tileset definitions |
| Gustav | `Content/Assets/Tilesets/.../_merged.lsx` | Campaign tilesets |

**167 files in Shared** containing TileSetBank regions.

## Region Structure

```xml
<region id="TileSetBank">
  <node id="TileSetBank">
    <children>
      <node id="Resource"> ... </node>
    </children>
  </node>
</region>
```

## Node Types

| Node | File | Description |
|------|------|-------------|
| Resource | [Resource.md](Resource.md) | One per tile set — contains TileSet → Tile children (3 levels) |

## Cross-Region References

| From | To | Via |
|------|----|-----|
| TileSetBank.Tile.VisualGUID | [VisualBank](../VisualBank/_REGION.md) | Tile visual mesh |
| TileSetBank.Tile.PhysicsGUID | [PhysicsBank](../PhysicsBank/_REGION.md) | Tile physics collision |

## Co-located Banks

TileSetBank is frequently co-located with:
- [VisualBank](../VisualBank/_REGION.md), [SkeletonBank](../SkeletonBank/_REGION.md), [PhysicsBank](../PhysicsBank/_REGION.md), [MaterialBank](../MaterialBank/_REGION.md), [VirtualTextureBank](../VirtualTextureBank/_REGION.md) (tileset asset bundles)
