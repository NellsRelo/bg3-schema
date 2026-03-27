# Content Banks Reference

> Content banks store visual, animation, scene, and environment assets in multi-region LSX files.
> They live in `Public/{ModName}/Content/` directories within each source pak.
>
> **Detailed per-bank documentation:**
> - [Visual Banks](01-visual-banks.md) — VisualBank, CharacterVisualBank, MaterialBank, MaterialPresetBank, TextureBank, VirtualTextureBank, DiffusionProfileBank
> - [Animation Banks](02-animation-banks.md) — AnimationBank, AnimationBlueprintBank, AnimationSetBank, SkeletonBank, IKRigBank, ClothColliderBank, BlendSpaceBank, FCurveBank
> - [Scene Banks](03-scene-banks.md) — DialogBank, TimelineBank, TimelineSceneBank, VoiceBarkBank, EffectBank, ScriptBank, SoundBank
> - [Environment Banks](04-environment-banks.md) — AtmosphereBank, LightingBank, LightCookieBank, PhysicsBank, MeshProxyBank, TileSetBank, SplineSetBank, TerrainBrushBank

## Key Facts

- **2,921 total Content files** across all sources (1,405 `.lsx` + 1,405 `.lsf` + 1 `.bin` in Shared alone)
- **883 multi-region files** (multiple bank types per file)
- **30 bank types** documented below
- Each bank uses `<region id="BankType">` with `<node id="Resource">` entries inside (except DiffusionProfileBank which uses `<node id="DiffusionProfile">`)
- All resources have an `ID` (FixedString UUID) primary key and `_OriginalFileVersion_` (int64)

## Common Multi-Region Patterns

| Pattern | Banks Combined | Typical Files |
|---------|---------------|---------------|
| Asset bundles | VirtualTextureBank + MaterialBank + VisualBank | 212 files — buildings, characters, effects |
| Character bundles | SkeletonBank + MaterialBank + TextureBank + AnimationSetBank + AnimationBank + VisualBank | Character body/creature paks |
| Preset bundles | CharacterVisualBank + MaterialPresetBank | Character editor presets |
| Light sources | LightingBank + EffectBank | Light source VFX definitions |
| Atmosphere bundles | AtmosphereBank + VirtualTextureBank | Environment atmosphere paks |
| SSS profiles | DiffusionProfileBank + VirtualTextureBank | Subsurface scattering material paks |

## Bank Types by Category

### Visual (7) → [01-visual-banks.md](01-visual-banks.md)

| Bank Type | Files (Shared) | Content | Child Depth |
|-----------|---------------|---------|-------------|
| `VisualBank` | 54 | 3D model/mesh visual definitions | 3 (Resource → Objects, ClothParams, etc.) |
| `CharacterVisualBank` | 17 | Character visual assemblies (slots + material overrides) | 3 (Resource → Slots, MaterialOverrides) |
| `MaterialBank` | 48 | Material/shader instance definitions | 2 (Resource → ScalarParams, Texture2DParams, etc.) |
| `MaterialPresetBank` | 47 | Material override presets for character customization | 3 (Resource → Presets → ScalarParams, Vector3Params) |
| `TextureBank` | 9 | Texture asset registrations (DDS references + dimensions) | 1 (flat) |
| `VirtualTextureBank` | 263 | Virtual texture streaming asset registrations | 1 (flat) |
| `DiffusionProfileBank` | 17 | Subsurface scattering profiles (skin, cloth, foliage) | 1 (uses `DiffusionProfile` node, not `Resource`) |

### Animation (8) → [02-animation-banks.md](02-animation-banks.md)

| Bank Type | Files (Shared) | Content | Child Depth |
|-----------|---------------|---------|-------------|
| `AnimationBank` | 46 | Animation clip definitions | 1 (flat) |
| `AnimationBlueprintBank` | 140 | Animation state machine blueprints | 2 (Resource → Params) |
| `AnimationSetBank` | 120 | Animation set groupings with subsets | 4 (Resource → AnimationSet → AnimationBank → AnimationSubSets) |
| `SkeletonBank` | 243 | Skeleton/rig definitions with bone metadata | 2 (Resource → Bones map) |
| `IKRigBank` | 1 | Inverse kinematics rig configurations | 4 (Resource → BoneProperties → IKBone → Limits) |
| `ClothColliderBank` | 10 | Cloth simulation sphere/capsule colliders | 3 (Resource → Spheres → Links) |
| `BlendSpaceBank` | 3 | 2D animation blend space definitions | 2 (Resource → Inputs) |
| `FCurveBank` | 8 | Function curve keyframe data | 2 (Resource → CurveKeys, CurveLimits) |

### Scene (7) → [03-scene-banks.md](03-scene-banks.md)

| Bank Type | Files (Shared/Gustav) | Content | Child Depth |
|-----------|----------------------|---------|-------------|
| `DialogBank` | 9 / 104 | Dialog tree metadata (.lsj references) | 2 (Resource → SpeakerSlotsWithLines) |
| `TimelineBank` | 1 / 2 | Timeline/cinematic sequence registrations | 2 (Resource → DependencyCache) |
| `TimelineSceneBank` | 1 / 1 | Timeline scene compositions with labels | 2 (Resource → Labels) |
| `VoiceBarkBank` | 0 / 56 | Voice bark audio references (Gustav only) | 1 (flat, no Name attr) |
| `EffectBank` | 98 | Visual effect definitions (VFX) | 5 (deepest: Resource → EffectComponents → Properties → Property → Parameter) |
| `ScriptBank` | 7 / 7 | Script/behavior registrations | 2 (Resource → Parameters) |
| `SoundBank` | 80 | Wwise audio event registrations | 1 (flat) |

### Environment (9) → [04-environment-banks.md](04-environment-banks.md)

| Bank Type | Files (Shared/Gustav) | Content | Child Depth |
|-----------|----------------------|---------|-------------|
| `AtmosphereBank` | 1 / 1 | Atmosphere presets (lighting, fog, post-processing, wind) | 5+ (deepest bank — hundreds of attributes) |
| `LightingBank` | 1 | Scene lighting setups (sun, sky, fog, SSAO, clouds) | 4+ (Resource → Lighting → Sun → CoverageSettings) |
| `LightCookieBank` | 2 / 1 | Light cookie/gobo textures with coverage grids | 2 (Resource → Data ×128) |
| `PhysicsBank` | 51 / 1 | Physics collision asset registrations | 1 (flat) |
| `MeshProxyBank` | 1 | Mesh proxy/LOD registrations | 1 (flat) |
| `TileSetBank` | 167 | Modular tile set definitions (walls, floors) | 3 (Resource → TileSet → Tile) |
| `SplineSetBank` | 1 | Spline-based tile sets (cliffs, paths) | 3 (Resource → TileSet → Tile) |
| `TerrainBrushBank` | 2 | Terrain painting brush materials (25 attributes) | 1 (flat) |
| `DiffusionProfileBank` | 17 | _(also listed under Visual — subsurface scattering)_ | — |

## Source Distribution

| Source | .lsx Files | Notes |
|--------|-----------|-------|
| Shared | 1,405 | Core visual, animation, and effect assets |
| SharedDev | ~1,138 | Extended/development assets |
| Gustav | ~63 | Campaign-specific assets (dialogs, voice barks, atmospheres) |
| GustavDev | ~314 | Campaign development assets (HLOD, cinematics) |
| GustavX | varies | Extended Edition assets |
| Engine | varies | Engine-level assets |
| Honour | varies | Honour mode assets |

## Bank Complexity Ranking

From simplest to most complex node hierarchy:

| Depth | Banks |
|-------|-------|
| **1** (flat) | PhysicsBank, TextureBank, VirtualTextureBank, MeshProxyBank, AnimationBank, SoundBank, VoiceBarkBank, TerrainBrushBank |
| **2** | MaterialBank, AnimationBlueprintBank, SkeletonBank, FCurveBank, BlendSpaceBank, DialogBank, TimelineBank, TimelineSceneBank, ScriptBank, LightCookieBank |
| **3** | CharacterVisualBank, MaterialPresetBank, TileSetBank, SplineSetBank, ClothColliderBank |
| **4** | AnimationSetBank, IKRigBank, LightingBank |
| **5+** | EffectBank (deepest — components → properties → parameters), AtmosphereBank (widest — hundreds of attributes across fog/post-processing/camera/color correction) |
