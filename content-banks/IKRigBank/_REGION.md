# Region: `IKRigBank`

> **Category**: Animation
> **Primary Node**: [Resource](Resource.md)
>
> Defines inverse kinematics rig configurations — controls how bone chains solve
> (e.g., foot placement on terrain, hand reaching for objects).

---

## File Inventory

| Source | Path Pattern | Content |
|--------|-------------|---------|
| Shared | `Content/Assets/Characters/.../_merged.lsx` | IK rig definitions |

**1 file in Shared** containing IKRigBank regions.

## Region Structure

```xml
<region id="IKRigBank">
  <node id="IKRigBank">
    <children>
      <node id="Resource"> ... </node>
    </children>
  </node>
</region>
```

## Node Types

| Node | File | Description |
|------|------|-------------|
| Resource | [Resource.md](Resource.md) | One per IK rig — deeply nested bone property configuration (4 levels) |

## Cross-Region References

| From | To | Via |
|------|----|-----|
| IKRigBank.ID | [SkeletonBank](../SkeletonBank/_REGION.md) | `IKRigResourceID` — skeleton IK rig |

## Notes

- Only 1 instance in Shared — IK rigs are shared across many skeletons
- `BoneCategories` child node is always empty in data
- `DoF` value of 7 (binary 111) enables all three rotation axes
