# Node: `Resource`

> **Region**: [ClothColliderBank](_REGION.md)
> **Child Depth**: 3 (Resource → Spheres → Links)

---

## Node Hierarchy

```
Resource
└── Spheres                       ← repeated (one per collision sphere)
    ├── AttachedName (FixedString) ← bone to attach to
    ├── Name         (FixedString) ← sphere name
    ├── Position     (fvec3)       ← offset from bone
    ├── Radius       (float)       ← collision radius
    └── Links                      ← optional (capsule connections)
        └── Link     (FixedString) ← target bone name
```

## Attributes

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `ID` | FixedString | UUID primary key | `f29e4d2d-...` |
| `Name` | LSString | Collider set name | `MFL_M_NKD_Body_ClothCollider` |
| `SourceFile` | LSString | Source file path | _(empty)_ |
| `_OriginalFileVersion_` | int64 | Engine version stamp | `144115207403208706` |

## Child: Spheres

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `AttachedName` | FixedString | Skeleton bone name | `Toes_L`, `Chest_M`, `Hip_R` |
| `Name` | FixedString | Sphere identifier (matches bone) | `Toes_L` |
| `Position` | fvec3 | Offset from bone origin | `-0.10327445 -1.937151E-07 -4.7683716E-07` |
| `Radius` | float | Collision sphere radius | `0.1`, `0.25` |

## Spheres → Links (Optional)

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `Link` | FixedString | Target bone name (forms capsule) | `Ankle_L`, `Root_M` |

## Cross-References

| From | To | Via |
|------|----|-----|
| Resource.ID | [SkeletonBank](../SkeletonBank/_REGION.md) | `ClothColliderResourceID` |
| Resource.ID | [VisualBank](../VisualBank/_REGION.md) | `ClothColliderResourceID` |
