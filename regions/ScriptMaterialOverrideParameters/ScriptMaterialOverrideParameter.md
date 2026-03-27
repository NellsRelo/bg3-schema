# Node: `ScriptMaterialOverrideParameter`

> **Region**: [ScriptMaterialOverrideParameters](_REGION.md)
> **Source**: `Gustav/Public/Gustav/ScriptMaterialOverrides/ScriptMaterialOverrideParameters.lsx`

---

## Attributes

| Attribute | Type | Frequency | Examples | Notes |
|-----------|------|-----------|----------|-------|
| `ParameterName` | FixedString | always | `Blindness_L`, `Blindness` | Material parameter name |
| `ParameterType` | FixedString | always | `Float` | Data type of parameter value |
| `ParameterValue` | LSString | always | `1` | Value as string |
| `UUID` | guid | always | — | Primary key |

## Child Nodes

*(None)*

## Vanilla Scope

| Pack | Nodes |
|------|-------|
| Gustav | 2 |

Defines individual material override parameters (e.g. Hag eye blindness effects).
Referenced by [ScriptMaterialOverridePreset](../ScriptMaterialOverridePresets/ScriptMaterialOverridePreset.md) via `ParameterUUIDs` children.

## Cross-References

| From | To | Via |
|------|----|-----|
| — | — | — |

## Caveats & Gotchas

*(To be documented)*

## Similarities to Other Nodes

*(To be documented)*
