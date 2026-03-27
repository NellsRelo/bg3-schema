# Node: `ManagedStatusVFX`

> **Region**: [ManagedStatusVFX](_REGION.md)
> **Folder**: `VFX/`
> **Vanilla entries**: 4 (Shared)

---

## Attributes

| Attribute | Type | Frequency | Examples | Notes |
|-----------|------|-----------|----------|-------|
| `UUID` | guid | 4/4 | `bc4f779b-...` | Primary key |
| `Name` | LSString | 4/4 | `New_Stat_0`, `New_Stat_1`, `New_Stat_2` | Internal name |
| `Group` | FixedString | 4/4 | `Head`, `Torso`, `Legs` | Body part group |
| `MixedEffect` | guid | 4/4 | `7549cf88-...` | VFX for mixed (positive+negative) status |
| `NegativeEffect` | guid | 4/4 | `97b76dcf-...` | VFX for negative status |
| `PositiveEffect` | guid | 4/4 | `9c89df30-...` | VFX for positive status |

## Child Nodes

*(None in vanilla data)*

## Patterns of Use

- Maps body regions to positive/negative/mixed status VFX.
- Only 4 entries covering Head, Torso, Legs groups.

## Cross-References

| From | To | Via |
|------|----|-----|
| ManagedStatusVFX | VFX templates | Effect guid attributes |

## Caveats & Gotchas

- Very small region (4 entries).

## Similarities to Other Nodes

- **DeathEffects**: Similar pattern of mapping categories to VFX GUIDs.
