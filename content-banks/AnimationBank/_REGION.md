# Region: `AnimationBank`

> **Category**: Animation
> **Primary Node**: [Resource](Resource.md)
>
> Defines individual animation clips — single animation sequences bound to a skeleton.
> Flat resource structure — no child nodes.

---

## File Inventory

| Source | Path Pattern | Content |
|--------|-------------|---------|
| Shared | `Content/Assets/Characters/.../_merged.lsx` | Character animation clips |
| Shared | `Content/Assets/Buildings/.../_merged.lsx` | Object animations (doors, levers) |
| Shared | `Content/Assets/Items/.../_merged.lsx` | Item animations |

**46 files in Shared** containing AnimationBank regions.

## Region Structure

```xml
<region id="AnimationBank">
  <node id="AnimationBank">
    <children>
      <node id="Resource"> ... </node>
    </children>
  </node>
</region>
```

## Node Types

| Node | File | Description |
|------|------|-------------|
| Resource | [Resource.md](Resource.md) | One per animation clip — flat, no child nodes |

## Cross-Region References

| From | To | Via |
|------|----|-----|
| AnimationBank.ID | [AnimationSetBank](../AnimationSetBank/_REGION.md) | `Animation.Object.ID` — animation set member |
| AnimationBank.ID | [VisualBank](../VisualBank/_REGION.md) | `AnimationWaterfall.Object` — visual animation waterfall |
| AnimationBank.SkeletonResource | [SkeletonBank](../SkeletonBank/_REGION.md) | Skeleton binding |
| AnimationBank.PreviewVisualResource | [VisualBank](../VisualBank/_REGION.md) | Editor preview mesh |

## Naming Conventions

Animation names follow a hierarchical convention:
- `{CREATURE}_{RIG}_{CONTEXT}_{ACTION}_{VARIANT}`
- **Creature**: `BIRD`, `HUM`, `DWR`, `MFL`, `GNO`, etc.
- **Context**: `CINE` (cinematic), `GP` (gameplay), `CC` (character creation)
- **Action**: `Idle`, `Walk`, `Run`, `Attack`, `Cast`, `Death`, etc.
