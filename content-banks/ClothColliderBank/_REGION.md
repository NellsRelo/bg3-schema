# Region: `ClothColliderBank`

> **Category**: Animation
> **Primary Node**: [Resource](Resource.md)
>
> Defines cloth simulation collision shapes — sphere + capsule primitives attached to skeleton bones
> that cloth physics will collide against.

---

## File Inventory

| Source | Path Pattern | Content |
|--------|-------------|---------|
| Shared | `Content/Assets/Characters/.../_merged.lsx` | Character cloth collider definitions |

**10 files in Shared** containing ClothColliderBank regions.

## Region Structure

```xml
<region id="ClothColliderBank">
  <node id="ClothColliderBank">
    <children>
      <node id="Resource"> ... </node>
    </children>
  </node>
</region>
```

## Node Types

| Node | File | Description |
|------|------|-------------|
| Resource | [Resource.md](Resource.md) | One per collider set — contains sphere/capsule collision primitives |

## Cross-Region References

| From | To | Via |
|------|----|-----|
| ClothColliderBank.ID | [SkeletonBank](../SkeletonBank/_REGION.md) | `ClothColliderResourceID` — skeleton cloth collision |
| ClothColliderBank.ID | [VisualBank](../VisualBank/_REGION.md) | `ClothColliderResourceID` — visual cloth collision |

## Notes

- 10 instances in Shared — primarily for humanoid characters (cloaks, robes, hair)
- **Spheres alone** define simple sphere colliders; **Spheres + Links** define capsule colliders (two linked spheres form a capsule)
- Leaf bones (shoulders, spine, root) may have no Links — they act as simple sphere colliders
