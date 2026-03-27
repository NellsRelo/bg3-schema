# Node: `Type`

> **Region**: [Types](_REGION.md)
> **Folder**: `Encumbrance/`
> **Source**: `Shared/Public/Shared/Encumbrance/Types.lsx`
> **Total Nodes**: ~3 (Shared only)

---

## Attributes

| Attribute | Type | Frequency | Examples | Notes |
|-----------|------|-----------|----------|-------|
| `UUID` | guid | x3 | `6bf69d49-2428-4823-a6f2-21383a66395e` | Primary key |
| `Status` | FixedString | x3 | `ENCUMBERED_LIGHT`, `ENCUMBERED_HEAVY`, `ENCUMBERED_MAX` | Status applied at this encumbrance tier |

## Child Nodes

None.

## Patterns of Use

- Defines the 3 tiers of encumbrance: Light, Heavy, Max
- Each tier maps to a status effect applied to the character
- `ENCUMBERED_LIGHT`: reduced speed
- `ENCUMBERED_HEAVY`: further reduced speed + disadvantage
- `ENCUMBERED_MAX`: cannot move

## Caveats & Gotchas

- **Region is `Types`**, file is `Types.lsx` in `Encumbrance/` folder
- Fixed set of exactly 3 entries

## Similarities to Other Nodes

None — unique encumbrance system.
