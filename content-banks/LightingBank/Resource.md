# Node: `Resource`

> **Region**: [LightingBank](_REGION.md)
> **Child Depth**: 4+ (Resource → Lighting → Sun → CoverageSettings)

---

## Node Hierarchy

```
Resource
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

## Attributes

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `ID` | FixedString | UUID primary key | ... |
| `Name` | LSString | Lighting setup name | `VFX_Static_Cinematic_MyconidLight_01` |
| `DisplayName` | TranslatedString | _(optional)_ UI label | ... |
| `Localized` | bool | Localization flag | ... |
| `_OriginalFileVersion_` | int64 | Engine version stamp | ... |

## Lighting (Root Container)

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `TimelineFogOverride` | bool | Override fog for timelines | `False` |

## Lighting → Fog → FogLayer0/FogLayer1

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

## Lighting → SSAOSettings

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `Bias` | float | SSAO bias | `0.2` |
| `DirectLightInfluence` | float | Direct light influence on AO | `0` |
| `Enabled` | bool | SSAO enabled | `True` |
| `Intensity` | float | AO intensity | `1.2` |
| `Radius` | float | AO sample radius | `1.5` |

## Lighting → SkyLight

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

## Lighting → Sun

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

## Sun/VolumetricClouds → CoverageSettings

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `EndHeight` | float | Cloud coverage end height | `4000` |
| `StartHeight` | float | Cloud coverage start height | `1500` |
| `HorizonDistance` | float | Horizon distance | `35000` |
| `Offset` | fvec2 | Coverage offset | `0 0` |
| `TexResourceGUID` | FixedString | Coverage texture UUID | _(empty)_ |

## Lighting → VolumetricCloudsSettings

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

## Cross-References

| From | To | Via |
|------|----|-----|
| Resource.ID | [AtmosphereBank](../AtmosphereBank/_REGION.md) (indirect) | Atmosphere lighting reference |
| Co-located with | [EffectBank](../EffectBank/_REGION.md) | Same `_merged.lsx` file |
