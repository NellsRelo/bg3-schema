# Node: `CharacterCreationVOLine`

> **Region**: [CharacterCreationVOLines](_REGION.md)
> **Folder**: `CharacterCreation/`

---

## Attributes

> 11 nodes in Shared (vanilla)

| Attribute | Type | Count | Examples | Notes |
|-----------|------|-------|----------|-------|
| `UUID` | guid | 11/11 | `365f4a6e-eada-4235-a731-835428e3b0a3` | Primary key |
| `TableUUID` | guid | 11/11 | `14df8f45-90af-4bd0-8024-42624da9976e` | Voice table reference |
| `VoiceLine` | FixedString | 11/11 | `h83d4c80dg70b4g4ab6g97dfg0878d5e8f473` | TranslatedString handle for the VO line |

## Cross-References

| From | To | Via |
|------|----|-----|
| [CCPreset](../CharacterCreationPresets/CharacterCreationPreset.md).VOLinesTableUUID | CCVOLine.TableUUID | Voice line table lookup |

## Caveats & Gotchas

- `VoiceLine` contains a TranslatedString handle (format `h...g...g...g...g...`) but is stored as FixedString, not TranslatedString type.
- `TableUUID` groups VO lines into voice tables referenced by CC Presets.

## Cross-References

| From | To | Via |
|------|----|-----|
| — | — | — |

## Caveats & Gotchas

*(To be documented)*

## Similarities to Other Nodes

*(To be documented)*
