# Node: `Resource`

> **Region**: [AnimationBank](_REGION.md)
> **Child Depth**: 1 (flat — no child nodes)

---

## Attributes

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `ID` | FixedString | UUID primary key | `0633bd42-4d72-6581-e111-5e64f7fc55f8` |
| `Name` | LSString | Animation name (convention driven) | `BIRD_Eagle_Rig_CINE_Idle_01` |
| `SourceFile` | LSString | GR2 source path | `Public/Shared/Assets/.../_Construction/....GR2` |
| `Template` | FixedString | Animation template ref | `Public/Shared/Assets/.../_Construction/....Anim.0` |
| `SkeletonResource` | FixedString | UUID → [SkeletonBank](../SkeletonBank/_REGION.md) | `9b42fe29-1ad4-bf0c-4149-054d7f4eadde` |
| `PreviewVisualResource` | FixedString | UUID → [VisualBank](../VisualBank/_REGION.md) (editor preview) | `2ec332b3-5f3a-f7d9-0b80-4d6b6aad380a` |
| `Duration` | float | Clip duration in seconds | `16.666668` |
| `TimeStep` | float | Time step per frame | `0.005555556` |
| `Looping` | bool | Whether animation loops | `False` |
| `IsPoseBank` | bool | Is this a pose (static frame) | `False` |
| `Offset` | float | Start offset | `0` |
| `SupportingLeg` | uint8 | Which leg supports (IK hint) | `0` |
| `AnchorHand` | uint8 | Which hand anchors (weapon hand) | `0` |
| `LeftTransitionAnimation` | FixedString | UUID → AnimationBank (left transition) | _(empty)_ |
| `RightTransitionAnimation` | FixedString | UUID → AnimationBank (right transition) | _(empty)_ |
| `AdditiveLoopingAnimationID` | FixedString | _(optional)_ Additive loop overlay | _(empty)_ |
| `AdditiveLoopingBlendTime` | float | _(optional)_ Additive blend time | `0` |
| `AdditiveLoopingStart` | float | _(optional)_ Additive start time | `0` |
| `Localized` | bool | _(optional)_ Localization flag | `False` |
| `_OriginalFileVersion_` | int64 | Engine version stamp | `144115205255725257` |

## Child Nodes

_(None — flat resource structure)_

## Cross-References

| From | To | Via |
|------|----|-----|
| Resource.ID | [AnimationSetBank](../AnimationSetBank/_REGION.md) | `Animation.Object.ID` |
| Resource.ID | [VisualBank](../VisualBank/_REGION.md) | `AnimationWaterfall.Object` |
| Resource.SkeletonResource | [SkeletonBank](../SkeletonBank/_REGION.md) | Skeleton binding |
| Resource.PreviewVisualResource | [VisualBank](../VisualBank/_REGION.md) | Editor preview mesh |
