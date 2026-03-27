# Region: `VisualBank`

> **Category**: Visual
> **Primary Node**: [Resource](Resource.md)
>
> Defines individual 3D model/mesh resources — the building blocks of all visible objects.
> Referenced by `CharacterVisualBank` slots, `GameObjects.VisualTemplate`, and `TileSetBank` tiles.

---

## File Inventory

| Source | Path Pattern | Content |
|--------|-------------|---------|
| Shared | `Content/Assets/Characters/.../_merged.lsx` | Character body/head meshes |
| Shared | `Content/Assets/Buildings/.../_merged.lsx` | Architecture meshes |
| Shared | `Content/Assets/Effects/Models/.../_merged.lsx` | VFX model meshes |
| SharedDev | `Content/Assets/.../_merged.lsx` | Extended assets |

**54 files in Shared** containing VisualBank regions.

## Region Structure

```xml
<region id="VisualBank">
  <node id="VisualBank">
    <children>
      <node id="Resource"> ... </node>   <!-- repeated -->
    </children>
  </node>
</region>
```

## Node Types

| Node | File | Description |
|------|------|-------------|
| Resource | [Resource.md](Resource.md) | One per visual mesh/model — contains LOD meshes, cloth physics, animation waterfalls |

## Cross-Region References

| From | To | Via |
|------|----|-----|
| VisualBank.ID | [CharacterVisualBank](../CharacterVisualBank/_REGION.md) | `Slots.VisualResource` — slot visual assignment |
| VisualBank.ID | [TileSetBank](../TileSetBank/_REGION.md) | `Tile.VisualGUID` — tile visual |
| VisualBank.ID | [SplineSetBank](../SplineSetBank/_REGION.md) | `Tile.VisualGUID` — spline visual |
| VisualBank.SkeletonResource | [SkeletonBank](../SkeletonBank/_REGION.md) | Skeleton binding |
| VisualBank.BlueprintInstanceResourceID | [AnimationBlueprintBank](../AnimationBlueprintBank/_REGION.md) | Animation blueprint |
| VisualBank.Objects.MaterialID | [MaterialBank](../MaterialBank/_REGION.md) | Mesh material |
| VisualBank.AnimationWaterfall.Object | [AnimationSetBank](../AnimationSetBank/_REGION.md) | Animation waterfall |
| GameObjects.VisualTemplate | VisualBank.ID | World object visual |

## Co-located Banks

VisualBank is frequently co-located in `_merged.lsx` files with:
- [MaterialBank](../MaterialBank/_REGION.md), [TextureBank](../TextureBank/_REGION.md), [VirtualTextureBank](../VirtualTextureBank/_REGION.md) (asset bundles)
- [SkeletonBank](../SkeletonBank/_REGION.md), [AnimationBank](../AnimationBank/_REGION.md), [AnimationSetBank](../AnimationSetBank/_REGION.md) (character bundles)
