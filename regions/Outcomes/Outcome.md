# Node: `Outcome`

> **Region**: [Outcomes](_REGION.md)
> **Folder**: `RandomCasts/`
> **Source**: `Shared/Public/Shared/RandomCasts/Outcomes.lsx`, also GustavDev, GustavX
> **Total Nodes**: ~23 (Shared; additional in other packs)

---

## Attributes

| Attribute | Type | Frequency | Examples | Notes |
|-----------|------|-----------|----------|-------|
| `UUID` | guid | x23 | `0d6df6f9-53cd-4928-80c5-1ad0a512c424` | Primary key |
| `GroupName` | FixedString | x23 | `WildMagic`, `WildMagicTurn` | Random cast group (determines trigger context) |
| `Spell` | FixedString | x23 | `Shout_WildMagic_Burning`, `Shout_WildMagic_Teleport` | Spell ID to cast |
| `Level` | uint32 | x14 | `2` | Minimum character level to trigger this outcome |
| `ClassLevel` | uint32 | x1 | `2` | Class-specific level requirement |
| `ClassUUID` | guid | x1 | `14374d37-a70e-41a8-9dc5-85a23f8b5dd2` | Class reference for class-level-gated outcomes |

## Child Nodes

None.

## Patterns of Use

- Defines Wild Magic surge outcomes (random cast effects)
- `GroupName` groups outcomes: `WildMagic` (standard surge) vs `WildMagicTurn` (turn-based trigger)
- `Level` gates some outcomes behind minimum character level (sparse — 14/23)
- `ClassLevel` + `ClassUUID` used for very specific class-gated outcomes (1 node only)
- Spell IDs are all `Shout_WildMagic_*` prefixed

## Caveats & Gotchas

- `Level`, `ClassLevel`, `ClassUUID` are sparse — not all outcomes have level requirements
- Multi-pack: GustavDev and GustavX may add additional outcomes

## Similarities to Other Nodes

None — unique random outcome system.
