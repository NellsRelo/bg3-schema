# Node: `CrowdCharacterClothsColors`

> **Region**: [CrowdCharacterClothsColors](_REGION.md)
> **Folder**: `CrowdCharacters/`
> **Vanilla entries**: 3 (SharedDev)

---

## Attributes

| Attribute | Type | Frequency | Examples | Notes |
|-----------|------|-----------|----------|-------|
| `UUID` | guid | 3/3 | `68126a94-...` | Primary key |
| `Name` | FixedString | 3/3 | `Poor`, `Rich`, `Rich_Patterned` | Clothing quality tier |

## Child Nodes

| Child | Frequency | Notes |
|-------|-----------|-------|
| `ClothsColors` | 30 total | Color palette entries |
| `ClothsPatterns` | 11 total | Pattern/texture entries |

## Patterns of Use

- Groups clothing color/pattern palettes by wealth tier.
- `Rich_Patterned` adds `ClothsPatterns` children for patterned fabrics.

## Cross-References

| From | To | Via |
|------|----|-----|
| CrowdCharacterTemplates | CrowdCharacterClothsColors | `ClothsColorsUUID` |

## Caveats & Gotchas

- `ClothsPatterns` only on the `Rich_Patterned` group.

## Similarities to Other Nodes

- **CrowdCharacterEyeColors/SkinColors**: Similar grouping structure.
