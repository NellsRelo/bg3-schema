# Node: `CinematicArenaFrequencyGroup`

> **Region**: [CinematicArenaFrequencyGroups](_REGION.md)
> **Folder**: `CinematicArenaFrequencyGroups/`
> **Source**: `Shared/Public/Shared/CinematicArenaFrequencyGroups/CinematicArenaFrequencyGroups.lsx`
> **Total Nodes**: ~8 (Shared only)

---

## Attributes

| Attribute | Type | Frequency | Examples | Notes |
|-----------|------|-----------|----------|-------|
| `UUID` | guid | x8 | `18ee16a3-c553-4bfc-a1b8-f625cf3ba68f` | Primary key |
| `Name` | FixedString | x8 | `Always`, `Critical Hit`, `Death` | Event category name |
| `MaxFrequency` | double | x8 | `0`, `10`, `20` | Max frequency threshold |
| `PercentageChance` | int32 | x8 | `100`, `35`, `30` | Chance (%) to trigger cinematic for this event |

## Child Nodes

None.

## Patterns of Use

- Controls how often cinematic camera angles trigger for different combat events
- `Always` group has `PercentageChance=100` and `MaxFrequency=0` (no cooldown)
- Other events (Critical Hit, Death) have lower chances and frequency limits to avoid repetition

## Caveats & Gotchas

- `MaxFrequency` of 0 means no limit on how often the cinematic can play

## Similarities to Other Nodes

Related to `CombatCameraGroup` which also controls combat cinematic behavior.
