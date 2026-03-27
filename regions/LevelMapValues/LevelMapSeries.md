# Node: `LevelMapSeries`

> **Region**: [LevelMapValues](_REGION.md)
> **Folder**: `Levelmaps/`

---

## Attributes

> 12 nodes in Shared (vanilla)

| Attribute | Type | Count | Examples | Notes |
|-----------|------|-------|----------|-------|
| `UUID` | guid | 12/12 | `b183a804-e9c6-4990-8984-c76d3ed67a9f` | Primary key |
| `Name` | FixedString | 12/12 | `D4Cantrip`, `D6Cantrip`, `D8Cantrip` | Dice progression name |
| `Level1` | LSString | 12/12 | `1d4`, `1d6`, `1d8` | Dice at level 1 |
| `Level2` | LSString | 6/12 | `1d4`, `1d6`, `1d8` | Dice at level 2 |
| `Level3` | LSString | 7/12 | `1d4`, `1d6` | Dice at level 3 |
| `Level4` | LSString | 6/12 | `1d4`, `1d6` | Dice at level 4 |
| `Level5` | LSString | 9/12 | `2d4`, `2d6`, `2d8` | Dice at level 5 |
| `Level6` | LSString | 7/12 | `2d4`, `2d6` | Dice at level 6 |
| `Level7` | LSString | 7/12 | `2d4`, `2d6` | Dice at level 7 |
| `Level8` | LSString | 6/12 | `2d4`, `2d6` | Dice at level 8 |
| `Level9` | LSString | 9/12 | `2d4`, `2d6` | Dice at level 9 |
| `Level10` | LSString | 8/12 | `3d4`, `3d6`, `3d8` | Dice at level 10 |
| `Level11` | LSString | 2/12 | `6d6`, `4d6` | Dice at level 11 |
| `FallbackValue` | LSString | 3/12 | `1`, `1d8`, `2` | Default if level not found |
| `PreferredClassUUID` | guid | 4/12 | links to ClassDescription.UUID | Class this map is associated with |

## Cross-References

| From | To | Via |
|------|----|-----|
| LevelMapSeries.PreferredClassUUID | [ClassDescription](../ClassDescriptions/ClassDescription.md) | ClassDescription.UUID |
| LevelMapSeries.Name | Stats DamageType expressions | Level-scaled damage dice |

## Caveats & Gotchas

- Provides scalable dice expressions indexed by character level (cantrip damage scaling, etc.).
- Not all levels need entries — the engine falls back to the nearest defined level or `FallbackValue`.
- `Level11` only has 2 entries because BG3 caps at level 12 and most progressions plateau earlier.

## Cross-References

| From | To | Via |
|------|----|-----|
| — | — | — |

## Caveats & Gotchas

*(To be documented)*

## Similarities to Other Nodes

*(To be documented)*
