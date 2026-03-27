# Node: `Resource`

> **Region**: [SoundBank](_REGION.md)
> **Child Depth**: 1 (flat — no child nodes)

---

## Attributes

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `ID` | FixedString | UUID primary key | `007cf46b-0179-4145-9765-a3f257e8f387` |
| `Name` | LSString | Sound name | `Action_Loop_ArcaneArcher_GraspingArrow_Stop_01` |
| `SoundEvent` | FixedString | Wwise event name | `Action_Loop_ArcaneArcher_GraspingArrow_Stop_01` |
| `SoundEventID` | uint32 | Wwise event hash ID | `2998283788` |
| `SoundEventUUID` | guid | Sound event UUID | `0e76e27e-4727-4ebe-8671-151056823e72` |
| `SoundBank` | FixedString | Parent Wwise bank name | `ACTIONS` |
| `SourceFile` | LSString | Wwise bank file (.bnk) | `Public/Shared/Assets/Sound/ACTIONS.bnk` |
| `Duration` | float | Sound duration in seconds (-1 = looping) | `5.930666`, `-1` |
| `MaxDistance` | float | Maximum audible distance (0 = unlimited) | `50`, `0` |
| `SoundCategory` | int8 | Sound category enum | `0` |
| `SoundCodec` | int8 | Audio codec enum | `7` |
| `Preload` | bool | Pre-load audio data | `False` |
| `Internal` | bool | Internal engine sound | `True` |
| `DisplayName` | LSString | _(optional)_ UI display name | _(empty)_ |
| `GMSoundCategory` | int8 | _(optional)_ Game Master category | `0` |
| `GMSubSection` | LSString | _(optional)_ Game Master UI section | _(empty)_ |
| `Localized` | bool | Localization flag | `False` |
| `_OriginalFileVersion_` | int64 | Engine version stamp | `144115205255725357` |

## Child Nodes

_(None — flat resource structure)_

## Cross-References

| From | To | Via |
|------|----|-----|
| Resource.ID | [SkeletonBank](../SkeletonBank/_REGION.md) | `Bones.MapValue.SoundObjectIndex` |
| Resource.SoundEventID | Wwise audio engine | Runtime sound playback |

## Notes

- `SoundCodec` value `7` appears to be the standard codec
- `Duration = -1` indicates a looping sound
