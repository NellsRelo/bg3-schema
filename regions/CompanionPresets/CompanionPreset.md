# Node: `CompanionPreset`

> **Region**: [CompanionPresets](_REGION.md)
> **Folder**: `CharacterCreationPresets/`
> **Vanilla entries**: 60 (Gustav; also present in GustavDev and Shared)

---

## Attributes

| Attribute | Type | Frequency | Examples | Notes |
|-----------|------|-----------|----------|-------|
| `UUID` | guid | 60/60 | `fd3b6992-...` | Primary key |
| `BodyShape` | uint8 | 60/60 | `0`, `1` | 0=Normal, 1=Strong |
| `BodyType` | uint8 | 60/60 | `0`, `1` | 0=Masculine, 1=Feminine |
| `RaceUUID` | guid | 60/60 | `4f5d1434-...` | References Races region |
| `SubRaceUUID` | guid | 60/60 | `c5f8ebdd-...` | References SubRace |
| `RootTemplate` | guid | 60/60 | `7231948a-...` | References GameObjects template |
| `VoiceTableUUID` | guid | 60/60 | `60e91119-...` | References voice table |
| `VOLinesTableUUID` | guid | 60/60 | `eec1dacc-...` | References CC VO lines |
| `CloseUpA` | LSString | 60/60 | `ELF_M_Camera_CompanionCloseup_A` | Camera preset name for close-up A |
| `CloseUpB` | LSString | 60/60 | `ELF_M_Camera_CompanionCloseup_B` | Camera preset name for close-up B |
| `Overview` | LSString | 60/60 | `ELF_M_Camera_CompanionOverview_A` | Camera preset name for overview |

## Child Nodes

*(None in vanilla data)*

## Patterns of Use

- All 60 entries have all attributes — no optional fields.
- Camera preset names follow pattern: `{RACE}_{GENDER}_Camera_Companion{Type}_{Variant}`.
- Each companion has multiple presets for different race/body combinations in CC.

## Cross-References

| From | To | Via |
|------|----|-----|
| CompanionPreset | Races | `RaceUUID` |
| CompanionPreset | Races (SubRace) | `SubRaceUUID` |
| CompanionPreset | GameObjects | `RootTemplate` |
| CompanionPreset | CharacterCreationVOLines | `VOLinesTableUUID` |

## Caveats & Gotchas

- Camera names are `LSString`, not GUIDs — they reference camera definitions by name.

## Similarities to Other Nodes

- **CharacterCreationPresets**: Similar CC preset structure but for player characters.
