# Region: `BlendSpaceBank`

> **Category**: Animation
> **Primary Node**: [Resource](Resource.md)
>
> Defines 2D blend spaces for animation interpolation — maps parameter values to animation positions
> for smooth blending (e.g., speed → walk/run blend, angle → directional movement).

---

## File Inventory

| Source | Path Pattern | Content |
|--------|-------------|---------|
| Shared | `Content/Assets/Characters/.../_merged.lsx` | Traversal animation blend spaces |

**3 files in Shared** containing BlendSpaceBank regions.

## Region Structure

```xml
<region id="BlendSpaceBank">
  <node id="BlendSpaceBank">
    <children>
      <node id="Resource"> ... </node>
    </children>
  </node>
</region>
```

## Node Types

| Node | File | Description |
|------|------|-------------|
| Resource | [Resource.md](Resource.md) | One per blend space — contains input sample points |

## Cross-Region References

| From | To | Via |
|------|----|-----|
| BlendSpaceBank.Inputs.AnimationID | [AnimationBank](../AnimationBank/_REGION.md) | Blend space animation source |

## Notes

- Only 3 instances in Shared — used for traversal animations (ladder climbing, etc.)
- Blend spaces interpolate between animation clips based on runtime parameter values
