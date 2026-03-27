# Environment Content Banks

> Environment content banks define atmospheres, lighting, terrain, physics, and spatial assets.
> These banks control the look and feel of game levels — lighting, fog, post-processing,
> terrain materials, and physics collision shapes.

---

## AtmosphereBank

> Defines atmosphere presets — comprehensive environment configurations that control
> lighting, fog, post-processing, cloth wind, and color correction.
> The most attribute-rich bank type.

### Region Structure

```xml
<region id="AtmosphereBank">
  <node id="AtmosphereBank">
    <children>
      <node id="Resource"> ... </node>
    </children>
  </node>
</region>
```

### File Locations

| Source | Path Pattern | Content |
|--------|-------------|---------|
| Shared | `Content/Assets/Atmospheres/[PAK]_Atmospheres/_merged.lsx` | Shared atmospheres (co-located with VirtualTextureBank) |
| Gustav | `Content/Assets/Atmospheres/.../_merged.lsx` | Campaign-specific atmospheres |

### Node Hierarchy

```
AtmosphereBank (region + root node)
└── Resource
    ├── Atmosphere                       ← primary atmosphere settings
    │   ├── Camera
    │   │   ├── FarPlane (float)
    │   │   └── NearPlane (float)
    │   ├── Fog                          ← optional (legacy format)
    │   │   ├── FogLayer0
    │   │   └── FogLayer1
    │   └── PostProcessing
    │       ├── ExposureSettings         ← appears twice (scene + timeline)
    │       │   └── Object
    │       ├── NewColorCorrection       ← variant A (newer format)
    │       │   ├── DarkRange
    │       │   ├── GlobalRange
    │       │   ├── HighlightRange
    │       │   ├── MidtonesRange
    │       │   ├── ShadowRange
    │       │   └── SpecularRange
    │       └── ColorCorrection          ← variant B (older format)
    │           ├── GlobalRange
    │           ├── HighlightsRange
    │           ├── MidtonesRange
    │           └── ShadowsRange
    └── Labels                           ← repeated (scene tags)
        └── Object (FixedString)
```

### Resource Attributes

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `ID` | FixedString | UUID primary key | ... |
| `Name` | LSString | Atmosphere name | ... |
| `Localized` | bool | _(optional)_ Localization flag | `False` |
| `CharacterLightSetup` | guid | _(optional)_ Character light reference | ... |
| `DisplayName` | TranslatedString | _(optional)_ UI display name | ... |
| `ForGameMaster` | bool | _(optional)_ Game Master mode visibility | ... |
| `GMSubSection` | TranslatedString | _(optional)_ Game Master UI section | ... |
| `_OriginalFileVersion_` | int64 | Engine version stamp | ... |

### Child: Atmosphere (Core Settings)

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `WindDirection` | float | Wind direction in degrees | `69` |
| `WindSpeed` | float | Wind speed | `0.5` |
| `InheritanceFlags` | uint32 | Which settings to inherit | `0` |
| `EnvironmentEffect` | FixedString | UUID → EffectBank | _(empty or UUID)_ |
| `EnvironmentEffectEnabled` | bool | Enable environment effect | ... |
| `EnvironmentEffectEnabledForTimeline` | bool | _(optional)_ Timeline enable | ... |
| `EnvironmentEffectGlobalEnabled` | bool | _(optional)_ Global enable | ... |
| `EnvironmentEffectOffset` | float | _(optional)_ Effect offset | ... |
| `LocalLightSourceColor` | fvec3 | Local light color | `1 1 1` |
| `LocalLightSourceEnabled` | bool | Enable local light | ... |
| `LocalLightSourceIntensity` | float | Local light intensity | `2` |
| `LocalLightSourceOverrideSettings` | bool | Override light settings | ... |
| `TimelineAutomaticLightingDefaultSetup` | guid | Auto-lighting setup for timelines | ... |
| `TimelineAutomaticLightingDisableFlip` | bool | Disable lighting flip | `False` |
| `ClothMainWindFrequency` | float | Cloth wind frequency | `3` |
| `ClothMainWindSpeed` | float | Cloth wind speed | `3` |
| `ClothMaxWindDirectionOffset` | float | Max wind direction offset | `45` |
| `ClothWindDirectionOffsetFrequency` | float | Wind direction change rate | `1` |
| `ClothWindSpeed` | float | Cloth-specific wind speed | `0` |
| `ClothWindVariance` | float | Wind variance | `0` |

_(Note: `EnvironmentEffect1`/`2`/`3` variants exist for multiple simultaneous effects)_

### Atmosphere → Camera

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `FarPlane` | float | Camera far clip plane | `1000` |
| `NearPlane` | float | Camera near clip plane | `0.1` |

### Atmosphere → Fog → FogLayer0/FogLayer1

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `BlendWithSky` | bool | Blend fog with sky | `False` |
| `Color` | fvec3 | Fog color (RGB) | `0.859 0.725 0.859` |
| `Density` | float | Fog density | `0.003` |
| `Enabled` | bool | Layer enabled | `True` |
| `FarEnd` | float | Fog far end distance | `500` |
| `NearStart` | float | Fog near start distance | `15` |
| `HeightStart` | float | Height fog start | `0` |
| `MaxHeight` | float | Height fog max | `100` |
| `Intensity` | float | Fog intensity multiplier | `100` |

### Atmosphere → PostProcessing

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `Bloom` | bool | Enable bloom | `True` |
| `Amount` | float | Bloom amount | `2` |
| `Threshold` | float | Bloom threshold | `0.4` |
| `GodRays` | bool | Enable god rays | `True` |
| `GodRaysPower` | float | God ray power | `12` |
| `GodRaysRayIntensity` | float | Ray intensity | `1` |
| `GodRaysThreshold` | float | God ray threshold | `0` |
| `GradingLut` | FixedString | Color grading LUT reference | _(empty)_ |
| `GradingLutEnabled` | bool | Enable LUT color grading | `False` |
| `DOFAperature` | float | Depth of field aperture | `13.45` |
| `LensFlareEnabled` | bool | Enable lens flare | `False` |
| `LensFlareChromaticDistortion` | float | Chromatic aberration | `0.89` |
| `LensFlareGhostDispersal` | float | Ghost dispersal | `0.12` |
| `LensFlareHaloWidth` | float | Halo width | `0.69` |
| `LensFlareIntensity` | float | Lens flare intensity | `0.01` |
| `LensFlareTreshold` | float | Lens flare threshold | `4.67` |
| `ToneMapHighlightsFixAmount` | float | Tonemap highlight fix | `0.6` |
| `Vignette` | bool | Enable vignette | `False` |
| `VignetteColor` | fvec3 | Vignette color | `0 0 0` |
| `VignetteIntensity` | float | Vignette intensity | `0.17` |
| `VignettePower` | float | Vignette falloff | `5.05` |
| `WhiteBalanceTemperature` | float | Color temperature (Kelvin) | `6500` |
| `WhiteBalanceTint` | float | Color tint offset | `0` |

### PostProcessing → ExposureSettings → Object

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `Exposure` | bool | Enable auto-exposure | ... |
| `ExposureCompensation` | float | Exposure compensation EV | ... |
| `ExposureMax` | float | Maximum exposure | ... |
| `ExposureMin` | float | Minimum exposure | ... |
| `ExposureMaxPercentile` | float | _(optional)_ Max percentile | ... |
| `ExposureMinPercentile` | float | _(optional)_ Min percentile | ... |
| `ExposureMeteringMode` | int32 | _(optional)_ Metering mode | ... |

### PostProcessing → NewColorCorrection (Newer Format)

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `Contrast` | float | Global contrast | ... |
| `Highlights` | float | Highlights adjustment | ... |
| `Shadows` | float | Shadows adjustment | ... |
| `Saturation` | float | Global saturation | ... |
| `Hue` | float | Hue shift | ... |
| `Pivot` | float | Contrast pivot point | ... |
| `LutApplyMode` | int32 | LUT application mode | ... |
| `LutBlendFactors` | fvec2 | LUT blend weights | ... |

Each **range node** (DarkRange, GlobalRange, HighlightRange, MidtonesRange, ShadowRange, SpecularRange):

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `ExposureShift` | float | Per-range exposure shift | ... |
| `Saturation` | float | Per-range saturation | ... |
| `XYOffset` | fvec2 | Per-range color offset | ... |

### PostProcessing → ColorCorrection (Older Format)

| Attribute | Type | Description |
|-----------|------|-------------|
| `HighlightsRangeBegin` | float | Highlights range start |
| `ShadowsRangeEnd` | float | Shadows range end |

Each **range node** (GlobalRange, HighlightsRange, MidtonesRange, ShadowsRange):

| Attribute | Type | Description |
|-----------|------|-------------|
| `Contrast` | fvec4 | Per-range contrast (RGBA) |
| `Gain` | fvec4 | Per-range gain (RGBA) |
| `Gamma` | fvec4 | Per-range gamma (RGBA) |
| `Offset` | fvec4 | Per-range offset (RGBA) |
| `Saturation` | fvec4 | Per-range saturation (RGBA) |

### Child: Labels

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `Object` | FixedString | Scene label/tag | `EXT_NIGHT` |

### Cross-References

| From | To | Via |
|------|----|-----|
| AtmosphereBank.Atmosphere.EnvironmentEffect | EffectBank.ID | Environment effect |
| AtmosphereBank.Labels | TimelineSceneBank.Labels | Shared scene tagging system |

### Notes

- **Most attribute-rich bank type** — hundreds of attributes across nested hierarchy
- Two color correction formats exist: `NewColorCorrection` (modern, range-based) and `ColorCorrection` (legacy, RGBA curves)
- Often co-located with VirtualTextureBank in the same `_merged.lsx` file
- `InheritanceFlags` on Atmosphere controls which settings cascade from parent atmospheres

---

## LightingBank

> Defines lighting setups — sun, sky light, fog, SSAO, volumetric clouds, and shadow configuration.
> Often co-located with EffectBank in light source files.

### Region Structure

```xml
<region id="LightingBank">
  <node id="LightingBank">
    <children>
      <node id="Resource"> ... </node>
    </children>
  </node>
</region>
```

### Node Hierarchy

```
LightingBank (region + root node)
└── Resource
    └── Lighting
        ├── Fog
        │   ├── FogLayer0
        │   └── FogLayer1
        ├── SSAOSettings
        ├── SkyLight
        ├── Sun
        │   └── CoverageSettings
        ├── TimelineFog
        │   ├── FogLayer0
        │   └── FogLayer1
        └── VolumetricCloudsSettings
            └── CoverageSettings
```

### Resource Attributes

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `ID` | FixedString | UUID primary key | ... |
| `Name` | LSString | Lighting setup name | `VFX_Static_Cinematic_MyconidLight_01` |
| `DisplayName` | TranslatedString | _(optional)_ UI label | ... |
| `Localized` | bool | Localization flag | ... |
| `_OriginalFileVersion_` | int64 | Engine version stamp | ... |

### Lighting (Root Container)

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `TimelineFogOverride` | bool | Override fog for timelines | `False` |

### Lighting → Fog → FogLayer0/FogLayer1

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `Albedo` | fvec3 | Fog color | (RGB) |
| `Density0` | float | Primary density | ... |
| `Density1` | float | Secondary density | ... |
| `Enabled` | bool | Layer enabled | ... |
| `Height0` | float | Height start | ... |
| `Height1` | float | Height end | ... |
| `NoiseCoverage` | float | Noise coverage amount | ... |
| `NoiseFrequency` | fvec3 | Noise frequency per axis | ... |
| `NoiseRotation` | fvec3 | Noise rotation | ... |
| `NoiseWind` | fvec3 | Noise wind movement | ... |

_(Note: LightingBank fog uses `Albedo`/`Density0`/`Density1`/`NoiseCoverage`/etc. — different attributes from AtmosphereBank fog)_

### Lighting → SSAOSettings

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `Bias` | float | SSAO bias | `0.2` |
| `DirectLightInfluence` | float | Direct light influence on AO | `0` |
| `Enabled` | bool | SSAO enabled | `True` |
| `Intensity` | float | AO intensity | `1.2` |
| `Radius` | float | AO sample radius | `1.5` |

### Lighting → SkyLight

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `Color` | fvec3 | Sky light color | `0.86 0.9 1` |
| `Intensity` | float | Sky light intensity | `20000` |
| `Kelvin` | float | Color temperature | `6445.8965` |
| `UseTemperature` | bool | Use Kelvin temperature | `False` |
| `PhysicalModel` | int32 | Lighting model | `0` |
| `ScatteringEnabled` | bool | Atmospheric scattering | `False` |
| `ScatteringIntensity` | float | Scatter intensity | `35000` |
| `ScatteringSunIntensity` | float | Sun scatter intensity | `120000` |
| `SkydomeEnabled` | bool | Enable skydome | `False` |
| `SkydomeTex` | FixedString | Skydome texture UUID | _(empty)_ |

### Lighting → Sun

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `SunColor` | fvec3 | Sun color | `1 0.92 0.85` |
| `SunIntensity` | float | Sun intensity | `120000` |
| `Pitch` | float | Sun pitch angle | `45` |
| `Yaw` | float | Sun yaw angle | `270` |
| `LightSize` | float | Sun angular size | `0.53` |
| `LightDistance` | float | Sun distance | `150` |
| `Kelvin` | float | Sun color temperature | `6445.8965` |
| `UseTemperature` | bool | Use Kelvin temperature | `False` |
| `ShadowEnabled` | bool | Enable shadows | `False` |
| `ShadowBias` | float | Shadow bias | `0.05` |
| `ShadowFade` | float | Shadow fade distance | `0.15` |
| `ShadowFarPlane` | float | Shadow far plane | `50` |
| `ShadowNearPlane` | float | Shadow near plane | `0.01` |
| `ShadowObscurity` | uint8 | Shadow obscurity mode | `1` |
| `SunlightObscurity` | uint8 | Sunlight obscurity mode | `0` |
| `CascadeCount` | uint8 | Shadow cascade count | `2` |
| `CascadeSpread` | float | Shadow cascade spread | `0.5` |
| `LocalCoverageEnabled` | bool | Local cloud coverage | ... |
| `LocalCoverageScalar` | float | Coverage scalar | ... |

### Sun/VolumetricClouds → CoverageSettings

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `EndHeight` | float | Cloud coverage end height | `4000` |
| `StartHeight` | float | Cloud coverage start height | `1500` |
| `HorizonDistance` | float | Horizon distance | `35000` |
| `Offset` | fvec2 | Coverage offset | `0 0` |
| `TexResourceGUID` | FixedString | Coverage texture UUID | _(empty)_ |

### Lighting → VolumetricCloudsSettings

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `Enabled` | bool | Enable volumetric clouds | ... |
| `Density` | float | Cloud density | ... |
| `BaseColor` | fvec3 | Cloud base color | ... |
| `TopColor` | fvec3 | Cloud top color | ... |
| `Intensity` | float | Cloud lighting intensity | ... |
| `AmbientLightFactor` | float | Ambient light contribution | ... |
| `SunLightFactor` | float | Sun light contribution | ... |
| `ShadowFactor` | float | Shadow factor | ... |
| `ForwardScatteringG` | float | Forward scattering (Henyey-Greenstein) | ... |
| `BackwardScatteringG` | float | Backward scattering | ... |
| `DetailScale` | float | Detail noise scale | ... |
| `CoverageStartDistance` | float | Cloud start distance | ... |
| `CoverageEndDistance` | float | Cloud end distance | ... |
| `CoverageWindSpeed` | float | Cloud wind speed | ... |
| `SunRayLength` | float | Sun ray length through clouds | ... |
| `LODDistance` | float | Cloud LOD distance | ... |

_(Full volumetric clouds have ~25 attributes)_

### Cross-References

| From | To | Via |
|------|----|-----|
| LightingBank.ID | AtmosphereBank (indirect) | Atmosphere lighting reference |
| LightingBank co-located with | EffectBank | Same `_merged.lsx` file |

### Notes

- Only 1 instance in Shared — LightingBank defines scene-level lighting presets
- **Always co-located with EffectBank** — light source `_merged.lsx` files contain both banks
- Fog attributes differ from AtmosphereBank fog (LightingBank uses `Albedo`, `Density0`/`Density1`, noise params)

---

## LightCookieBank

> Defines light cookie textures — projected shadow/pattern maps for light sources.
> Each entry includes a grid of boolean coverage data (~128 cells).

### Region Structure

```xml
<region id="LightCookieBank">
  <node id="LightCookieBank">
    <children>
      <node id="Resource"> ... </node>
    </children>
  </node>
</region>
```

### Node Hierarchy

```
LightCookieBank (region + root node)
└── Resource
    └── Data                     ← repeated ~128 times (coverage grid)
        └── Object (bool)
```

### Resource Attributes

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `ID` | FixedString | UUID primary key | `766c5cbd-...` |
| `Name` | LSString | Cookie name | `Gobo_Bamboo_A` |
| `TextureName` | guid | UUID → TextureBank | `37870237-...` |
| `BrightnessThreshold` | int32 | Coverage threshold | `10` |
| `Localized` | bool | Localization flag | `False` |
| `_OriginalFileVersion_` | int64 | Engine version stamp | ... |

### Child: Data (Coverage Grid)

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `Object` | bool | Grid cell coverage (True = shadow) | `True` |

### Cross-References

| From | To | Via |
|------|----|-----|
| LightCookieBank.TextureName | TextureBank.ID | Cookie texture source |

### Notes

- 2 instances in Shared, 1 in Gustav
- The `Data` children form a flattened 2D grid (~128 cells) representing the light cookie's coverage pattern
- Used for window shadows, foliage dappling, gobo patterns on spotlights

---

## PhysicsBank

> Registers physics collision assets — references to compiled `.bin` physics files.
> Flat resource structure — simplest bank type.

### Region Structure

```xml
<region id="PhysicsBank">
  <node id="PhysicsBank">
    <children>
      <node id="Resource"> ... </node>
    </children>
  </node>
</region>
```

### Resource Attributes

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `ID` | FixedString | UUID primary key | `2da5bcca-587e-dd4f-5fc3-9276d840d36a` |
| `Name` | LSString | Physics asset name | `BLD_City_Road_Paving_Rubble_A` |
| `SourceFile` | LSString | Physics binary file (.bin) | `Public/Shared/Assets/Tilesets/City/.../.bin` |
| `Template` | FixedString | Template reference path | `Public/Shared/Assets/Tilesets/City/...` |
| `Localized` | bool | Localization flag | `False` |
| `_OriginalFileVersion_` | int64 | Engine version stamp | `144115196665791066` |

### Cross-References

| From | To | Via |
|------|----|-----|
| PhysicsBank.ID | GameObjects.PhysicsTemplate | Object physics collision |
| PhysicsBank.ID | TileSetBank.Tile.PhysicsGUID | Tile physics collision |

### Notes

- 51 instances in Shared, 1 in Gustav
- Flat structure — no child nodes
- Physics data is compiled into `.bin` files; the bank just registers them

---

## MeshProxyBank

> Registers mesh proxy assets — simplified LOD meshes for distance rendering.
> Flat resource structure.

### Region Structure

```xml
<region id="MeshProxyBank">
  <node id="MeshProxyBank">
    <children>
      <node id="Resource"> ... </node>
    </children>
  </node>
</region>
```

### Resource Attributes

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `ID` | FixedString | UUID primary key | `125d8105-...` |
| `Name` | LSString | Proxy mesh name | `VFX_Proxy_CRA_Crash_Shockwave_Trees_01` |
| `SourceFile` | LSString | GR2 source file | `Public/Shared/Assets/.../file.GR2` |
| `Template` | FixedString | Template mesh reference | `Public/Shared/Assets/.../file.MeshName.0` |
| `Localized` | bool | _(optional)_ Localization flag | `False` |
| `_OriginalFileVersion_` | int64 | Engine version stamp | ... |

### Notes

- Only 1 instance in Shared
- `Localized` attribute is optional — some entries omit it
- Used for VFX proxy meshes (collision/interaction proxies for particle effects)

---

## TileSetBank

> Defines tile sets — collections of visual + physics tiles for modular level construction
> (walls, floors, pillars, etc.).

### Region Structure

```xml
<region id="TileSetBank">
  <node id="TileSetBank">
    <children>
      <node id="Resource"> ... </node>
    </children>
  </node>
</region>
```

### Node Hierarchy

```
TileSetBank (region + root node)
└── Resource
    └── TileSet                        ← single child
        ├── IsRoof (bool)              ← roof flag
        └── Tile                       ← repeated (individual tiles)
            ├── TileGUID               (guid) ← tile identifier
            ├── VisualGUID             (FixedString) ← UUID → VisualBank
            ├── PhysicsGUID            (FixedString) ← UUID → PhysicsBank
            └── InvisibleClimbingHelperPhysicsGUID (FixedString) ← climbing collision
```

### Resource Attributes

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `ID` | FixedString | UUID primary key | `f7de2f7d-d19f-1c0a-40c5-3009c4d2efb5` |
| `Name` | LSString | Tile set name | `WALL_GEN_Rope_A` |
| `EditorSourceFile` | LSString | Editor source file (.set) | `Editor/Mods/Gustav/TileSet/WALL_GEN_Rope_A.set` |
| `Localized` | bool | Localization flag | `False` |
| `_OriginalFileVersion_` | int64 | Engine version stamp | `144115196665791066` |

### Child: TileSet

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `IsRoof` | bool | Whether this is a roof tile set | `False` |

### TileSet → Tile

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `TileGUID` | guid | Tile identifier UUID | `6cef9527-...` |
| `VisualGUID` | FixedString | UUID → VisualBank | `7f421a96-...` |
| `PhysicsGUID` | FixedString | UUID → PhysicsBank | `9eb00d29-...` |
| `InvisibleClimbingHelperPhysicsGUID` | FixedString | Climbing collision UUID | `00000000-...` |

### Cross-References

| From | To | Via |
|------|----|-----|
| TileSetBank.Tile.VisualGUID | VisualBank.ID | Tile visual |
| TileSetBank.Tile.PhysicsGUID | PhysicsBank.ID | Tile physics collision |

### Notes

- 167 instances in Shared — extensive for modular level design
- `InvisibleClimbingHelperPhysicsGUID` is often null UUID — only used for climbable surfaces
- See also SplineSetBank for a similar structure

---

## SplineSetBank

> Defines spline sets — similar to TileSetBank but for spline-based placement (cliffs, paths).
> Uses the same TileSet → Tile hierarchy but with fewer tile attributes.

### Region Structure

```xml
<region id="SplineSetBank">
  <node id="SplineSetBank">
    <children>
      <node id="Resource"> ... </node>
    </children>
  </node>
</region>
```

### Node Hierarchy

```
SplineSetBank (region + root node)
└── Resource
    └── TileSet                     ← single child (NO attributes — no IsRoof)
        └── Tile                    ← repeated
            ├── TileGUID            (guid) ← tile identifier
            └── VisualGUID          (FixedString) ← UUID → VisualBank
```

### Resource Attributes

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `ID` | FixedString | UUID primary key | `df572cbf-...` |
| `Name` | LSString | Spline set name | `SPL_NAT_Cliff_Sandstone_A` |
| `EditorSourceFile` | LSString | Editor source file (.set) | `Editor/Mods/Gustav/SplineSet/SPL_NAT_Cliff_Sandstone_A.set` |
| `Localized` | bool | Localization flag | `False` |
| `_OriginalFileVersion_` | int64 | Engine version stamp | `144115188075855879` |

### TileSet → Tile

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `TileGUID` | guid | Tile identifier UUID | `e1914f54-...` |
| `VisualGUID` | FixedString | UUID → VisualBank | `fe5d92ea-...` |

### Key Differences from TileSetBank

| Aspect | TileSetBank | SplineSetBank |
|--------|-------------|---------------|
| TileSet has `IsRoof` | Yes | No |
| Tile has `PhysicsGUID` | Yes | No |
| Tile has `InvisibleClimbingHelperPhysicsGUID` | Yes | No |
| Tile attributes | 4 | 2 |
| Purpose | Wall/floor modules | Cliff/path splines |

### Notes

- Only 1 instance in Shared
- Used for natural environment features that follow spline curves (cliff faces, riverbanks)

---

## TerrainBrushBank

> Defines terrain brush materials — texture configurations for terrain painting.
> Flat structure with extensive texture and gradient parameters.

### Region Structure

```xml
<region id="TerrainBrushBank">
  <node id="TerrainBrushBank">
    <children>
      <node id="Resource"> ... </node>
    </children>
  </node>
</region>
```

### Resource Attributes

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `ID` | FixedString | UUID primary key | `95780be3-...` |
| `Name` | LSString | Brush name | `TT_Ground_Moss_A_Imposter` |
| `MaterialType` | uint8 | Material type enum | `3` |
| `BaseColorMap` | FixedString | UUID → TextureBank (color texture) | `032d8a3c-...` |
| `NormalMap` | FixedString | UUID → TextureBank (normal map) | `edb2a0b1-...` |
| `PhysicalMap` | FixedString | UUID → TextureBank (roughness/metallic) | `ac371ec7-...` |
| `Tiling` | float | Texture tiling frequency | `0.02` |
| `HeightScale` | float | Height map scale | `3.5` |
| `HeightOffset` | float | Height map offset | `0` |
| `HeightContrast` | float | Height map contrast | `1` |
| `AlphaThreshold` | float | Alpha test threshold | `0` |
| `UseDetailNormalMap` | bool | Enable detail normal | `True` |
| `DetailNormalMap` | FixedString | UUID → TextureBank (detail normal) | `079cee24-...` |
| `DetailNormalScale` | float | Detail normal strength | `5` |
| `DetailNormalTiling` | float | Detail normal tiling | `0.003` |
| `UseHeightGradient` | bool | Enable height-based color gradient | `False` |
| `GradientBottomHeightColor` | fvec3 | Gradient bottom color | `0.139 0.154 0.111` |
| `GradientMidHeightColor` | fvec3 | Gradient mid color | `0.639 0.494 0.28` |
| `GradientHeightBottom` | float | Gradient bottom height | `-0.25` |
| `GradientHeightMidPoint` | float | Gradient mid point | `0.1` |
| `GradientHeightTop` | float | Gradient top height | `10.5` |
| `GradientRoughnessPower` | float | Gradient roughness power | `5` |
| `GradientRoughnessReach` | float | Gradient roughness reach | `0.4` |
| `Localized` | bool | Localization flag | `False` |
| `_OriginalFileVersion_` | int64 | Engine version stamp | `144115188075855888` |

### Cross-References

| From | To | Via |
|------|----|-----|
| TerrainBrushBank.BaseColorMap | TextureBank.ID | Color texture |
| TerrainBrushBank.NormalMap | TextureBank.ID | Normal map texture |
| TerrainBrushBank.PhysicalMap | TextureBank.ID | Physical properties texture |
| TerrainBrushBank.DetailNormalMap | TextureBank.ID | Detail normal texture |

### Notes

- Only 2 instances in Shared
- 25 attributes on Resource — heavily focused on texture layering and height-based gradients
- Used by the terrain system for landscape painting in the editor

---

## Multi-Region Co-location Patterns

Environment bank files frequently contain multiple region types:

| Primary Bank | Co-located With | Example |
|-------------|----------------|---------|
| AtmosphereBank | VirtualTextureBank | Atmosphere asset bundles |
| LightingBank | EffectBank | Light source definitions |
| DiffusionProfileBank | VirtualTextureBank | SSS material bundles |
| TileSetBank | VisualBank, SkeletonBank, PhysicsBank, MaterialBank, VirtualTextureBank | Building asset bundles |
