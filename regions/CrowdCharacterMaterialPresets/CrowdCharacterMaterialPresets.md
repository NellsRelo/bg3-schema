# Node: `CrowdCharacterMaterialPresets`

> **Region**: [CrowdCharacterMaterialPresets](_REGION.md)
> **Folder**: `CrowdCharacters/`
> **Vanilla entries**: 31 (SharedDev)

---

## Attributes

| Attribute | Type | Frequency | Examples | Notes |
|-----------|------|-----------|----------|-------|
| `UUID` | guid | 31/31 | `bc10158e-...` | Primary key |
| `Name` | FixedString | 31/31 | `CROWD_Pattern_0_0`, `CROWD_Pattern_0_1` | Pattern identifier |
| `MaterialPresetUUID` | guid | 31/31 | `9b1486c5-...` | References material preset for clothing texture |

## Child Nodes

*(None in vanilla data)*

## Patterns of Use

- 31 material presets for crowd NPC clothing patterns.
- Names follow `CROWD_Pattern_{Group}_{Index}` pattern.

## Cross-References

| From | To | Via |
|------|----|-----|
| CrowdCharacterMaterialPresets | MaterialPresetBank | `MaterialPresetUUID` |

## Caveats & Gotchas

- Only for crowd NPCs.

## Similarities to Other Nodes

- **CharacterCreationAppearanceMaterials**: Similar material preset reference pattern.
