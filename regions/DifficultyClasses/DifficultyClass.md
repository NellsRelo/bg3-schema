# Node: `DifficultyClass`

> **Region**: [DifficultyClasses](_REGION.md)
> **Folder**: `DifficultyClasses/`

---

## Attributes

> 30 nodes in Shared (vanilla)

| Attribute | Type | Count | Examples | Notes |
|-----------|------|-------|----------|-------|
| `UUID` | guid | 30/30 | `4dfcb0ff-e02a-4efd-b132-77dfd956055e` | Primary key |
| `Name` | LSString | 30/30 | `Act1_Zero`, `Act1_Negligible`, `Act1_VeryEasy` | DC name with act prefix |
| `Difficulties` | LSString | 30/30 | `0`, `2`, `5` | Numeric DC values |

## Patterns of Use

### Naming Convention

DC names follow the pattern `{Act}_{Difficulty}`:
- Act prefix: `Act1_`, `Act2_`, `Act3_`
- Difficulty tiers: `Zero`, `Negligible`, `VeryEasy`, `Easy`, `Medium`, `Hard`, `VeryHard`, `NearlyImpossible`, `Godly`

## Caveats & Gotchas

- DC values scale by act — the same tier name maps to higher numeric DCs in later acts.
- Used by dialog/scripting checks to reference difficulty by name rather than hardcoded numbers.

## Cross-References

| From | To | Via |
|------|----|-----|
| — | — | — |

## Caveats & Gotchas

*(To be documented)*

## Similarities to Other Nodes

*(To be documented)*
