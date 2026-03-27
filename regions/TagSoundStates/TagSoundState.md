# Node: `TagSoundState`

> **Region**: [TagSoundStates](_REGION.md)
> **Folder**: `Sound/`
> **Vanilla entries**: 2 (Shared)

---

## Attributes

| Attribute | Type | Frequency | Examples | Notes |
|-----------|------|-----------|----------|-------|
| `UUID` | guid | 2/2 | `b2d426d2-...` | Primary key |
| `TagName` | FixedString | 2/2 | `REALLY_DARK_URGE`, `SHADOWHEART_ENEMYOFSHARPATH` | Tag name |
| `TagUUID` | guid | 2/2 | `cd611d7d-...` | References tag definition |
| `DefaultSwitch` | FixedString | 2/2 | `FALSE` | Wwise switch default state |
| `OverrideSwitch` | FixedString | 2/2 | `TRUE`, `True` | Wwise switch when tag present |
| `OverrideSwitchGroup` | FixedString | 2/2 | `Origin_DarkUrge`, `Shadowheart_EnemyOfShar` | Wwise switch group name |

## Child Nodes

*(None in vanilla data)*

## Patterns of Use

- Only 2 entries: Dark Urge and Shadowheart's Enemy of Shar path.
- Drives Wwise audio switches based on character tags.

## Cross-References

| From | To | Via |
|------|----|-----|
| TagSoundState | Tags | `TagUUID` |

## Caveats & Gotchas

- `OverrideSwitch` inconsistently cased: `TRUE` vs `True`.

## Similarities to Other Nodes

- **FlagSoundStates**: Identical schema but driven by flags.
- **StatusSoundStates**: Similar audio-state pattern for statuses.
