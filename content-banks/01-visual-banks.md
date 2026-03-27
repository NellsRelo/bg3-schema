# Visual Content Banks

> Visual content banks define 3D models, materials, textures, and character visual assemblies.
> They are the most commonly modded bank category — character appearance mods touch
> CharacterVisualBank, VisualBank, MaterialBank, and MaterialPresetBank extensively.

---

## VisualBank

> Defines individual 3D model/mesh resources — the building blocks of all visible objects.
> Referenced by `CharacterVisualBank` slots, `GameObjects.VisualTemplate`, and `TileSetBank` tiles.

### Region Structure

```xml
<region id="VisualBank">
  <node id="VisualBank">
    <children>
      <node id="Resource"> ... </node>   <!-- repeated -->
    </children>
  </node>
</region>
```

### File Locations

| Source | Path Pattern | Content |
|--------|-------------|---------|
| Shared | `Content/Assets/Characters/.../_merged.lsx` | Character body/head meshes |
| Shared | `Content/Assets/Buildings/.../_merged.lsx` | Architecture meshes |
| Shared | `Content/Assets/Effects/Models/.../_merged.lsx` | VFX model meshes |
| SharedDev | `Content/Assets/.../_merged.lsx` | Extended assets |

### Node Hierarchy

```
VisualBank (region + root node)
└── Resource                              ← one per visual mesh/model
    ├── AnimationWaterfall                 ← repeated (animation refs)
    ├── AnimationSetOverrides              ← animation set override map
    │   └── (PairElement1/PairElement2 mapped)
    ├── Attachments                        ← attachment container
    ├── Base                               ← empty marker node
    ├── ClothParams                        ← repeated (cloth physics per mesh)
    ├── ClothProxyMapping                  ← proxy map container
    │   └── Object (MapKey)
    │       └── MapValue → Object
    ├── Objects                            ← repeated (LOD mesh entries)
    ├── Tags                               ← repeated
    └── VertexColorMaskSlots               ← repeated (body region masks)
```

### Resource Attributes

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `ID` | FixedString | UUID primary key | `9468fe74-1ae3-df0c-70f6-6a7313a095e9` |
| `Name` | LSString | Display name | `ELEM_Grease_Head_A` |
| `SourceFile` | LSString | GR2 source path | `Generated/Public/Shared/Assets/.../file.GR2` |
| `Template` | FixedString | Template reference (mesh root) | `Generated/.../ELEM_Mud_Head_A.Dummy_Root.0` |
| `SkeletonResource` | FixedString | UUID → SkeletonBank | `6e822843-65c9-84bc-9349-75505e1178c0` |
| `BlueprintInstanceResourceID` | FixedString | UUID → AnimationBlueprintBank | `dcd733b9-a3b7-6064-4741-587385c33e33` |
| `ClothColliderResourceID` | FixedString | UUID → ClothColliderBank | _(empty or UUID)_ |
| `SoftbodyResourceID` | FixedString | Softbody physics ref | _(empty or UUID)_ |
| `HairPresetResourceId` | FixedString | Hair preset ref | _(empty or UUID)_ |
| `HairType` | uint8 | Hair rendering type | `0` |
| `Slot` | FixedString | Equipment/body slot | `Head`, `Body` |
| `SkeletonSlot` | FixedString | Skeleton slot index | `1`, `` |
| `RemapperSlotId` | FixedString | Remapper slot ref | _(empty)_ |
| `ScalpMaterialId` | FixedString | Scalp material for bald transitions | _(empty or UUID)_ |
| `AttachBone` | FixedString | Bone to attach to | _(empty)_ |
| `AttachmentSkeletonResource` | FixedString | Attachment skeleton ref | _(empty)_ |
| `BoundsMax` | fvec3 | AABB max corner | `0.5877333 4.4921784 0.9691809` |
| `BoundsMin` | fvec3 | AABB min corner | `-0.8485812 2.5789838 -1.2285966` |
| `MaterialType` | uint8 | Material type flag | `0` |
| `NeedsSkeletonRemap` | bool | Whether skeleton remapping is needed | `False` |
| `SupportsVertexColorMask` | bool | Body region masking support | `False`, `True` |
| `Localized` | bool | Localization flag | `False` |
| `_OriginalFileVersion_` | int64 | Engine version stamp | `144115207403209009` |

### Child: Objects (LOD Meshes)

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `LOD` | uint8 | Level of detail (0 = highest) | `0`, `1`, `2`, `3` |
| `MaterialID` | FixedString | UUID → MaterialBank | `cce6d925-baad-94a8-c09f-cee6fe9a3686` |
| `ObjectID` | FixedString | Mesh object identifier | `ELEM_Mud_Head_A.ELEM_Mud_Head_A_Mesh.0` |

### Child: AnimationWaterfall

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `Object` | FixedString | UUID → AnimationSetBank or AnimationBank | `eeff696b-04e8-1a83-66fd-d89483eeb1f1` |

### Child: ClothParams (Physics Simulation)

Extensive cloth simulation parameters per mesh. Key attributes:

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `AnimDriveDampingForce` | float | Animation drive damping | `150` |
| `AnimDriveSpringForce` | float | Animation drive spring | `200` |
| `BendingStiffness` | float | Cloth bending resistance | `1` |
| `Damping` | fvec3 | Damping per axis | `0.03 0.03 0.03` |
| `Friction` | float | Surface friction | `0.1` |
| `AtmosphericWindEnabled` | bool | Wind interaction | `False` |
| `ClothMainWindSpeed` | float | Wind speed for cloth | `0` |
| `ClothWindSpeed` | float | Cloth-specific wind | `0` |
| `LinearDrag` | fvec3 | Linear drag per axis | `0.0001 0.0001 0.0001` |
| `AngularDrag` | fvec3 | Angular drag per axis | `0.0001 0.0001 0.0001` |
| `CollisionMassScale` | float | Collision mass scaling | `1` |
| `CompressionLimit` | float | Compression constraint | `0.8` |

_(Full list includes ~30 cloth physics attributes)_

### Cross-References

| From | To | Via |
|------|----|-----|
| VisualBank.ID | CharacterVisualBank.Slots.VisualResource | Slot visual assignment |
| VisualBank.ID | TileSetBank.Tile.VisualGUID | Tile visual |
| VisualBank.ID | SplineSetBank.Tile.VisualGUID | Spline visual |
| VisualBank.SkeletonResource | SkeletonBank.ID | Skeleton binding |
| VisualBank.BlueprintInstanceResourceID | AnimationBlueprintBank.ID | Animation blueprint |
| VisualBank.Objects.MaterialID | MaterialBank.ID | Mesh material |
| VisualBank.AnimationWaterfall.Object | AnimationSetBank.ID | Animation waterfall |
| GameObjects.VisualTemplate | VisualBank.ID | World object visual |

---

## CharacterVisualBank

> Assembles complete character appearances from visual slots, material overrides, and color presets.
> The primary entry point for character appearance — referenced by `GameObjects.CharacterVisualResourceID`.

### Region Structure

```xml
<region id="CharacterVisualBank">
  <node id="CharacterVisualBank">
    <children>
      <node id="Resource"> ... </node>
    </children>
  </node>
</region>
```

### File Locations

| Source | Path Pattern | Content |
|--------|-------------|---------|
| Shared | `Content/[PAK]_CharacterVisuals/_merged.lsx` | Root-level character visuals (7 MB, largest single file) |
| Shared | `Content/Assets/Characters/.../_merged.lsx` | Per-creature character visuals |
| Gustav | `Content/Assets/Characters/.../_merged.lsx` | Campaign character visuals |

### Node Hierarchy

```
CharacterVisualBank (region + root node)
└── Resource                          ← one per character visual
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

### Resource Attributes

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `ID` | FixedString | UUID primary key | `ef2f6ade-294b-0b0f-7539-c4d67854f31c` |
| `Name` | LSString | Character visual name | `HUM_F_02`, `Gale`, `LOW_DevilsFee_Boar_A` |
| `BaseVisual` | FixedString | UUID → VisualBank (base body) | `4b8ff439-0a98-6e6c-ad48-c695c1c29b27` |
| `BodySetVisual` | FixedString | UUID → VisualBank (body set) | `db6e5918-8514-4dcc-8363-e8fd3c50cce5` |
| `ShowEquipmentVisuals` | bool | Whether equipment visuals render | `False` |
| `Localized` | bool | Localization flag | `False` |
| `_OriginalFileVersion_` | int64 | Engine version stamp | `144115207403209024` |

### Child: Slots

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `Slot` | FixedString | Equipment/body slot name | `Head`, `Body`, `Hair` |
| `VisualResource` | FixedString | UUID → VisualBank | `0430a573-683b-f1f0-3c02-1255d7cd1299` |
| `Bone` | FixedString | Attachment bone | _(empty)_ |

### Child: MaterialOverrides

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `MaterialResource` | FixedString | UUID → MaterialBank | _(empty or UUID)_ |

#### MaterialOverrides → ColorPreset

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `ForcePresetValues` | bool | Force preset values over material defaults | `False` |
| `GroupName` | FixedString | Preset group | _(empty)_ |
| `MaterialPresetResource` | FixedString | UUID → MaterialPresetBank | _(empty or UUID)_ |

#### MaterialOverrides → ScalarParameters

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `Parameter` | FixedString | Shader parameter name | `HemoglobinAmount`, `MelaninAmount`, `roughness` |
| `Value` | float | Parameter value | `0.8`, `0.05` |
| `Color` | bool | Is this a color parameter | `False` |
| `Custom` | bool | Custom (non-default) parameter | `True` |
| `Enabled` | bool | Parameter enabled | `True` |

#### MaterialOverrides → Vector3Parameters

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `Parameter` | FixedString | Shader parameter name | `Eyes_IrisColour`, `Cloth_Primary`, `HemoglobinColor` |
| `Value` | fvec3 | RGB or vector value | `0.3537409 0.19046287 0.1604435` |
| `Color` | bool | Is this a color parameter | `True` |
| `Custom` | bool | Custom (non-default) parameter | `True` |
| `Enabled` | bool | Parameter enabled | `True` |

### Cross-References

| From | To | Via |
|------|----|-----|
| CharacterVisualBank.ID | GameObjects | `CharacterVisualResourceID` field |
| CharacterVisualBank.BaseVisual | VisualBank.ID | Base body mesh |
| CharacterVisualBank.BodySetVisual | VisualBank.ID | Body set mesh |
| CharacterVisualBank.Slots.VisualResource | VisualBank.ID | Per-slot mesh |
| CharacterVisualBank.MaterialOverrides.MaterialResource | MaterialBank.ID | Material override |
| CharacterVisualBank.MaterialOverrides.ColorPreset.MaterialPresetResource | MaterialPresetBank.ID | Color preset |

### Modding Notes

- Character appearance mods primarily create or modify `CharacterVisualBank` entries
- The `Slots` children define which mesh goes on which body part (`Head`, `Body`, `Hair`, `Underwear`, etc.)
- `MaterialOverrides` control skin tone, eye color, hair color, and similar shader parameters
- `Name` is a human-readable label — the engine uses `ID` for resolution

---

## MaterialBank

> Defines material/shader instances — controls how surfaces look when rendered.
> Referenced by `VisualBank.Objects.MaterialID` and indirectly through `CharacterVisualBank.MaterialOverrides`.

### Region Structure

```xml
<region id="MaterialBank">
  <node id="MaterialBank">
    <children>
      <node id="Resource"> ... </node>
    </children>
  </node>
</region>
```

### Node Hierarchy

```
MaterialBank (region + root node)
└── Resource
    ├── ScalarParameters          ← repeated (float shader params)
    ├── Texture2DParameters       ← repeated (texture refs)
    ├── Vector3Parameters         ← repeated (color/vector params)
    └── VirtualTextureParameters  ← repeated (virtual texture refs)
```

### Resource Attributes

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `ID` | FixedString | UUID primary key | `1210a2a8-93a2-814a-85e2-36a3e97004dd` |
| `Name` | LSString | Material name | `ATM_GlowPlane_A_Red` |
| `SourceFile` | LSString | LSF source material | `Public/Shared/Assets/Materials/Base/Base_GM_Pulse_VT.lsf` |
| `MaterialType` | uint8 | Material type enum | `6` |
| `DiffusionProfileUUID` | FixedString | UUID → DiffusionProfileBank (subsurface scattering) | _(empty or UUID)_ |
| `_OriginalFileVersion_` | int64 | Engine version stamp | `144115207403209030` |

### Child: ScalarParameters

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `ParameterName` | FixedString | Shader parameter name | `SeeThroughEnabled`, `PulseSpeed`, `GlowMultiplier` |
| `Value` | float | Current value | `200` |
| `BaseValue` | float | Default/base value | `0` |
| `Enabled` | bool | Parameter active | `True` |
| `ExportAsPreset` | bool | Exportable as preset | `True` |
| `GroupName` | FixedString | UI group | `Glow`, `MicroDetailMap` |

### Child: Texture2DParameters

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `ParameterName` | FixedString | Texture slot name | `Glowmap`, `MicroDetailNormalMap` |
| `ID` | FixedString | UUID → TextureBank | `9dc5807b-3697-4b8f-ab0f-b9c5c1bd7010` |
| `Enabled` | bool | Parameter active | `False` |
| `ExportAsPreset` | bool | Exportable as preset | `True` |
| `GroupName` | FixedString | UI group | `Texture Map` |
| `IgnoreTexelDensity` | bool | _(optional)_ Skip texel density check | `True` |

### Child: Vector3Parameters

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `ParameterName` | FixedString | Shader parameter name | `GlowColour` |
| `Value` | fvec3 | Current RGB value | `0.8831797 0.22713652 0.4877652` |
| `BaseValue` | fvec3 | Default value | `0.85125166 0.101145156 0.0025858253` |
| `IsColor` | bool | Is this a color (vs direction vector) | `True` |
| `Enabled` | bool | Parameter active | `True` |
| `ExportAsPreset` | bool | Exportable as preset | `True` |
| `GroupName` | FixedString | UI group | `Glow` |

### Child: VirtualTextureParameters

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `ParameterName` | FixedString | VT parameter name | `virtualtexture` |
| `ID` | FixedString | UUID → VirtualTextureBank | `a881cad1-9b02-778e-3672-f5d94b792a64` |
| `Index` | int32 | VT layer index | `0` |
| `Enabled` | bool | Parameter active | `True` |
| `ExportAsPreset` | bool | Exportable as preset | `True` |
| `GroupName` | FixedString | UI group | `Texture Map` |

### Cross-References

| From | To | Via |
|------|----|-----|
| MaterialBank.ID | VisualBank.Objects.MaterialID | LOD mesh material |
| MaterialBank.DiffusionProfileUUID | DiffusionProfileBank.ID | Subsurface scattering |
| MaterialBank.Texture2DParameters.ID | TextureBank.ID | Texture reference |
| MaterialBank.VirtualTextureParameters.ID | VirtualTextureBank.ID | Virtual texture reference |

### Key Difference: MaterialBank vs MaterialPresetBank

| Aspect | MaterialBank | MaterialPresetBank |
|--------|-------------|-------------------|
| Scalar param name field | `ParameterName` | `Parameter` |
| Has `BaseValue`/`GroupName`/`ExportAsPreset` | Yes | No |
| Has `Color`/`Custom` | No | Yes |
| Purpose | Full material definition | Override preset for character visuals |

---

## MaterialPresetBank

> Defines material override presets for character visual customization (eye colors, skin tones, tattoo colors, etc.).
> Referenced by `CharacterVisualBank.MaterialOverrides.ColorPreset.MaterialPresetResource`.

### Region Structure

```xml
<region id="MaterialPresetBank">
  <node id="MaterialPresetBank">
    <children>
      <node id="Resource"> ... </node>
    </children>
  </node>
</region>
```

### Node Hierarchy

```
MaterialPresetBank (region + root node)
└── Resource
    └── Presets
        ├── ColorPreset
        ├── MaterialPresets    ← empty marker node
        ├── ScalarParameters   ← repeated (float overrides)
        └── Vector3Parameters  ← repeated (color overrides)
```

### Resource Attributes

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `ID` | FixedString | UUID primary key | `95995454-2c86-6ead-03a2-555012dc53f2` |
| `Name` | LSString | Preset name | `EYES_Cambion_Mizora` |
| `Localized` | bool | Localization flag | `False` |
| `_OriginalFileVersion_` | int64 | Engine version | `144115188075855919` |

### Child: Presets

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `MaterialResource` | FixedString | UUID → MaterialBank (base material) | _(empty or UUID)_ |

#### Presets → ColorPreset

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `ForcePresetValues` | bool | Force values over material defaults | `True` |
| `GroupName` | FixedString | Preset group | _(empty)_ |
| `MaterialPresetResource` | FixedString | UUID → another MaterialPresetBank | _(empty or UUID)_ |

#### Presets → ScalarParameters

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `Parameter` | FixedString | Shader parameter name | `FxMasking`, `GlowBrightness`, `IrisEdgeStrength` |
| `Value` | float | Override value | `6`, `15`, `0.5` |
| `Color` | bool | Is color parameter | `False` |
| `Custom` | bool | Custom override | `False` |
| `Enabled` | bool | Override active | `True` |

#### Presets → Vector3Parameters

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `Parameter` | FixedString | Shader parameter name | `Eyes_IrisColour`, `Eyes_ScleraColour`, `Eyes_GlowColour` |
| `Value` | fvec3 | RGB color value | `0.018912982 0.001686915 0.001686915` |
| `Color` | bool | Is color parameter | `True` |
| `Custom` | bool | Custom override | `False` |
| `Enabled` | bool | Override active | `True` |

### Cross-References

| From | To | Via |
|------|----|-----|
| MaterialPresetBank.ID | CharacterVisualBank.MaterialOverrides.ColorPreset.MaterialPresetResource | Character visual color preset |
| MaterialPresetBank.Presets.MaterialResource | MaterialBank.ID | Base material |

---

## TextureBank

> Registers individual texture assets (DDS files) with metadata like dimensions, format, and streaming flags.
> Flat resource structure — no child nodes.

### Region Structure

```xml
<region id="TextureBank">
  <node id="TextureBank">
    <children>
      <node id="Resource"> ... </node>
    </children>
  </node>
</region>
```

### Resource Attributes

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `ID` | FixedString | UUID primary key | `71708c59-8bb5-2367-a76c-7b98b09029da` |
| `Name` | LSString | Texture name | `Planet_moon_A_BM` |
| `SourceFile` | LSString | DDS source path | `Generated/Public/Shared/Assets/.../Planet_moon_A_BM.DDS` |
| `Template` | FixedString | Template name | `Planet_moon_A_BM` |
| `Width` | int32 | Texture width in pixels | `1024`, `2048` |
| `Height` | int32 | Texture height in pixels | `2048`, `512` |
| `Depth` | int32 | Texture depth (1 for 2D) | `1` |
| `Type` | int32 | Texture type enum | `1` |
| `SRGB` | bool | sRGB color space | `True`, `False` |
| `Streaming` | bool | Supports texture streaming | `True` |
| `Localized` | bool | _(optional)_ Localization flag | `False` |
| `_OriginalFileVersion_` | int64 | Engine version stamp | `144115207403209020` |

### Cross-References

| From | To | Via |
|------|----|-----|
| TextureBank.ID | MaterialBank.Texture2DParameters.ID | Material texture parameter |
| TextureBank.ID | LightCookieBank.TextureName | Light cookie texture |
| TextureBank.ID | TerrainBrushBank.BaseColorMap/NormalMap/PhysicalMap | Terrain textures |

---

## VirtualTextureBank

> Registers virtual texture assets for streaming — allows large textures to be loaded on demand.
> Flat resource structure — no child nodes. Often co-located with other banks in the same file.

### Region Structure

```xml
<region id="VirtualTextureBank">
  <node id="VirtualTextureBank">
    <children>
      <node id="Resource"> ... </node>
    </children>
  </node>
</region>
```

### Resource Attributes

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `ID` | FixedString | UUID primary key | `0a474694-...` |
| `Name` | LSString | Virtual texture name | `DEC_CEM_Tomb_A_Shar_Statue_A` |
| `GTexFileName` | FixedString | GTex hash filename | `96a33da0d8fd334745ec4d654e8bcaaa` |
| `Prefetch` | bool | Pre-fetch on load | `False` |
| `PrefetchMipLevel` | int8 | Mip level to prefetch (-1 = none) | `-1` |
| `ReferencedColorSpaces` | uint32 | Color space flags | `6` |
| `VirtualTextureLayerConfig` | uint32 | Layer configuration flags | `3` |
| `_OriginalFileVersion_` | int64 | Engine version stamp | `144115207403209023` |

### Cross-References

| From | To | Via |
|------|----|-----|
| VirtualTextureBank.ID | MaterialBank.VirtualTextureParameters.ID | Material VT binding |

### Notes

- **Most common bank type** — 263 files in Shared alone, 204 in Gustav
- Almost always co-located with other banks (MaterialBank, VisualBank, etc.) in the same `_merged.lsx` file
- The `GTexFileName` is a content hash, not a human-readable name

---

## DiffusionProfileBank

> Defines subsurface scattering profiles — controls how light penetrates translucent surfaces
> (skin, wax, foliage, etc.). Referenced by `MaterialBank.DiffusionProfileUUID`.

### Region Structure

```xml
<region id="DiffusionProfileBank">
  <node id="DiffusionProfileBank">
    <children>
      <node id="DiffusionProfile"> ... </node>   <!-- note: uses DiffusionProfile, not Resource -->
    </children>
  </node>
</region>
```

### DiffusionProfile Attributes

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `ID` | FixedString | UUID primary key | `d769c6b6-12e9-083e-35e3-02695252e44d` |
| `Name` | LSString | Profile name | `BLD_Druids_Camp_Tent_A_SS` |
| `Localized` | bool | Localization flag | `False` |
| `ScatterColor` | fvec3 | Subsurface scatter color | `0.11926401 0.28012437 0.3636039` |
| `ScatterDistance` | float | Scatter distance in world units | `200` |
| `TransmissionTint` | fvec3 | Transmission color tint | `0.11657577 0.28445205 0.3636039` |
| `ThickObjectTransmission` | bool | Enable thick object transmission | `False` |
| `ThicknessRemapMin` | float | Thickness remap minimum | `0` |
| `ThicknessRemapMax` | float | Thickness remap maximum | `1` |
| `DualSpecularMix` | float | Dual specular lobe mix ratio | `0.85` |
| `DualSpecularRoughnessA` | float | Primary specular roughness | `0.75` |
| `DualSpecularRoughnessB` | float | Secondary specular roughness | `1.3` |
| `_OriginalFileVersion_` | int64 | Engine version stamp | `144115198813274213` |

### Cross-References

| From | To | Via |
|------|----|-----|
| DiffusionProfileBank.ID | MaterialBank.DiffusionProfileUUID | Material SSS profile |

### Notes

- **Unique node ID**: Uses `DiffusionProfile` instead of the standard `Resource` node ID
- 17 instances in Shared — typically for skin, cloth, and organic surface materials
- Often co-located with VirtualTextureBank in the same file

---

## Multi-Region Co-location

Content bank files frequently contain multiple region types. Common visual bank co-locations:

| Primary Bank | Co-located With | Example Path |
|-------------|----------------|--------------|
| VirtualTextureBank | MaterialBank, VisualBank, SkeletonBank | Character/building asset bundles |
| CharacterVisualBank | MaterialPresetBank | Character preset bundles |
| MaterialBank | TextureBank, VirtualTextureBank | Material definition files |
| DiffusionProfileBank | VirtualTextureBank | SSS material files |
