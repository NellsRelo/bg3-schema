# Region: `AnimationSetBank`

> **Category**: Animation
> **Primary Node**: [Resource](Resource.md)
>
> Groups multiple animations into named sets with subset categorization.
> Referenced by `VisualBank.AnimationWaterfall` — controls which animations are available to a visual.

---

## File Inventory

| Source | Path Pattern | Content |
|--------|-------------|---------|
| Shared | `Content/Assets/Characters/.../_merged.lsx` | Character animation sets |

**120 files in Shared** containing AnimationSetBank regions.

## Region Structure

```xml
<region id="AnimationSetBank">
  <node id="AnimationSetBank">
    <children>
      <node id="Resource"> ... </node>
    </children>
  </node>
</region>
```

## Node Types

| Node | File | Description |
|------|------|-------------|
| Resource | [Resource.md](Resource.md) | One per animation set — deeply nested map structure (4 levels) |

## Cross-Region References

| From | To | Via |
|------|----|-----|
| AnimationSetBank.ID | [VisualBank](../VisualBank/_REGION.md) | `AnimationWaterfall.Object` — visual animation set |
| AnimationSetBank.Animation.ID | [AnimationBank](../AnimationBank/_REGION.md) | Individual animation clip |

## Notes

- 120 instances in Shared — animation sets bundle related clips (all idle variants, all attack variants, etc.)
- The deeply nested `AnimationBank` node inside `AnimationSet` is a **map container**, not a reference to the AnimationBank region
- `MapKey` fields are UUIDs that serve as animation slot identifiers
