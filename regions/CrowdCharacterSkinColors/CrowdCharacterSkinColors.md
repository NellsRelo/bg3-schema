# Node: `CrowdCharacterSkinColors`

> **Region**: [CrowdCharacterSkinColors](_REGION.md)
> **Folder**: `CrowdCharacters/`
> **Vanilla entries**: 3 (SharedDev)

---

## Attributes

| Attribute | Type | Frequency | Examples | Notes |
|-----------|------|-----------|----------|-------|
| `UUID` | guid | 3/3 | `abd89b8b-...` | Primary key |
| `Name` | FixedString | 3/3 | `Humans`, `Dwarves`, `Halflings` | Race group name |

## Child Nodes

| Child | Frequency | Notes |
|-------|-----------|-------|
| `SkinColors` | 77 total | Individual skin color entries per race |

## Patterns of Use

- Groups skin color palettes by race for crowd NPCs.
- Same 3 races as eye colors.

## Cross-References

| From | To | Via |
|------|----|-----|
| CrowdCharacterTemplates | CrowdCharacterSkinColors | `SkinColorsUUID` |

## Caveats & Gotchas

- Only for crowd NPCs; player characters use `CharacterCreationSkinColors`.

## Similarities to Other Nodes

- **CrowdCharacterEyeColors**: Identical structure.
- **CrowdCharacterClothsColors**: Similar grouping pattern.
