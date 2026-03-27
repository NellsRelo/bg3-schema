# Node: `LongRestCost`

> **Region**: [LongRestCosts](_REGION.md)
> **Folder**: `Levelmaps/`
> **Vanilla entries**: 2 (Shared)

---

## Attributes

| Attribute | Type | Frequency | Examples | Notes |
|-----------|------|-----------|----------|-------|
| `UUID` | guid | 2/2 | `caed1ebc-...` | Primary key |
| `CampQuality` | int32 | 2/2 | `1`, `2` | Camp quality tier |
| `CampGrowthDifficulty` | FixedString | 2/2 | `CAMPGROWTH_MEDIUM` | Growth difficulty setting |
| `RequiredSupplies` | int32 | 2/2 | `40` | Supplies needed for long rest |

## Child Nodes

*(None in vanilla data)*

## Patterns of Use

- Only 2 entries with different `CampQuality` levels (1 and 2).
- Both require 40 supplies and use `CAMPGROWTH_MEDIUM`.

## Cross-References

| From | To | Via |
|------|----|-----|
| Camp system | LongRestCost | Camp quality level |

## Caveats & Gotchas

- Very small region (2 entries). Difficulty modifiers may override these values.

## Similarities to Other Nodes

*(None)*
