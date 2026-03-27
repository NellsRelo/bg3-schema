# Node: `CustomDice`

> **Region**: [CustomDice](_REGION.md)
> **Folder**: `CustomDice/`
> **Vanilla entries**: 1 (Shared)

---

## Attributes

| Attribute | Type | Frequency | Examples | Notes |
|-----------|------|-----------|----------|-------|
| `UUID` | guid | 1/1 | `6de97dfc-...` | Primary key |
| `Name` | FixedString | 1/1 | `Default` | Internal name |
| `DisplayName` | TranslatedString | 1/1 | handle `h50c0...` | Shown in UI |
| `Description` | TranslatedString | 1/1 | handle `h1a55...` | Tooltip text |
| `IsDefault` | bool | 1/1 | `true` | Marks the default dice set |

## Child Nodes

*(None in vanilla data)*

## Patterns of Use

- Only one entry exists in vanilla — the `Default` dice set with `IsDefault=true`.
- Mods can add custom dice sets (cosmetic dice skins).

## Cross-References

| From | To | Via |
|------|----|-----|
| — | — | — |

## Caveats & Gotchas

- Only 1 node in vanilla; modders add more for custom dice cosmetics.

## Similarities to Other Nodes

*(None)*
