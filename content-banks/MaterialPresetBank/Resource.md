# Node: `Resource`

> **Region**: [MaterialPresetBank](_REGION.md)
> **Child Depth**: 3 (Resource → Presets → ScalarParameters, Vector3Parameters)

---

## Node Hierarchy

```
Resource
└── Presets
    ├── ColorPreset
    ├── MaterialPresets    ← empty marker node
    ├── ScalarParameters   ← repeated (float overrides)
    └── Vector3Parameters  ← repeated (color overrides)
```

## Attributes

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `ID` | FixedString | UUID primary key | `95995454-2c86-6ead-03a2-555012dc53f2` |
| `Name` | LSString | Preset name | `EYES_Cambion_Mizora` |
| `Localized` | bool | Localization flag | `False` |
| `_OriginalFileVersion_` | int64 | Engine version | `144115188075855919` |

## Child: Presets

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `MaterialResource` | FixedString | UUID → [MaterialBank](../MaterialBank/_REGION.md) (base material) | _(empty or UUID)_ |

### Presets → ColorPreset

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `ForcePresetValues` | bool | Force values over material defaults | `True` |
| `GroupName` | FixedString | Preset group | _(empty)_ |
| `MaterialPresetResource` | FixedString | UUID → another MaterialPresetBank | _(empty or UUID)_ |

### Presets → ScalarParameters

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `Parameter` | FixedString | Shader parameter name | `FxMasking`, `GlowBrightness`, `IrisEdgeStrength` |
| `Value` | float | Override value | `6`, `15`, `0.5` |
| `Color` | bool | Is color parameter | `False` |
| `Custom` | bool | Custom override | `False` |
| `Enabled` | bool | Override active | `True` |

### Presets → Vector3Parameters

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `Parameter` | FixedString | Shader parameter name | `Eyes_IrisColour`, `Eyes_ScleraColour`, `Eyes_GlowColour` |
| `Value` | fvec3 | RGB color value | `0.018912982 0.001686915 0.001686915` |
| `Color` | bool | Is color parameter | `True` |
| `Custom` | bool | Custom override | `False` |
| `Enabled` | bool | Override active | `True` |

## Cross-References

| From | To | Via |
|------|----|-----|
| Resource.ID | [CharacterVisualBank](../CharacterVisualBank/_REGION.md) | `MaterialOverrides.ColorPreset.MaterialPresetResource` |
| Resource.Presets.MaterialResource | [MaterialBank](../MaterialBank/_REGION.md) | Base material |
