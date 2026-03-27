# Node: `GoldValue`

> **Region**: [GoldValues](_REGION.md)
> **Folder**: `Levelmaps/`
> **Vanilla entries**: 58 (Shared)

---

## Attributes

| Attribute | Type | Frequency | Examples | Notes |
|-----------|------|-----------|----------|-------|
| `UUID` | guid | 58/58 | `8b2ad47c-...` | Primary key |
| `Name` | FixedString | 58/58 | `ZeroValue`, `Junk`, `Tools` | Item value category |
| `ParentScale` | double | 58/58 | `1` | Multiplier applied to parent's gold values |
| `ParentUUID` | guid | 53/58 | `7190ea94-...` | Parent category (hierarchical) |
| `Level1` | uint32 | 5/58 | `0`, `1`, `25` | Gold value at level 1 |
| `Level2` | uint32 | 2/58 | `1`, `13` | Gold value at level 2 |
| `Level3` | uint32 | 2/58 | `1`, `16` | Gold value at level 3 |
| `Level4` | uint32 | 2/58 | `1`, `20` | Gold value at level 4 |
| `Level5` | uint32 | 2/58 | `1`, `25` | Gold value at level 5 |
| `Level6` | uint32 | 2/58 | `1`, `32` | Gold value at level 6 |
| `Level7` | uint32 | 2/58 | `1`, `45` | Gold value at level 7 |
| `Level8` | uint32 | 2/58 | `1`, `60` | Gold value at level 8 |
| `Level9` | uint32 | 2/58 | `1`, `80` | Gold value at level 9 |
| `Level10` | uint32 | 2/58 | `1`, `100` | Gold value at level 10 |
| `Level11` | uint32 | 1/58 | `120` | Gold value at level 11 |
| `Level12` | uint32 | 1/58 | `150` | Gold value at level 12 |

## Child Nodes

*(None in vanilla data)*

## Patterns of Use

- Hierarchical item value categories (ParentUUID forms a tree).
- Most entries inherit scaling from parents via `ParentScale`.
- Level-based values are very sparse (only some categories define per-level prices).
- Categories: `ZeroValue`, `Junk`, `Tools`, `Scrolls`, `Potions`, weapon rarity tiers, etc.

## Cross-References

| From | To | Via |
|------|----|-----|
| GoldValue | GoldValue (parent) | `ParentUUID` → `UUID` |
| Items (stats) | GoldValue | Item value class reference |

## Caveats & Gotchas

- Level columns are extremely sparse — most entries use parent scaling instead.
- 5 root entries have no `ParentUUID`.

## Similarities to Other Nodes

- **ExperienceRewards**: Similar level-based value columns pattern.
