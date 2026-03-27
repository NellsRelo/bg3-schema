# Node: `ColorDefinition`

> **Region**: [ColorDefinitions](_REGION.md)
> **Folder**: `Lists/`
> **Source**: `Shared/Public/Shared/Lists/ColorDefinitions.lsx`
> **Total Nodes**: ~555 (Shared only)

---

## Attributes

| Attribute | Type | Frequency | Examples | Notes |
|-----------|------|-----------|----------|-------|
| `UUID` | guid | x555 | `10b6461c-2d58-4ccf-9e04-68c00291a691` | Primary key |
| `Name` | FixedString | x555 | `Hair_LightBlonde`, `Hair_AsheBlonde`, `Hair_DarkAsheBlonde` | Internal name; prefixed by category (Hair_, Skin_, Eye_, etc.) |
| `DisplayName` | TranslatedString | x555 | — | Localized display name |
| `Color` | LSString | x555 | `#FF55402F`, `#FF523A30`, `#FF352726` | Hex ARGB color value |

## Child Nodes

None.

## Patterns of Use

- Used for character creation color palettes — hair, skin, eye colors etc.
- Prefixed `Name` values group by category: `Hair_*`, `Skin_*`, `Eye_*`
- Referenced by `CharacterCreationEyeColor`, `CharacterCreationHairColor`, `CharacterCreationSkinColor` via MaterialPresetUUID

## Caveats & Gotchas

- Color values use `#AARRGGBB` (ARGB) format, not standard web `#RRGGBB`
- All 555 nodes present in the single Shared file — no cross-pack merging needed

## Similarities to Other Nodes

- Similar data to `CharacterCreationEyeColor`, `CharacterCreationHairColor`, `CharacterCreationSkinColor` which reference these definitions
