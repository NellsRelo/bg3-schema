# Node: `Resource`

> **Region**: [FCurveBank](_REGION.md)
> **Child Depth**: 2 (Resource → CurveKeys, CurveLimits)

---

## Node Hierarchy

```
Resource
├── CurveKeys                  ← repeated (keyframe entries)
│   ├── CurveKeyConstraintType     (int32)
│   ├── CurveKeyInterpolationType  (int32)
│   ├── CurveKeyLeftTangent        (float)
│   ├── CurveKeyPosition           (fvec2) ← (time, value)
│   └── CurveKeyRightTangent       (float)
└── CurveLimits                ← single child (axis bounds)
    ├── MaxX (float)
    ├── MaxY (float)
    ├── MinX (float)
    └── MinY (float)
```

## Attributes

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `ID` | FixedString | UUID primary key | `0f165107-d5d5-67ab-a35a-46b90b50dd73` |
| `Name` | LSString | Curve name | `DODGE_RootMovementYAxisCurve` |
| `Localized` | bool | Localization flag | `False` |
| `_OriginalFileVersion_` | int64 | Engine version stamp | `144115188075855891` |

## Child: CurveKeys

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `CurveKeyPosition` | fvec2 | (time, value) keyframe | `0 -0.05081273` |
| `CurveKeyInterpolationType` | int32 | Interpolation (0=step, 1=linear, 2=cubic) | `2` |
| `CurveKeyConstraintType` | int32 | Tangent constraint type | `0`, `2` |
| `CurveKeyLeftTangent` | float | Left (in) tangent | `2.4170623` |
| `CurveKeyRightTangent` | float | Right (out) tangent | `-0.7245303` |

## Child: CurveLimits

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `MinX` | float | Minimum time | `0` |
| `MaxX` | float | Maximum time | `0` |
| `MinY` | float | Minimum value | `0` |
| `MaxY` | float | Maximum value | `0` |
