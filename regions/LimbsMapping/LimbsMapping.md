# Node: `LimbsMapping`

> **Region**: [LimbsMapping](_REGION.md)
> **Folder**: `LimbsMapping/`
> **Vanilla entries**: 5 (Shared)

---

## Attributes

| Attribute | Type | Frequency | Examples | Notes |
|-----------|------|-----------|----------|-------|
| `UUID` | guid | 5/5 | `eb933d90-...` | Primary key |
| `RootTemplate` | guid | 5/5 | `95be4f20-...` | References creature template |
| `FrontLeft` | LSString | 5/5 | `1, 2, 5` | Comma-separated limb indices for front-left |
| `FrontRight` | LSString | 5/5 | `5, 7, 8` | Comma-separated limb indices for front-right |
| `BackLeft` | LSString | 5/5 | `3, 4, 6` | Comma-separated limb indices for back-left |
| `BackRight` | LSString | 5/5 | `6, 9, 10` | Comma-separated limb indices for back-right |

## Child Nodes

*(None in vanilla data)*

## Patterns of Use

- Maps creature limbs to quadrant positions for combat/animation targeting.
- Limb indices are comma-separated integers within LSString values.
- All 5 entries have all attributes.

## Cross-References

| From | To | Via |
|------|----|-----|
| LimbsMapping | GameObjects (RootTemplates) | `RootTemplate` |

## Caveats & Gotchas

- Quadrant values are comma-separated strings, not arrays.

## Similarities to Other Nodes

*(None)*
