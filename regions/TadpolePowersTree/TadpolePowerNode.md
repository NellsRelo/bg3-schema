# Node: `TadpolePowerNode`

> **Region**: [TadpolePowersTree](_REGION.md)
> **Folder**: `TadpolePowers/`
> **Vanilla entries**: 26 (SharedDev)

---

## Attributes

| Attribute | Type | Frequency | Examples | Notes |
|-----------|------|-----------|----------|-------|
| `UUID` | guid | 26/26 | `2b43bbd0-...` | Primary key |
| `Name` | FixedString | 26/26 | `TAD_IllithidPersuasion`, `Shout_TAD_PsionicOverload`, `TAD_PeaceBreaker` | Illithid power name |
| `NeedsHalfIllithidToUnlock` | bool | 10/26 | `true` | Requires partial ceremorphosis to unlock |

## Child Nodes

| Child | Frequency | Notes |
|-------|-----------|-------|
| `PrerequisiteUUIDs` | 45 total | Other TadpolePowerNode UUIDs that must be unlocked first |

## Patterns of Use

- Defines the illithid powers skill tree for tadpole abilities.
- `Name` references passive/spell stat entries.
- `NeedsHalfIllithidToUnlock` marks advanced powers (10 of 26).
- `PrerequisiteUUIDs` children form the directed graph of the unlock tree.

## Cross-References

| From | To | Via |
|------|----|-----|
| TadpolePowerNode | TadpolePowerNode (prereq) | `PrerequisiteUUIDs` children |
| TadpolePowerNode | Passives / Spells (stats) | `Name` |

## Caveats & Gotchas

- Only in SharedDev pack.
- `PrerequisiteUUIDs` children reference other TadpolePowerNode UUIDs (DAG structure).

## Similarities to Other Nodes

*(None)*
