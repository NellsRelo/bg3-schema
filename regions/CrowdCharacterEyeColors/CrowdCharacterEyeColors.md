# Node: `CrowdCharacterEyeColors`

> **Region**: [CrowdCharacterEyeColors](_REGION.md)
> **Folder**: `CrowdCharacters/`
> **Vanilla entries**: 3 (SharedDev)

---

## Attributes

| Attribute | Type | Frequency | Examples | Notes |
|-----------|------|-----------|----------|-------|
| `UUID` | guid | 3/3 | `f676fed7-...` | Primary key |
| `Name` | FixedString | 3/3 | `Humans`, `Dwarves`, `Halflings` | Race group name |

## Child Nodes

| Child | Frequency | Notes |
|-------|-----------|-------|
| `EyeColors` | 15 total | Individual eye color entries for each race |

## Patterns of Use

- Groups eye color palettes by race for crowd NPCs.
- Each entry contains child `EyeColors` nodes with actual color values.

## Cross-References

| From | To | Via |
|------|----|-----|
| CrowdCharacterTemplates | CrowdCharacterEyeColors | `EyeColorsUUID` |

## Caveats & Gotchas

- Only for crowd NPCs; player characters use `CharacterCreationEyeColors`.

## Similarities to Other Nodes

- **CrowdCharacterSkinColors**: Same structure (Name + UUID + color children).
- **CrowdCharacterClothsColors**: Similar grouping pattern.
