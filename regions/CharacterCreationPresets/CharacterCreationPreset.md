# Node: `CharacterCreationPreset`

> **Region**: [CharacterCreationPresets](_REGION.md)
> **Folder**: `CharacterCreationPresets/`

---

## Attributes

> 58 nodes in Shared (vanilla)

| Attribute | Type | Count | Examples | Notes |
|-----------|------|-------|----------|-------|
| `UUID` | guid | 58/58 | `94bc7b1d-70e4-476a-9c99-24b90d9f2083` | Primary key |
| `BodyShape` | uint8 | 58/58 | `0`, `1` | Body build (0=Regular, 1=Strong) |
| `BodyType` | uint8 | 58/58 | `0`, `1` | Body type (0=Masculine, 1=Feminine) |
| `RaceUUID` | guid | 58/58 | links to Race.UUID | Race this preset belongs to |
| `SubRaceUUID` | guid | 58/58 | links to Race.UUID (sub-race) | Sub-race for this preset |
| `RootTemplate` | guid | 58/58 | `f08563b3-748d-4783-837b-b8620bc60b22` | Character template |
| `VOLinesTableUUID` | guid | 58/58 | `14df8f45-90af-4bd0-8024-42624da9976e` | Voice lines table reference |
| `CloseUpA` | LSString | 58/58 | `ELF_F_Camera_Closeup_A` | CC camera angle A |
| `CloseUpB` | LSString | 58/58 | `ELF_F_Camera_Closeup_B` | CC camera angle B |
| `Overview` | LSString | 58/58 | `ELF_F_Camera_Overview_A` | CC overview camera |

## Cross-References

| From | To | Via |
|------|----|-----|
| CCPreset.RaceUUID | [Race](../Races/Race.md) | Race.UUID |
| CCPreset.SubRaceUUID | [Race](../Races/Race.md) | Race.UUID (sub-race) |
| CCPreset.VOLinesTableUUID | [CCVOLine](../CharacterCreationVOLines/CharacterCreationVOLine.md) | VOLine.TableUUID |
| CCPreset.RootTemplate | Templates | GameObjects.MapKey |

## Caveats & Gotchas

- Every race/sub-race × body shape × body type combination has a preset.
- Camera names encode race, gender, and angle: `{RACE}_{GENDER}_Camera_{Type}_{Variant}`.
- All attributes (except UUID) are present on all 58 entries — no optional fields.

## Cross-References

| From | To | Via |
|------|----|-----|
| — | — | — |

## Caveats & Gotchas

*(To be documented)*

## Similarities to Other Nodes

*(To be documented)*
