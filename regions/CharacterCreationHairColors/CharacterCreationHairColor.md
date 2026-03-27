# Node: `CharacterCreationHairColor`

> **Region**: [CharacterCreationHairColors](_REGION.md)
> **Folder**: `CharacterCreationPresets/`
> **Vanilla entries**: 125 (Shared)

---

## Attributes

| Attribute | Type | Frequency | Examples | Notes |
|-----------|------|-----------|----------|-------|
| `UUID` | guid | 125/125 | `0206c920-...` | Primary key |
| `Name` | FixedString | 125/125 | `HAIR_Color_Blonde_0`, `HAIR_Color_Blonde_1` | Internal name |
| `DisplayName` | TranslatedString | 125/125 | handle `ha197...` | Shown in CC UI |
| `MaterialPresetUUID` | guid | 125/125 | `b6d28fbc-...` | References material preset for hair texture |
| `UIColor` | LSString | 125/125 | `#FFFFD3AD`, `#FFE6B99A` | Hex ARGB color for UI swatch |

## Child Nodes

*(None in vanilla data)*

## Patterns of Use

- All 125 entries have all attributes — no optional fields.
- Names follow pattern `HAIR_Color_Blonde_0`, `HAIR_Color_Black_0`, etc.

## Cross-References

| From | To | Via |
|------|----|-----|
| CharacterCreationPresets | CharacterCreationHairColor | `HairColorUUID` |
| MaterialPresetBank | CharacterCreationHairColor | `MaterialPresetUUID` |

## Caveats & Gotchas

- `UIColor` type is `LSString`, not a dedicated color type.

## Similarities to Other Nodes

- **CharacterCreationEyeColor**: Identical attribute schema.
- **CharacterCreationSkinColor**: Identical attribute schema.
