# Node: `Resource`

> **Region**: [BlendSpaceBank](_REGION.md)
> **Child Depth**: 2 (Resource → Inputs)

---

## Node Hierarchy

```
Resource
└── Inputs                      ← repeated (blend space sample points)
    ├── AnimationID (FixedString) ← UUID → AnimationBank
    ├── Position    (fvec2)       ← 2D position in blend space
    └── ShortNameID (FixedString) ← animation short name UUID
```

## Attributes

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `ID` | FixedString | UUID primary key | `09fa116f-66b3-03a2-4e89-00bf733e658b` |
| `Name` | LSString | Blend space name | `Trav_EndDown` |
| `XAxisName` | LSString | X axis label | `Ladder Climbing Angle` |
| `YAxisName` | LSString | Y axis label | `N/a` |
| `MinXValue` | float | X axis minimum | `0` |
| `MaxXValue` | float | X axis maximum | `25` |
| `MinYValue` | float | Y axis minimum | `0` |
| `MaxYValue` | float | Y axis maximum | `1` |
| `XElements` | int32 | Grid elements on X axis | `2` |
| `YElements` | int32 | Grid elements on Y axis | `2` |
| `Localized` | bool | _(optional)_ Localization flag | `False` |
| `_OriginalFileVersion_` | int64 | Engine version stamp | `144115188075855891` |

## Child: Inputs

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `AnimationID` | FixedString | UUID → [AnimationBank](../AnimationBank/_REGION.md) (or empty) | `6d20e2d6-ac44-8675-89fb-01494561baf3` |
| `Position` | fvec2 | Position in X/Y blend space | `25 0`, `0 0` |
| `ShortNameID` | FixedString | Animation short name reference | `9aa73082-b0ce-4243-b893-4598f15ea717` |

## Cross-References

| From | To | Via |
|------|----|-----|
| Inputs.AnimationID | [AnimationBank](../AnimationBank/_REGION.md) | Blend space animation source |
