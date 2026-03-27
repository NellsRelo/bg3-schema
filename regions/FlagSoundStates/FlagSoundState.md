# Node: `FlagSoundState`

> **Region**: [FlagSoundStates](_REGION.md)
> **Folder**: `Sound/`
> **Vanilla entries**: 8 (Shared)

---

## Attributes

| Attribute | Type | Frequency | Examples | Notes |
|-----------|------|-----------|----------|-------|
| `UUID` | guid | 8/8 | `57f42d2c-...` | Primary key |
| `FlagName` | FixedString | 8/8 | `ORI_Astarion_State_BecameVampireLord` | Story flag name |
| `FlagUUID` | guid | 8/8 | `c446ce94-...` | References flag definition |
| `DefaultSwitch` | FixedString | 8/8 | `FALSE` | Wwise switch default state |
| `OverrideSwitch` | FixedString | 8/8 | `TRUE` | Wwise switch when flag is set |
| `OverrideSwitchGroup` | FixedString | 8/8 | `Astarion_BecameVampireLord` | Wwise switch group name |

## Child Nodes

*(None in vanilla data)*

## Patterns of Use

- All 8 entries are companion story state flags (Astarion, Lae'zel, Shadowheart, Karlach, Wyll, Gale).
- Drives audio switch changes (Wwise) based on story progression.

## Cross-References

| From | To | Via |
|------|----|-----|
| FlagSoundState | Flags | `FlagUUID` |

## Caveats & Gotchas

- Wwise-specific: `DefaultSwitch`/`OverrideSwitch`/`OverrideSwitchGroup` are audio middleware params.

## Similarities to Other Nodes

- **TagSoundStates**: Identical schema but driven by tags instead of flags.
- **StatusSoundStates**: Similar audio-state pattern for status effects.
