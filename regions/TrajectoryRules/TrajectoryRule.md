# Node: `TrajectoryRule`

> **Region**: [TrajectoryRules](_REGION.md)
> **Source**: `Shared/Public/Shared/TrajectoryRules/Projectiles.lsx`

---

## Attributes

| Attribute | Type | Frequency | Examples | Notes |
|-----------|------|-----------|----------|-------|
| `HeightMax` | float | always | `1`, `999`, `-1` | Maximum height threshold |
| `HeightMin` | float | always | `-1`, `1`, `-999` | Minimum height threshold |
| `LengthMax` | float | always | `999` | Maximum distance |
| `LengthMin` | float | always | `0` | Minimum distance |
| `Priority` | int32 | always | `1`, `2`, `3` | Rule evaluation priority (lower = first) |
| `Template` | FixedString | always | *(guid)* | Trajectory template resource reference |
| `UUID` | guid | always | — | Primary key |

## Child Nodes

*(None)*

## Vanilla Scope

| Pack | Nodes |
|------|-------|
| Shared | 3 |

Three rules selecting projectile trajectory templates based on height difference and distance ranges. Priority determines which rule applies when ranges overlap.
See also [SpellSoundTrajectoryRule](../SpellSoundTrajectoryRules/SpellSoundTrajectoryRule.md) for the audio-side counterpart.

## Cross-References

| From | To | Via |
|------|----|-----|
| — | — | — |

## Caveats & Gotchas

*(To be documented)*

## Similarities to Other Nodes

*(To be documented)*
