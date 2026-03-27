# Node: `Resource`

> **Region**: [AtmosphereBank](_REGION.md)
> **Child Depth**: 5+ (Resource → Atmosphere → PostProcessing → NewColorCorrection → Range nodes)

---

## Node Hierarchy

```
Resource
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

## Attributes

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

## Child: Atmosphere (Core Settings)

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `WindDirection` | float | Wind direction in degrees | `69` |
| `WindSpeed` | float | Wind speed | `0.5` |
| `InheritanceFlags` | uint32 | Which settings to inherit | `0` |
| `EnvironmentEffect` | FixedString | UUID → [EffectBank](../EffectBank/_REGION.md) | _(empty or UUID)_ |
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

## Atmosphere → Camera

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `FarPlane` | float | Camera far clip plane | `1000` |
| `NearPlane` | float | Camera near clip plane | `0.1` |

## Atmosphere → Fog → FogLayer0/FogLayer1

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

## Atmosphere → PostProcessing

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

## PostProcessing → ExposureSettings → Object

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `Exposure` | bool | Enable auto-exposure | ... |
| `ExposureCompensation` | float | Exposure compensation EV | ... |
| `ExposureMax` | float | Maximum exposure | ... |
| `ExposureMin` | float | Minimum exposure | ... |
| `ExposureMaxPercentile` | float | _(optional)_ Max percentile | ... |
| `ExposureMinPercentile` | float | _(optional)_ Min percentile | ... |
| `ExposureMeteringMode` | int32 | _(optional)_ Metering mode | ... |

## PostProcessing → NewColorCorrection (Newer Format)

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

## PostProcessing → ColorCorrection (Older Format)

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

## Child: Labels

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `Object` | FixedString | Scene label/tag | `EXT_NIGHT` |

## Cross-References

| From | To | Via |
|------|----|-----|
| Atmosphere.EnvironmentEffect | [EffectBank](../EffectBank/_REGION.md) | Environment effect |
| Labels | [TimelineSceneBank](../TimelineSceneBank/_REGION.md) | Shared scene tagging system |
