# Node: `MultiEffectInfos`

> **Region**: [MultiEffectInfos](_REGION.md)
> **Source**: `Gustav/Public/Gustav/MultiEffectInfos/<UUID>.lsx` (one file per entry)

---

## Attributes

| Attribute | Type | Frequency | Examples | Notes |
|-----------|------|-----------|----------|-------|
| `Name` | LSString | always | *(descriptive name)* | Human-readable multi-effect name |
| `UUID` | guid | always | — | Primary key (also the filename) |

## Child Nodes

### EffectInfo

Each `MultiEffectInfos` node contains one or more `EffectInfo` children describing individual VFX attachments:

| Attribute | Type | Frequency | Notes |
|-----------|------|-----------|-------|
| `BindSourceTo` | FixedString | sparse | Source bone/socket to bind effect origin |
| `BindTargetTo` | FixedString | sparse | Target bone/socket to bind effect destination |
| `DetachSource` | bool | sparse | Detach effect from source on completion |
| `DetachTarget` | bool | sparse | Detach effect from target on completion |
| `EffectResourceGuid` | guid | always | Reference to the VFX resource |
| `KeepRotation` | bool | sparse | Maintain rotation after detach |
| `KeepScale` | bool | sparse | Maintain scale after detach |
| `MainHand` | bool | sparse | Apply to main hand |
| `MaxDistance` | float | sparse | Maximum activation distance |
| `MinDistance` | float | sparse | Minimum activation distance |
| `OffHand` | bool | sparse | Apply to off hand |
| `Pivot` | FixedString | sparse | Pivot point reference |
| `UUID` | guid | always | EffectInfo primary key |
| `UseDistance` | bool | sparse | Enable distance-based activation |
| `UseOrientDirection` | bool | sparse | Orient effect along direction |
| `UseScaleOverride` | bool | sparse | Override scale from parent |

#### EffectInfo Sub-children

- **TargetBone**: `<attribute id="Value" type="LSString" value="..." />` — target bone name
- **TargetSkeletonSlot**: `<attribute id="Value" type="LSString" value="..." />` — target skeleton slot

## Vanilla Scope

| Pack | Files |
|------|-------|
| Gustav | ~160 |

UUID-named per-file collection (like [Flags](../Flags/Flags.md)). Each file defines a multi-effect bundle grouping several VFX attachments with bone targeting and distance/orientation rules.

## Cross-References

| From | To | Via |
|------|----|-----|
| — | — | — |

## Caveats & Gotchas

*(To be documented)*

## Similarities to Other Nodes

*(To be documented)*
