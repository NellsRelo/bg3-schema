# Node: `ShortNameCategory`

> **Region**: [ShortNameCategories](_REGION.md)
> **Folder**: `Animation/`
> **Source**: `Shared/Public/Shared/Animation/ShortNameCategories.lsx`
> **Total Nodes**: ~60 (Shared only)

---

## Attributes

| Attribute | Type | Frequency | Examples | Notes |
|-----------|------|-----------|----------|-------|
| `UUID` | guid | x60 | `bed504fb-634d-4821-a975-5f76902b4c51` | Primary key |
| `Name` | FixedString | x60 | `Character Creation`, `Idle System`, `Idle Neutral System` | Human-readable category name |

## Child Nodes

None.

## Patterns of Use

- Defines categories for the 8,789 `ShortName` entries
- 60 categories covering: Character Creation, Idle, Combat, Dialogue, Cinematic, etc.
- Referenced by `ShortName.CategoryGuid` → `ShortNameCategory.UUID`

## Cross-References

| From | To | Via |
|------|----|-----|
| `ShortName.CategoryGuid` | `ShortNameCategory.UUID` | FK |

## Caveats & Gotchas

- Separate file from `ShortNames.lsx` — `ShortNameCategories.lsx` in same `Animation/` folder

## Similarities to Other Nodes

Paired with `ShortName` — this is the category lookup table.
