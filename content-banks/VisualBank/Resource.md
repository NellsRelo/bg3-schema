# Node: `Resource`

> **Region**: [VisualBank](_REGION.md)
> **Child Depth**: 3 (Resource → Objects, ClothParams, etc.)

---

## Node Hierarchy

```
Resource                              ← one per visual mesh/model
├── AnimationWaterfall                 ← repeated (animation refs)
├── AnimationSetOverrides              ← animation set override map
│   └── (PairElement1/PairElement2 mapped)
├── Attachments                        ← attachment container
├── Base                               ← empty marker node
├── ClothParams                        ← repeated (cloth physics per mesh)
├── ClothProxyMapping                  ← proxy map container
│   └── Object (MapKey)
│       └── MapValue → Object
├── Objects                            ← repeated (LOD mesh entries)
├── Tags                               ← repeated
└── VertexColorMaskSlots               ← repeated (body region masks)
```

## Attributes

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `ID` | FixedString | UUID primary key | `9468fe74-1ae3-df0c-70f6-6a7313a095e9` |
| `Name` | LSString | Display name | `ELEM_Grease_Head_A` |
| `SourceFile` | LSString | GR2 source path | `Generated/Public/Shared/Assets/.../file.GR2` |
| `Template` | FixedString | Template reference (mesh root) | `Generated/.../ELEM_Mud_Head_A.Dummy_Root.0` |
| `SkeletonResource` | FixedString | UUID → [SkeletonBank](../SkeletonBank/_REGION.md) | `6e822843-65c9-84bc-9349-75505e1178c0` |
| `BlueprintInstanceResourceID` | FixedString | UUID → [AnimationBlueprintBank](../AnimationBlueprintBank/_REGION.md) | `dcd733b9-a3b7-6064-4741-587385c33e33` |
| `ClothColliderResourceID` | FixedString | UUID → [ClothColliderBank](../ClothColliderBank/_REGION.md) | _(empty or UUID)_ |
| `SoftbodyResourceID` | FixedString | Softbody physics ref | _(empty or UUID)_ |
| `HairPresetResourceId` | FixedString | Hair preset ref | _(empty or UUID)_ |
| `HairType` | uint8 | Hair rendering type | `0` |
| `Slot` | FixedString | Equipment/body slot | `Head`, `Body` |
| `SkeletonSlot` | FixedString | Skeleton slot index | `1`, `` |
| `RemapperSlotId` | FixedString | Remapper slot ref | _(empty)_ |
| `ScalpMaterialId` | FixedString | Scalp material for bald transitions | _(empty or UUID)_ |
| `AttachBone` | FixedString | Bone to attach to | _(empty)_ |
| `AttachmentSkeletonResource` | FixedString | Attachment skeleton ref | _(empty)_ |
| `BoundsMax` | fvec3 | AABB max corner | `0.5877333 4.4921784 0.9691809` |
| `BoundsMin` | fvec3 | AABB min corner | `-0.8485812 2.5789838 -1.2285966` |
| `MaterialType` | uint8 | Material type flag | `0` |
| `NeedsSkeletonRemap` | bool | Whether skeleton remapping is needed | `False` |
| `SupportsVertexColorMask` | bool | Body region masking support | `False`, `True` |
| `Localized` | bool | Localization flag | `False` |
| `_OriginalFileVersion_` | int64 | Engine version stamp | `144115207403209009` |

## Child: Objects (LOD Meshes)

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `LOD` | uint8 | Level of detail (0 = highest) | `0`, `1`, `2`, `3` |
| `MaterialID` | FixedString | UUID → [MaterialBank](../MaterialBank/_REGION.md) | `cce6d925-baad-94a8-c09f-cee6fe9a3686` |
| `ObjectID` | FixedString | Mesh object identifier | `ELEM_Mud_Head_A.ELEM_Mud_Head_A_Mesh.0` |

## Child: AnimationWaterfall

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `Object` | FixedString | UUID → [AnimationSetBank](../AnimationSetBank/_REGION.md) or [AnimationBank](../AnimationBank/_REGION.md) | `eeff696b-04e8-1a83-66fd-d89483eeb1f1` |

## Child: ClothParams (Physics Simulation)

Extensive cloth simulation parameters per mesh. Key attributes:

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `AnimDriveDampingForce` | float | Animation drive damping | `150` |
| `AnimDriveSpringForce` | float | Animation drive spring | `200` |
| `BendingStiffness` | float | Cloth bending resistance | `1` |
| `Damping` | fvec3 | Damping per axis | `0.03 0.03 0.03` |
| `Friction` | float | Surface friction | `0.1` |
| `AtmosphericWindEnabled` | bool | Wind interaction | `False` |
| `ClothMainWindSpeed` | float | Wind speed for cloth | `0` |
| `ClothWindSpeed` | float | Cloth-specific wind | `0` |
| `LinearDrag` | fvec3 | Linear drag per axis | `0.0001 0.0001 0.0001` |
| `AngularDrag` | fvec3 | Angular drag per axis | `0.0001 0.0001 0.0001` |
| `CollisionMassScale` | float | Collision mass scaling | `1` |
| `CompressionLimit` | float | Compression constraint | `0.8` |

_(Full list includes ~30 cloth physics attributes)_

## Cross-References

| From | To | Via |
|------|----|-----|
| Resource.ID | [CharacterVisualBank](../CharacterVisualBank/_REGION.md) | `Slots.VisualResource` |
| Resource.ID | [TileSetBank](../TileSetBank/_REGION.md) | `Tile.VisualGUID` |
| Resource.ID | [SplineSetBank](../SplineSetBank/_REGION.md) | `Tile.VisualGUID` |
| Resource.SkeletonResource | [SkeletonBank](../SkeletonBank/_REGION.md) | Skeleton binding |
| Resource.BlueprintInstanceResourceID | [AnimationBlueprintBank](../AnimationBlueprintBank/_REGION.md) | Animation blueprint |
| Resource.Objects.MaterialID | [MaterialBank](../MaterialBank/_REGION.md) | Mesh material |
| Resource.AnimationWaterfall.Object | [AnimationSetBank](../AnimationSetBank/_REGION.md) | Animation waterfall |
| GameObjects.VisualTemplate | Resource.ID | World object visual |
