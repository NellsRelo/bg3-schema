# Node: `Resource`

> **Region**: [MaterialBank](_REGION.md)
> **Child Depth**: 2 (Resource → ScalarParameters, Texture2DParameters, etc.)

---

## Node Hierarchy

```
Resource
├── ScalarParameters          ← repeated (float shader params)
├── Texture2DParameters       ← repeated (texture refs)
├── Vector3Parameters         ← repeated (color/vector params)
└── VirtualTextureParameters  ← repeated (virtual texture refs)
```

## Attributes

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `ID` | FixedString | UUID primary key | `1210a2a8-93a2-814a-85e2-36a3e97004dd` |
| `Name` | LSString | Material name | `ATM_GlowPlane_A_Red` |
| `SourceFile` | LSString | LSF source material | `Public/Shared/Assets/Materials/Base/Base_GM_Pulse_VT.lsf` |
| `MaterialType` | uint8 | Material type enum | `6` |
| `DiffusionProfileUUID` | FixedString | UUID → [DiffusionProfileBank](../DiffusionProfileBank/_REGION.md) (subsurface scattering) | _(empty or UUID)_ |
| `_OriginalFileVersion_` | int64 | Engine version stamp | `144115207403209030` |

## Child: ScalarParameters

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `ParameterName` | FixedString | Shader parameter name | `SeeThroughEnabled`, `PulseSpeed`, `GlowMultiplier` |
| `Value` | float | Current value | `200` |
| `BaseValue` | float | Default/base value | `0` |
| `Enabled` | bool | Parameter active | `True` |
| `ExportAsPreset` | bool | Exportable as preset | `True` |
| `GroupName` | FixedString | UI group | `Glow`, `MicroDetailMap` |

## Child: Texture2DParameters

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `ParameterName` | FixedString | Texture slot name | `Glowmap`, `MicroDetailNormalMap` |
| `ID` | FixedString | UUID → [TextureBank](../TextureBank/_REGION.md) | `9dc5807b-3697-4b8f-ab0f-b9c5c1bd7010` |
| `Enabled` | bool | Parameter active | `False` |
| `ExportAsPreset` | bool | Exportable as preset | `True` |
| `GroupName` | FixedString | UI group | `Texture Map` |
| `IgnoreTexelDensity` | bool | _(optional)_ Skip texel density check | `True` |

## Child: Vector3Parameters

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `ParameterName` | FixedString | Shader parameter name | `GlowColour` |
| `Value` | fvec3 | Current RGB value | `0.8831797 0.22713652 0.4877652` |
| `BaseValue` | fvec3 | Default value | `0.85125166 0.101145156 0.0025858253` |
| `IsColor` | bool | Is this a color (vs direction vector) | `True` |
| `Enabled` | bool | Parameter active | `True` |
| `ExportAsPreset` | bool | Exportable as preset | `True` |
| `GroupName` | FixedString | UI group | `Glow` |

## Child: VirtualTextureParameters

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `ParameterName` | FixedString | VT parameter name | `virtualtexture` |
| `ID` | FixedString | UUID → [VirtualTextureBank](../VirtualTextureBank/_REGION.md) | `a881cad1-9b02-778e-3672-f5d94b792a64` |
| `Index` | int32 | VT layer index | `0` |
| `Enabled` | bool | Parameter active | `True` |
| `ExportAsPreset` | bool | Exportable as preset | `True` |
| `GroupName` | FixedString | UI group | `Texture Map` |

## Cross-References

| From | To | Via |
|------|----|-----|
| Resource.ID | [VisualBank](../VisualBank/_REGION.md) | `Objects.MaterialID` |
| Resource.DiffusionProfileUUID | [DiffusionProfileBank](../DiffusionProfileBank/_REGION.md) | Subsurface scattering |
| Resource.Texture2DParameters.ID | [TextureBank](../TextureBank/_REGION.md) | Texture reference |
| Resource.VirtualTextureParameters.ID | [VirtualTextureBank](../VirtualTextureBank/_REGION.md) | Virtual texture reference |
