# Node: `Passives`

> **Region**: [PassivesVFX](_REGION.md)
> **Folder**: `VFX/`
> **Vanilla entries**: 9 (Shared)

---

## Attributes

| Attribute | Type | Frequency | Examples | Notes |
|-----------|------|-----------|----------|-------|
| `UUID` | guid | 9/9 | `fa6cc1ca-...` | Primary key |
| `PassiveName` | FixedString | 9/9 | `Metamagic_Extended`, `Metamagic_Quickened`, `Metamagic_Careful` | References passive stat entry |
| `CastEffect` | guid | 9/9 | `67539cbe-...` | VFX played when casting |
| `PrepareEffect` | guid | 9/9 | `723cf8bd-...` | VFX played during preparation |

## Child Nodes

*(None in vanilla data)*

## Patterns of Use

- All 9 entries are Metamagic passives.
- Links passive abilities to visual effects during spellcasting.

## Cross-References

| From | To | Via |
|------|----|-----|
| Passives (VFX) | Passives (stats) | `PassiveName` |
| Passives (VFX) | VFX templates | `CastEffect`, `PrepareEffect` |

## Caveats & Gotchas

- Node name is `Passives`, NOT `PassivesVFX`. Region name is `PassivesVFX`.

## Similarities to Other Nodes

- **ManagedStatusVFX**: Similar VFX mapping pattern.
