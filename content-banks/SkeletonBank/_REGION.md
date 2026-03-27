# Region: `SkeletonBank`

> **Category**: Animation
> **Primary Node**: [Resource](Resource.md)
>
> Defines skeleton/rig resources — bone hierarchies that animations are applied to.
> Referenced by `VisualBank.SkeletonResource` and `AnimationBank.SkeletonResource`.

---

## File Inventory

| Source | Path Pattern | Content |
|--------|-------------|---------|
| Shared | `Content/Assets/Characters/.../_merged.lsx` | Character skeletons |
| Shared | `Content/Assets/Buildings/.../_merged.lsx` | Object skeletons (animated doors, etc.) |

**243 files in Shared** — the most common bank type by instance count.

## Region Structure

```xml
<region id="SkeletonBank">
  <node id="SkeletonBank">
    <children>
      <node id="Resource"> ... </node>
    </children>
  </node>
</region>
```

## Node Types

| Node | File | Description |
|------|------|-------------|
| Resource | [Resource.md](Resource.md) | One per skeleton — contains optional bone sound metadata |

## Cross-Region References

| From | To | Via |
|------|----|-----|
| SkeletonBank.ID | [VisualBank](../VisualBank/_REGION.md) | `SkeletonResource` — visual skeleton |
| SkeletonBank.ID | [AnimationBank](../AnimationBank/_REGION.md) | `SkeletonResource` — animation skeleton target |
| SkeletonBank.ClothColliderResourceID | [ClothColliderBank](../ClothColliderBank/_REGION.md) | Cloth collision |
| SkeletonBank.IKRigResourceID | [IKRigBank](../IKRigBank/_REGION.md) | IK rig |

## Notes

- **Most common bank type** — 243 instances in Shared (every animated object needs a skeleton)
- `Bones` children are optional — only present when bones have sound object associations
- Many physics reference fields accept null UUIDs (`00000000-...`) when not used
