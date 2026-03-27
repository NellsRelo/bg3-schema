# Region: `SplineSetBank`

> **Category**: Environment
> **Primary Node**: [Resource](Resource.md)
>
> Defines spline sets — similar to TileSetBank but for path/curve-based constructions
> (roads, rivers, cable runs). Simpler than TileSetBank — no physics or climbing helpers.

---

## File Inventory

| Source | Path Pattern | Content |
|--------|-------------|---------|
| Shared | `Content/Assets/Tilesets/.../_merged.lsx` | Spline set definitions |

**13 files in Shared** containing SplineSetBank regions.

## Region Structure

```xml
<region id="SplineSetBank">
  <node id="SplineSetBank">
    <children>
      <node id="Resource"> ... </node>
    </children>
  </node>
</region>
```

## Node Types

| Node | File | Description |
|------|------|-------------|
| Resource | [Resource.md](Resource.md) | One per spline set — contains TileSet → Tile children (3 levels) |

## Cross-Region References

| From | To | Via |
|------|----|-----|
| SplineSetBank.Tile.VisualGUID | [VisualBank](../VisualBank/_REGION.md) | Tile visual mesh |

## Co-located Banks

SplineSetBank is co-located with:
- [VisualBank](../VisualBank/_REGION.md), [MaterialBank](../MaterialBank/_REGION.md), [VirtualTextureBank](../VirtualTextureBank/_REGION.md) (spline asset bundles)

## Notes

- 13 instances in Shared — spline-based construction sets (roads, ropes, cables, etc.)
- Structure mirrors TileSetBank but **no PhysicsGUID** on tiles
