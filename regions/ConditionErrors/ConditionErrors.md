# Node: `ConditionErrors`

> **Region**: [ConditionErrors](_REGION.md)
> **Folder**: `ErrorDescriptions/`
> **Source**: `Shared/Public/Shared/ErrorDescriptions/ConditionErrors.lsx` (primary), also in Gustav (GustavDev pub), GustavX
> **Total Nodes**: ~271 combined (Shared: 182, Gustav/GustavDev: 72, GustavX: 17)

---

## Attributes

| Attribute | Type | Frequency | Examples | Notes |
|-----------|------|-----------|----------|-------|
| `UUID` | guid | always | `cc7ec561-2d34-4499-996c-d0522f205534` | Primary key |
| `Identifier` | FixedString | always | `NoTarget`, `NoSource`, `HasConcentration` | Machine-readable condition error ID |
| `ErrorDescriptionType` | uint8 | ~269/271 | `0` | Error category (0 = default; nearly always 0) |
| `DisplayName` | TranslatedString | ~266/271 | — | Localized error message shown to player |
| `Hidden` | bool | ~22/271 | `true` | When true, error is suppressed from UI display |

## Child Nodes

None.

## Patterns of Use

- Maps condition check failures to user-facing error messages (e.g., "Target is out of range")
- `Identifier` matches condition names used in spell/ability condition expressions
- `Hidden=true` on ~22 entries — suppresses display for internal/engine conditions
- Multi-pack: Shared has base conditions, Gustav adds game-specific ones, GustavX adds DLC conditions
- GustavX examples: `CE_Status_SG_Blinded_True`, `CE_Status_TWINKLINGCONSTELLATIONS_True`

## Caveats & Gotchas

- `DisplayName` missing on ~5 nodes (likely engine-internal conditions)
- `ErrorDescriptionType` missing on ~2 nodes
- Gustav's file is published under `Public/GustavDev/` not `Public/Gustav/`

## Similarities to Other Nodes

None unique — purpose-built error description system.
