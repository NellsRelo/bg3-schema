# Node: `CharacterCreationSkinColor`

> **Region**: [CharacterCreationSkinColors](_REGION.md)
> **Folder**: `CharacterCreationPresets/`
> **Vanilla entries**: 334 (Shared)

---

## Attributes

| Attribute | Type | Frequency | Examples | Notes |
|-----------|------|-----------|----------|-------|
| `UUID` | guid | 334/334 | `a359ed69-...` | Primary key |
| `Name` | FixedString | 334/334 | `HUM_Neutral_-2`, `HUM_Neutral_0` | Internal name; race-prefixed |
| `DisplayName` | TranslatedString | 334/334 | handle `h57a7...` | Shown in CC UI |
| `MaterialPresetUUID` | guid | 334/334 | `42f29250-...` | References material preset for skin texture |
| `UIColor` | LSString | 334/334 | `#FFFFF0E6`, `#FFFFE1CD` | Hex ARGB color for UI swatch |

## Child Nodes

*(None in vanilla data)*

## Patterns of Use

- All 334 entries have all attributes — no optional fields.
- Names are race-prefixed: `HUM_Neutral_-2`, `TIF_Neutral_0`, `DWR_Neutral_0`, etc.
- Largest of the three CC color regions (334 vs 145 eye, 125 hair).

## Cross-References

| From | To | Via |
|------|----|-----|
| CharacterCreationPresets | CharacterCreationSkinColor | `SkinColorUUID` |
| MaterialPresetBank | CharacterCreationSkinColor | `MaterialPresetUUID` |

## Caveats & Gotchas

- `UIColor` type is `LSString`, not a dedicated color type.

## Similarities to Other Nodes

- **CharacterCreationEyeColor**: Identical attribute schema.
- **CharacterCreationHairColor**: Identical attribute schema.
