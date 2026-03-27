# Region: `FCurveBank`

> **Category**: Animation
> **Primary Node**: [Resource](Resource.md)
>
> Defines animation function curves — keyframe curves used for procedural animation
> (root motion, camera shake, etc.).

---

## File Inventory

| Source | Path Pattern | Content |
|--------|-------------|---------|
| Shared | `Content/Assets/Characters/.../_merged.lsx` | Combat root motion curves |

**8 files in Shared** containing FCurveBank regions.

## Region Structure

```xml
<region id="FCurveBank">
  <node id="FCurveBank">
    <children>
      <node id="Resource"> ... </node>
    </children>
  </node>
</region>
```

## Node Types

| Node | File | Description |
|------|------|-------------|
| Resource | [Resource.md](Resource.md) | One per curve — contains keyframes and axis limits |

## Notes

- 8 instances in Shared — primarily for combat root motion curves (dodge, knockback)
- `CurveKeyPosition.x` = time, `CurveKeyPosition.y` = value
