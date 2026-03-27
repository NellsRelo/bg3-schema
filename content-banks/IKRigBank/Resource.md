# Node: `Resource`

> **Region**: [IKRigBank](_REGION.md)
> **Child Depth**: 4 (Resource → BoneProperties → IKBone → Limits)

---

## Node Hierarchy

```
Resource
├── BoneCategories            ← empty node
└── BoneProperties            ← repeated map entries (per bone)
    ├── MapKey (FixedString)  ← bone name
    └── MapValue
        └── IKBone
            ├── DoF           (int64) ← degrees of freedom bitmask
            ├── Enabled       (bool)
            ├── Weight        (fvec3) ← per-axis weight
            └── Limits        ← repeated (per axis constraint)
                ├── Axis      (uint8) ← axis index
                ├── Enabled   (bool)
                ├── Max       (fvec3) ← rotation max
                └── Min       (fvec3) ← rotation min
```

## Attributes

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `ID` | FixedString | UUID primary key | `3dd1bb68-7f06-c7bc-0521-b3be9b4eb90b` |
| `Name` | LSString | IK rig name | `Animals_Heads_IKRig` |
| `SourceFile` | LSString | Source file path | _(empty)_ |
| `Localized` | bool | Localization flag | `False` |
| `_OriginalFileVersion_` | int64 | Engine version stamp | `144115198813274313` |

## Child: BoneProperties → IKBone

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `DoF` | int64 | Degrees of freedom bitmask (7 = all axes) | `7` |
| `Enabled` | bool | IK solving enabled for this bone | `True`, `False` |
| `Weight` | fvec3 | Per-axis IK weight | `1 1 1` |

## BoneProperties → IKBone → Limits

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `Axis` | uint8 | Rotation axis (0/1/2 = X/Y/Z) | `0` |
| `Enabled` | bool | Limit enabled | `True` |
| `Max` | fvec3 | Maximum rotation | `20 20 20` |
| `Min` | fvec3 | Minimum rotation | `-20 -20 -20` |

## Cross-References

| From | To | Via |
|------|----|-----|
| Resource.ID | [SkeletonBank](../SkeletonBank/_REGION.md) | `IKRigResourceID` |
