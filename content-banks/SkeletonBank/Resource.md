# Node: `Resource`

> **Region**: [SkeletonBank](_REGION.md)
> **Child Depth**: 2 (Resource → Bones map)

---

## Node Hierarchy

```
Resource
└── Bones                              ← repeated map entries (optional)
    ├── MapKey (FixedString)           ← bone name
    └── MapValue
        ├── SoundObjectActivationRange (float)
        └── SoundObjectIndex           (uint8)
```

## Attributes

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `ID` | FixedString | UUID primary key | `8484b732-8a7d-6678-5384-84b33f48f279` |
| `Name` | LSString | Skeleton name | `BLD_Village_House_Door_A_Wood_Scenery_B_Explode_Base` |
| `SourceFile` | LSString | GR2 source path | `Public/Shared/Assets/Buildings/.../....GR2` |
| `Template` | FixedString | Skeleton template ref | `Public/Shared/Assets/Buildings/.../....Dummy_Root.0` |
| `PreviewAnimationResource` | FixedString | UUID → [AnimationBank](../AnimationBank/_REGION.md) (editor preview) | _(empty)_ |
| `PreviewVisualResource` | FixedString | UUID → [VisualBank](../VisualBank/_REGION.md) (editor preview) | _(empty)_ |
| `ClothColliderResourceID` | FixedString | _(optional)_ UUID → [ClothColliderBank](../ClothColliderBank/_REGION.md) | _(empty or UUID)_ |
| `DynamicPhysicsResourceID` | FixedString | Dynamic physics ref | `1ed36695-03da-85ef-dcd0-b06a018584e5` |
| `IKRigResourceID` | FixedString | UUID → [IKRigBank](../IKRigBank/_REGION.md) | `00000000-0000-0000-0000-000000000000` |
| `RagdollResourceID` | FixedString | Ragdoll physics ref | `00000000-...` |
| `SoftbodyResourceID` | FixedString | Softbody physics ref | `00000000-...` |
| `SpringResourceID` | FixedString | Spring physics ref | `00000000-...` |
| `Localized` | bool | Localization flag | `False` |
| `_OriginalFileVersion_` | int64 | Engine version stamp | `144115188075855902` |

## Child: Bones (Map Structure)

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `MapKey` | FixedString | Bone name | `Dummy_R_HandFX` |
| `MapValue.SoundObjectActivationRange` | float | Sound trigger radius | `40` |
| `MapValue.SoundObjectIndex` | uint8 | Sound object index | `1`, `2`, `3` |

## Cross-References

| From | To | Via |
|------|----|-----|
| Resource.ID | [VisualBank](../VisualBank/_REGION.md) | `SkeletonResource` |
| Resource.ID | [AnimationBank](../AnimationBank/_REGION.md) | `SkeletonResource` |
| Resource.ClothColliderResourceID | [ClothColliderBank](../ClothColliderBank/_REGION.md) | Cloth collision |
| Resource.IKRigResourceID | [IKRigBank](../IKRigBank/_REGION.md) | IK rig |
