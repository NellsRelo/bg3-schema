# Node: `StatusSoundState`

> **Region**: [StatusSoundStates](_REGION.md)
> **Folder**: `Status/`
> **Vanilla entries**: 2 (Shared)

---

## Attributes

| Attribute | Type | Frequency | Examples | Notes |
|-----------|------|-----------|----------|-------|
| `UUID` | guid | 2/2 | `7adcc1d1-...` | Primary key |
| `SoundStateName` | FixedString | 2/2 | `RAGE`, `CANT_VOCAL` | Status identifier for audio |
| `BlockVocals` | bool | 1/2 | `true` | Whether to block vocal sounds |
| `CombatVocalOverrideSwitch` | FixedString | 1/2 | `Critical` | Override combat vocal Wwise switch |
| `SpellOverrideSwitchGroup` | FixedString | 1/2 | `Rage_NormalAttack` | Wwise switch group for spell audio |
| `SpellOverrideSwitchState` | FixedString | 1/2 | `Rage` | Active Wwise switch state |
| `SpellOverrideSwitchClearState` | FixedString | 1/2 | `Neutral` | Wwise switch state when status clears |

## Child Nodes

*(None in vanilla data)*

## Patterns of Use

- `RAGE`: Overrides spell audio to rage sounds, overrides combat vocals to Critical.
- `CANT_VOCAL`: Simply blocks vocal sounds (e.g., Silence status).

## Cross-References

| From | To | Via |
|------|----|-----|
| StatusSoundState | Statuses (stats) | `SoundStateName` |

## Caveats & Gotchas

- Most attributes are only on 1 of 2 entries — highly sparse.

## Similarities to Other Nodes

- **FlagSoundStates**: Similar Wwise audio pattern.
- **TagSoundStates**: Similar Wwise audio pattern.
