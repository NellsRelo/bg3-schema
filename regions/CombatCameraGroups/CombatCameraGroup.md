# Node: `CombatCameraGroup`

> **Region**: [CombatCameraGroups](_REGION.md)
> **Folder**: `CombatCameraGroups/`
> **Source**: `Shared/Public/Shared/CombatCameraGroups/CombatCameraGroups.lsx`
> **Total Nodes**: ~3 (Shared only)

---

## Attributes

| Attribute | Type | Frequency | Examples | Notes |
|-----------|------|-----------|----------|-------|
| `UUID` | guid | x3 | `1608525c-d81f-4a89-a734-a1f4b1338ea8` | Primary key |
| `Name` | FixedString | x3 | `Death`, `RangedAttack`, `MeleeAttack` | Combat camera event type |

## Child Nodes

| Child | Count | Description |
|-------|-------|-------------|
| `TimelineGUIDs` | x3 | Timeline references for each combat camera group (one per node) |

## Patterns of Use

- Defines groups of timeline animations for combat camera shots
- 3 categories: Death, RangedAttack, MeleeAttack
- Each group has `TimelineGUIDs` children that reference specific timeline animations
- Used with `CinematicArenaFrequencyGroup` to control combat camera behavior

## Caveats & Gotchas

- Only 3 entries — fixed set of combat camera categories

## Similarities to Other Nodes

Paired with `CinematicArenaFrequencyGroup` for combat cinematic system.
