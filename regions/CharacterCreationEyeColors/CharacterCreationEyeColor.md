# Node: `CharacterCreationEyeColor`

> **Region**: [CharacterCreationEyeColors](_REGION.md)
> **Folder**: `CharacterCreationPresets/`
> **Vanilla entries**: 145 (Shared)

---

## Attributes

| Attribute | Type | Frequency | Examples | Notes |
|-----------|------|-----------|----------|-------|
| `UUID` | guid | 145/145 | `d19b8c63-...` | Primary key |
| `Name` | FixedString | 145/145 | `Natural Brown A`, `Natural Brown B` | Internal name |
| `DisplayName` | TranslatedString | 145/145 | handle `h19d2...` | Shown in CC UI |
| `MaterialPresetUUID` | guid | 145/145 | `93cb58ae-...` | References material preset for iris texture |
| `UIColor` | LSString | 145/145 | `#FF51240F`, `#FF703C16` | Hex ARGB color for UI swatch |

## Child Nodes

*(None in vanilla data)*

## Patterns of Use

- All 145 entries have all attributes — no optional fields.
- `UIColor` is always an ARGB hex string (e.g., `#FF51240F`).
- Names follow pattern: `Natural Brown A`, `Underdark Blue A`, `Infernal Red A`, etc.

## Cross-References

| From | To | Via |
|------|----|-----|
| CharacterCreationPresets | CharacterCreationEyeColor | `EyeColorUUID` |
| MaterialPresetBank | CharacterCreationEyeColor | `MaterialPresetUUID` |

## Caveats & Gotchas

- `UIColor` type is `LSString`, not a dedicated color type.

## Similarities to Other Nodes

- **CharacterCreationHairColor**: Identical attribute schema (UUID, Name, DisplayName, MaterialPresetUUID, UIColor).
- **CharacterCreationSkinColor**: Identical attribute schema.
