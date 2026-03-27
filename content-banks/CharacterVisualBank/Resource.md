# Node: `Resource`

> **Region**: [CharacterVisualBank](_REGION.md)
> **Child Depth**: 3 (Resource → Slots, MaterialOverrides → ScalarParameters/Vector3Parameters)

---

## Node Hierarchy

```
Resource                          ← one per character visual
├── MaterialOverrides             ← material override container
│   ├── ColorPreset               ← optional color preset reference
│   ├── MaterialPresets           ← empty marker node
│   ├── ScalarParameters          ← repeated (float overrides)
│   ├── Vector2Parameters         ← repeated (fvec2 overrides)
│   └── Vector3Parameters         ← repeated (fvec3 color/vector overrides)
├── RealMaterialOverrides         ← empty marker/container
├── Slots                         ← repeated (visual slot assignments)
└── Materials                     ← optional map-keyed materials
    └── Object (MapKey)
```

## Attributes

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `ID` | FixedString | UUID primary key | `ef2f6ade-294b-0b0f-7539-c4d67854f31c` |
| `Name` | LSString | Character visual name | `HUM_F_02`, `Gale`, `LOW_DevilsFee_Boar_A` |
| `BaseVisual` | FixedString | UUID → [VisualBank](../VisualBank/_REGION.md) (base body) | `4b8ff439-0a98-6e6c-ad48-c695c1c29b27` |
| `BodySetVisual` | FixedString | UUID → [VisualBank](../VisualBank/_REGION.md) (body set) | `db6e5918-8514-4dcc-8363-e8fd3c50cce5` |
| `ShowEquipmentVisuals` | bool | Whether equipment visuals render | `False` |
| `Localized` | bool | Localization flag | `False` |
| `_OriginalFileVersion_` | int64 | Engine version stamp | `144115207403209024` |

## Child: Slots

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `Slot` | FixedString | Equipment/body slot name | `Head`, `Body`, `Hair` |
| `VisualResource` | FixedString | UUID → [VisualBank](../VisualBank/_REGION.md) | `0430a573-683b-f1f0-3c02-1255d7cd1299` |
| `Bone` | FixedString | Attachment bone | _(empty)_ |

## Child: MaterialOverrides

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `MaterialResource` | FixedString | UUID → [MaterialBank](../MaterialBank/_REGION.md) | _(empty or UUID)_ |

### MaterialOverrides → ColorPreset

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `ForcePresetValues` | bool | Force preset values over material defaults | `False` |
| `GroupName` | FixedString | Preset group | _(empty)_ |
| `MaterialPresetResource` | FixedString | UUID → [MaterialPresetBank](../MaterialPresetBank/_REGION.md) | _(empty or UUID)_ |

### MaterialOverrides → ScalarParameters

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `Parameter` | FixedString | Shader parameter name | `HemoglobinAmount`, `MelaninAmount`, `roughness` |
| `Value` | float | Parameter value | `0.8`, `0.05` |
| `Color` | bool | Is this a color parameter | `False` |
| `Custom` | bool | Custom (non-default) parameter | `True` |
| `Enabled` | bool | Parameter enabled | `True` |

### MaterialOverrides → Vector3Parameters

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `Parameter` | FixedString | Shader parameter name | `Eyes_IrisColour`, `Cloth_Primary`, `HemoglobinColor` |
| `Value` | fvec3 | RGB or vector value | `0.3537409 0.19046287 0.1604435` |
| `Color` | bool | Is this a color parameter | `True` |
| `Custom` | bool | Custom (non-default) parameter | `True` |
| `Enabled` | bool | Parameter enabled | `True` |

## Cross-References

| From | To | Via |
|------|----|-----|
| Resource.ID | GameObjects | `CharacterVisualResourceID` field |
| Resource.BaseVisual | [VisualBank](../VisualBank/_REGION.md) | Base body mesh |
| Resource.BodySetVisual | [VisualBank](../VisualBank/_REGION.md) | Body set mesh |
| Resource.Slots.VisualResource | [VisualBank](../VisualBank/_REGION.md) | Per-slot mesh |
| Resource.MaterialOverrides.MaterialResource | [MaterialBank](../MaterialBank/_REGION.md) | Material override |
| Resource.MaterialOverrides.ColorPreset.MaterialPresetResource | [MaterialPresetBank](../MaterialPresetBank/_REGION.md) | Color preset |
