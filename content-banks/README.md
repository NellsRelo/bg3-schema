# Content Banks Reference

> Content banks store visual, animation, scene, and environment assets in multi-region LSX files.
> They live in `Public/{ModName}/Content/` directories within each source pak.
>
> **Per-bank documentation** — each bank type has its own folder with `_REGION.md` + node files:
>
> **Visual (7):**
> [VisualBank](VisualBank/_REGION.md) · [CharacterVisualBank](CharacterVisualBank/_REGION.md) · [MaterialBank](MaterialBank/_REGION.md) · [MaterialPresetBank](MaterialPresetBank/_REGION.md) · [TextureBank](TextureBank/_REGION.md) · [VirtualTextureBank](VirtualTextureBank/_REGION.md) · [DiffusionProfileBank](DiffusionProfileBank/_REGION.md)
>
> **Animation (8):**
> [AnimationBank](AnimationBank/_REGION.md) · [AnimationBlueprintBank](AnimationBlueprintBank/_REGION.md) · [AnimationSetBank](AnimationSetBank/_REGION.md) · [SkeletonBank](SkeletonBank/_REGION.md) · [IKRigBank](IKRigBank/_REGION.md) · [ClothColliderBank](ClothColliderBank/_REGION.md) · [BlendSpaceBank](BlendSpaceBank/_REGION.md) · [FCurveBank](FCurveBank/_REGION.md)
>
> **Scene (7):**
> [DialogBank](DialogBank/_REGION.md) · [TimelineBank](TimelineBank/_REGION.md) · [TimelineSceneBank](TimelineSceneBank/_REGION.md) · [VoiceBarkBank](VoiceBarkBank/_REGION.md) · [EffectBank](EffectBank/_REGION.md) · [ScriptBank](ScriptBank/_REGION.md) · [SoundBank](SoundBank/_REGION.md)
>
> **Environment (8+1):**
> [AtmosphereBank](AtmosphereBank/_REGION.md) · [LightingBank](LightingBank/_REGION.md) · [LightCookieBank](LightCookieBank/_REGION.md) · [PhysicsBank](PhysicsBank/_REGION.md) · [MeshProxyBank](MeshProxyBank/_REGION.md) · [TileSetBank](TileSetBank/_REGION.md) · [SplineSetBank](SplineSetBank/_REGION.md) · [TerrainBrushBank](TerrainBrushBank/_REGION.md) · [DiffusionProfileBank](DiffusionProfileBank/_REGION.md) _(dual-listed)_

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

### Visual (7)

| Bank Type | Files (Shared) | Content | Child Depth |
|-----------|---------------|---------|-------------|
| [VisualBank](VisualBank/_REGION.md) | 54 | 3D model/mesh visual definitions | 3 (Resource → Objects, ClothParams, etc.) |
| [CharacterVisualBank](CharacterVisualBank/_REGION.md) | 17 | Character visual assemblies (slots + material overrides) | 3 (Resource → Slots, MaterialOverrides) |
| [MaterialBank](MaterialBank/_REGION.md) | 48 | Material/shader instance definitions | 2 (Resource → ScalarParams, Texture2DParams, etc.) |
| [MaterialPresetBank](MaterialPresetBank/_REGION.md) | 47 | Material override presets for character customization | 3 (Resource → Presets → ScalarParams, Vector3Params) |
| [TextureBank](TextureBank/_REGION.md) | 9 | Texture asset registrations (DDS references + dimensions) | 1 (flat) |
| [VirtualTextureBank](VirtualTextureBank/_REGION.md) | 263 | Virtual texture streaming asset registrations | 1 (flat) |
| [DiffusionProfileBank](DiffusionProfileBank/_REGION.md) | 17 | Subsurface scattering profiles (skin, cloth, foliage) | 1 (uses `DiffusionProfile` node, not `Resource`) |

### Animation (8)

| Bank Type | Files (Shared) | Content | Child Depth |
|-----------|---------------|---------|-------------|
| [AnimationBank](AnimationBank/_REGION.md) | 46 | Animation clip definitions | 1 (flat) |
| [AnimationBlueprintBank](AnimationBlueprintBank/_REGION.md) | 140 | Animation state machine blueprints | 2 (Resource → Params) |
| [AnimationSetBank](AnimationSetBank/_REGION.md) | 120 | Animation set groupings with subsets | 4 (Resource → AnimationSet → AnimationBank → AnimationSubSets) |
| [SkeletonBank](SkeletonBank/_REGION.md) | 243 | Skeleton/rig definitions with bone metadata | 2 (Resource → Bones map) |
| [IKRigBank](IKRigBank/_REGION.md) | 1 | Inverse kinematics rig configurations | 4 (Resource → BoneProperties → IKBone → Limits) |
| [ClothColliderBank](ClothColliderBank/_REGION.md) | 10 | Cloth simulation sphere/capsule colliders | 3 (Resource → Spheres → Links) |
| [BlendSpaceBank](BlendSpaceBank/_REGION.md) | 3 | 2D animation blend space definitions | 2 (Resource → Inputs) |
| [FCurveBank](FCurveBank/_REGION.md) | 8 | Function curve keyframe data | 2 (Resource → CurveKeys, CurveLimits) |

### Scene (7)

| Bank Type | Files (Shared/Gustav) | Content | Child Depth |
|-----------|----------------------|---------|-------------|
| [DialogBank](DialogBank/_REGION.md) | 9 / 104 | Dialog tree metadata (.lsj references) | 2 (Resource → SpeakerSlotsWithLines) |
| [TimelineBank](TimelineBank/_REGION.md) | 1 / 2 | Timeline/cinematic sequence registrations | 2 (Resource → DependencyCache) |
| [TimelineSceneBank](TimelineSceneBank/_REGION.md) | 1 / 1 | Timeline scene compositions with labels | 2 (Resource → Labels) |
| [VoiceBarkBank](VoiceBarkBank/_REGION.md) | 0 / 56 | Voice bark audio references (Gustav only) | 1 (flat, no Name attr) |
| [EffectBank](EffectBank/_REGION.md) | 98 | Visual effect definitions (VFX) | 5 (deepest: Resource → EffectComponents → Properties → Property → Parameter) |
| [ScriptBank](ScriptBank/_REGION.md) | 7 / 7 | Script/behavior registrations | 2 (Resource → Parameters) |
| [SoundBank](SoundBank/_REGION.md) | 80 | Wwise audio event registrations | 1 (flat) |

### Environment (8+1)

| Bank Type | Files (Shared/Gustav) | Content | Child Depth |
|-----------|----------------------|---------|-------------|
| [AtmosphereBank](AtmosphereBank/_REGION.md) | 1 / 1 | Atmosphere presets (lighting, fog, post-processing, wind) | 5+ (deepest bank — hundreds of attributes) |
| [LightingBank](LightingBank/_REGION.md) | 1 | Scene lighting setups (sun, sky, fog, SSAO, clouds) | 4+ (Resource → Lighting → Sun → CoverageSettings) |
| [LightCookieBank](LightCookieBank/_REGION.md) | 2 / 1 | Light cookie/gobo textures with coverage grids | 2 (Resource → Data ×128) |
| [PhysicsBank](PhysicsBank/_REGION.md) | 51 / 1 | Physics collision asset registrations | 1 (flat) |
| [MeshProxyBank](MeshProxyBank/_REGION.md) | 1 | Mesh proxy/LOD registrations | 1 (flat) |
| [TileSetBank](TileSetBank/_REGION.md) | 167 | Modular tile set definitions (walls, floors) | 3 (Resource → TileSet → Tile) |
| [SplineSetBank](SplineSetBank/_REGION.md) | 1 | Spline-based tile sets (cliffs, paths) | 3 (Resource → TileSet → Tile) |
| [TerrainBrushBank](TerrainBrushBank/_REGION.md) | 2 | Terrain painting brush materials (25 attributes) | 1 (flat) |
| [DiffusionProfileBank](DiffusionProfileBank/_REGION.md) | 17 | _(also listed under Visual — subsurface scattering)_ | — |

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
