# Node: `SpellSoundTrajectoryRule`

> **Region**: [SpellSoundTrajectoryRules](_REGION.md)
> **Source**: `Shared/Public/Shared/TrajectoryRules/SpellSoundTrajectoryRules.lsx`

---

## Attributes

| Attribute | Type | Frequency | Examples | Notes |
|-----------|------|-----------|----------|-------|
| `RuleName` | FixedString | always | `Big`, `Normal`, `Small` | Size category name |
| `CurveUUID` | FixedString | sparse (×3 of 5) | *(guid-like)* | Sound curve reference |
| `DistancePastListener` | float | sparse (×3 of 5) | *(numeric)* | Distance threshold past listener |
| `UUID` | guid | always | — | Primary key |

## Child Nodes

*(None)*

## Vanilla Scope

| Pack | Nodes |
|------|-------|
| Shared | 5 |

Maps spell projectile size categories (Big/Normal/Small) to audio trajectory curves that control how spell sounds travel past the listener.

## Cross-References

| From | To | Via |
|------|----|-----|
| — | — | — |

## Caveats & Gotchas

*(To be documented)*

## Similarities to Other Nodes

*(To be documented)*
