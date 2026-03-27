# Node: `Resource`

> **Region**: [EffectBank](_REGION.md)
> **Child Depth**: 5 (Resource → EffectComponents → Properties → Property → Parameter)

---

## Node Hierarchy

```
Resource
├── Dependencies
│   └── DependentResource          ← repeated
│       └── Object (FixedString)   ← UUID dependency
└── EffectComponents               ← repeated (per VFX component)
    ├── Modules
    │   └── Module                 ← repeated
    │       ├── Name (LSString)    ← module name
    │       └── FullName
    │           └── Object (FixedString)
    └── Properties
        └── Property               ← repeated
            ├── AttributeName (FixedString)
            ├── FullName (FixedString)
            ├── Input (FixedString)
            ├── Type (uint8)
            └── Parameter          ← repeated
                ├── Name (LSString)
                └── Value (float)
```

## Attributes

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `ID` | FixedString | UUID primary key | `9a52ef15-2633-216f-84ea-cd9c6f28e2a5` |
| `Name` | LSString | Effect name | `VFX_Actions_Cast_Damage_Fire_...` |
| `EffectName` | FixedString | Effect identifier (often matches Name) | `VFX_Actions_Cast_Damage_Fire_...` |
| `SourceFile` | LSString | LSFX source file | `Public/Shared/Assets/Effects/Effects_Banks/...lsfx` |
| `Duration` | float | Effect duration in seconds | `2`, `1.5` |
| `Looping` | bool | Whether effect loops | `False` |
| `InterruptionMode` | uint32 | How effect handles interruption | `0` |
| `BoundsMin` | fvec3 | AABB min corner | `-3 -3 -3` |
| `BoundsMax` | fvec3 | AABB max corner | `3 3 3` |
| `Center` | fvec3 | _(optional)_ Effect center | `0 0 0` |
| `Radius` | float | _(optional)_ Effect radius | `5.196152` |
| `CullingDistance` | float | LOD culling distance | `30` |
| `Initialized` | bool | _(optional)_ Initialization flag | `True` |
| `Localized` | bool | _(optional)_ Localization flag | `False` |
| `_OriginalFileVersion_` | int64 | Engine version stamp | `144115198813274212` |

## Child: EffectComponents

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `ID` | guid | Component UUID | `54767a94-674f-49ec-816e-a367315d2cac` |
| `Name` | LSString | Component type | `OverlayMaterial`, `Light`, `ParticleSystem` |
| `StartTime` | float | Component start time | `0` |
| `EndTime` | float | Component end time | `0` |
| `Track` | uint32 | Timeline track index | `0` |

## EffectComponents → Properties → Property

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `AttributeName` | FixedString | Property name | `Alpha`, `Position` |
| `FullName` | FixedString | Qualified name | `Dynamic Parameters.Alpha`, `Offset` |
| `Input` | FixedString | Input binding | _(empty)_ |
| `Type` | uint8 | Property type enum | `6`, `8` |

## Properties → Property → Parameter

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `Name` | LSString | Parameter channel | `default`, `X`, `Y`, `Z`, `X Scale` |
| `Value` | float | Parameter value | `1`, `0` |

## Cross-References

| From | To | Via |
|------|----|-----|
| Resource.ID | GameObjects (StatusEffect, HitEffect, etc.) | Effect references in stats/game data |
| Dependencies.DependentResource.Object | Various banks | Material, texture, model dependencies |
