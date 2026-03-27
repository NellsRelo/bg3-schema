# Scene Content Banks

> Scene content banks define dialogs, timelines, voice barks, visual effects, scripts, and sounds.
> These banks control narrative content, cinematic sequences, and gameplay feedback.

---

## DialogBank

> Defines dialog tree resources — metadata entries that reference dialog `.lsj` files.
> Dialog content itself is in the source files; the bank registers them for the engine.

### Region Structure

```xml
<region id="DialogBank">
  <node id="DialogBank">
    <children>
      <node id="Resource"> ... </node>
    </children>
  </node>
</region>
```

### File Locations

| Source | Path Pattern | Content |
|--------|-------------|---------|
| Shared | `Content/Assets/Dialogs/.../_merged.lsx` | Generic/combat dialogs (9 files) |
| Gustav | `Content/Assets/Dialogs/.../_merged.lsx` | Campaign dialogs (104 files) |

### Node Hierarchy

```
DialogBank (region + root node)
└── Resource
    └── SpeakerSlotsWithLines    ← repeated (speakers that have lines)
        └── HasLines (bool)
```

### Resource Attributes

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `ID` | FixedString | UUID primary key | `ca90c53f-...` |
| `Name` | LSString | Dialog name | `CMB_AD_LookingForHiddenPlayer` |
| `SourceFile` | LSString | Dialog source file (.lsj) | `Mods/Shared/Story/Dialogs/.../X.lsj` |
| `EnableTimeline` | bool | Whether dialog uses timeline system | `True` |
| `automated` | bool | Automated (non-interactive) dialog | `True` |
| `isBehaviour` | bool | Behavior-triggered dialog | `False` |
| `isPrivateDialog` | bool | Private (non-overheard) dialog | `False` |
| `isSubbedDialog` | bool | Subtitle-only dialog (no VO) | `False` |
| `isWorld` | bool | World dialog (ambient) | `False` |
| `AllowDeadSpeakers` | bool | Allow dead NPCs as speakers | `False` |
| `BlockFTB` | bool | Block fast-travel during dialog | `False` |
| `IsAllowingJoinCombat` | bool | Allow joining combat during dialog | `False` |
| `_OriginalFileVersion_` | int64 | Engine version stamp | `144115207403209030` |

### Child: SpeakerSlotsWithLines

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `HasLines` | bool | Whether this speaker slot has dialog lines | `True` |

### Cross-References

| From | To | Via |
|------|----|-----|
| DialogBank.ID | TimelineBank.DialogResourceId | Timeline dialog link |
| DialogBank.SourceFile | Dialog `.lsj` files | Actual dialog content |

### Attribute Naming Note

Several DialogBank attributes use **lowercase camelCase** (`automated`, `isBehaviour`, `isWorld`) — unusual compared to other banks which use PascalCase. This appears to be a legacy naming convention.

---

## TimelineBank

> Registers timeline resources — cinematic/dialog sequences that control camera, animation,
> audio, and staging over time. Links to DialogBank resources.

### Region Structure

```xml
<region id="TimelineBank">
  <node id="TimelineBank">
    <children>
      <node id="Resource"> ... </node>
    </children>
  </node>
</region>
```

### File Locations

| Source | Path Pattern | Content |
|--------|-------------|---------|
| Shared | `Content/Generated/[PAK]_GeneratedDialogTimelines/_merged.lsx` | Auto-generated dialog timelines |
| Gustav | `Content/Generated/.../_merged.lsx` | Campaign timelines |

### Node Hierarchy

```
TimelineBank (region + root node)
└── Resource
    └── DependencyCache          ← repeated (resource dependencies)
        └── Object (guid)
```

### Resource Attributes

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `ID` | FixedString | UUID primary key | `01d95486-...` |
| `Name` | LSString | Timeline name | `GEB_AD_Noticed_AttackedAnimal` |
| `SourceFile` | LSString | Compiled timeline file (.lsf) | `Public/Shared/Timeline/Generated/X.lsf` |
| `EditorSourceFile` | LSString | Editor source file (.tml) | `Editor/Mods/.../X.tml` |
| `DialogResourceId` | guid | UUID → DialogBank | `c62f94b6-...` |
| `IsGenerated` | bool | Whether automatically generated | `True` |
| `EditorTimelineType` | int32 | Timeline type (0=standard, 4/5=cinematic) | `0` |
| `BodyPartMocap` | int32 | Body part mocap flags (1=face, 3=body+face) | `3` |
| `FadeOutDuration` | float | _(optional)_ Fade-out time (-1 = no fade) | `0`, `-1` |
| `FadeOutOnEnd` | bool | _(optional)_ Fade to black on end | `False` |
| `Localized` | bool | _(optional)_ Localization flag | `False` |
| `_OriginalFileVersion_` | int64 | Engine version stamp | `144115207403209032` |

### Child: DependencyCache

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `Object` | guid | UUID of dependent resource | `c62f94b6-...` |

### Cross-References

| From | To | Via |
|------|----|-----|
| TimelineBank.ID | TimelineSceneBank (assembled scenes) | Scene composition |
| TimelineBank.DialogResourceId | DialogBank.ID | Dialog link |

---

## TimelineSceneBank

> Composes timeline scenes from timelines and speaker configurations.
> Metadata layer that describes how timelines are assembled into complete scenes.

### Region Structure

```xml
<region id="TimelineSceneBank">
  <node id="TimelineSceneBank">
    <children>
      <node id="Resource"> ... </node>
    </children>
  </node>
</region>
```

### Node Hierarchy

```
TimelineSceneBank (region + root node)
└── Resource
    └── Labels                   ← repeated, optional (scene labels/tags)
        └── Object (FixedString)
```

### Resource Attributes

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `ID` | FixedString | UUID primary key | `0059442a-...` |
| `Name` | LSString | Scene name | `_Add_EXT_NIGHT_Px1_Hyena` |
| `SourceFile` | string | Source file path | `Public/.../X.lsx` |
| `SceneType` | uint8 | Scene type (1=dialog, 2=cinematic, 4=ambient) | `1` |
| `AdditionalSpeakerCount` | int32 | Extra speakers beyond default (0-5) | `1` |
| `_OriginalFileVersion_` | int64 | Engine version stamp | `144115207403209026` |

### Child: Labels

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `Object` | FixedString | Scene label/tag | `EXT_NIGHT` |

### Notes

- `SourceFile` uses type `string` (not `LSString`) — unusual among bank types
- Labels (like `EXT_NIGHT`, `CAMP`, `DUNGEON`) tag scenes for scheduling/filtering
- `SceneType` values observed: 1 (dialog), 2 (cinematic), 4 (ambient)
- Only 1 instance in Shared, 1 in Gustav — scene banks are generated files

---

## VoiceBarkBank

> Registers voice bark resources — short voiced lines that play outside dialog trees
> (combat callouts, ambient reactions, etc.).

### Region Structure

```xml
<region id="VoiceBarkBank">
  <node id="VoiceBarkBank">
    <children>
      <node id="Resource"> ... </node>
    </children>
  </node>
</region>
```

### File Locations

| Source | Path Pattern | Content |
|--------|-------------|---------|
| Gustav | `Content/Assets/Voicebarks/Act1/.../_merged.lsx` | Act 1 voice barks |
| Gustav | `Content/Assets/Voicebarks/Act2/.../_merged.lsx` | Act 2 voice barks |
| Gustav | `Content/Assets/Voicebarks/Act3/.../_merged.lsx` | Act 3 voice barks |

### Resource Attributes

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `ID` | FixedString | UUID primary key | `12cef6a8-...` |
| `SourceFile` | LSString | Voice bark source file (.lsj) | `Mods/Gustav/Story/VoiceBarks/.../X.lsj` |
| `Localized` | bool | Localization flag | `False` |
| `_OriginalFileVersion_` | int64 | Engine version stamp | ...  |

### Notes

- **No `Name` attribute** — the only bank type that lacks a human-readable name on Resource
- 56 instances in Gustav, 0 in Shared — voice barks are campaign-specific content
- Organized by game act (`Act1/`, `Act2/`, `Act3/`)
- Flat structure — no child nodes

---

## EffectBank

> Defines visual effects (VFX) — particle systems, overlays, lights, and sound triggers.
> The most deeply nested bank type (up to 5 levels deep).

### Region Structure

```xml
<region id="EffectBank">
  <node id="EffectBank">
    <children>
      <node id="Resource"> ... </node>
    </children>
  </node>
</region>
```

### File Locations

| Source | Path Pattern | Content |
|--------|-------------|---------|
| Shared | `Content/Assets/Effects/Effects/.../_merged.lsx` | Gameplay VFX (spells, actions) |
| Shared | `Content/Assets/Effects/Effects/[PAK]_LightSources/_merged.lsx` | Light source effects (co-located with LightingBank) |

### Node Hierarchy

```
EffectBank (region + root node)
└── Resource
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

### Resource Attributes

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

### Child: EffectComponents

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `ID` | guid | Component UUID | `54767a94-674f-49ec-816e-a367315d2cac` |
| `Name` | LSString | Component type | `OverlayMaterial`, `Light`, `ParticleSystem` |
| `StartTime` | float | Component start time | `0` |
| `EndTime` | float | Component end time | `0` |
| `Track` | uint32 | Timeline track index | `0` |

### EffectComponents → Properties → Property

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `AttributeName` | FixedString | Property name | `Alpha`, `Position` |
| `FullName` | FixedString | Qualified name | `Dynamic Parameters.Alpha`, `Offset` |
| `Input` | FixedString | Input binding | _(empty)_ |
| `Type` | uint8 | Property type enum | `6`, `8` |

### Properties → Property → Parameter

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `Name` | LSString | Parameter channel | `default`, `X`, `Y`, `Z`, `X Scale` |
| `Value` | float | Parameter value | `1`, `0` |

### Cross-References

| From | To | Via |
|------|----|-----|
| EffectBank.ID | GameObjects (StatusEffect, HitEffect, etc.) | Effect references in stats/game data |
| EffectBank.Dependencies.DependentResource.Object | Various banks | Material, texture, model dependencies |

### Notes

- 98 instances in Shared — covers all spell VFX, combat effects, ambient particles
- **Most deeply nested bank** — Resource → EffectComponents → Properties → Property → Parameter (5 levels)
- Often co-located with LightingBank in light source files
- Component `Name` identifies the VFX module type: `OverlayMaterial`, `Light`, `ParticleSystem`, `Sound`, `Decal`, etc.

---

## ScriptBank

> Registers script/behavior resources — references to compiled `.itemScript` and `.charScript` files.
> Lightweight registration — actual logic is in the source files.

### Region Structure

```xml
<region id="ScriptBank">
  <node id="ScriptBank">
    <children>
      <node id="Resource"> ... </node>
    </children>
  </node>
</region>
```

### Node Hierarchy

```
ScriptBank (region + root node)
└── Resource
    └── Parameters    ← empty node (parameters defined in script file)
```

### Resource Attributes

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `ID` | FixedString | UUID primary key | `01d15b11-...` |
| `Name` | LSString | Script name | `DOS2_GEN_ItemSetMaterial` |
| `SourceFile` | LSString | Script source file | `Public/Shared/Scripts/GEN_ItemSetMaterial.itemScript` |
| `_OriginalFileVersion_` | int64 | Engine version stamp | `144537400540922156` |

### Notes

- 7 instances in Shared, 7 in Gustav
- `Parameters` child node is always empty — parameters are defined within the script file itself
- Script types: `.itemScript` (item behaviors), `.charScript` (character behaviors)

---

## SoundBank

> Registers audio assets — individual sound events from Wwise `.bnk` sound banks.
> Flat resource structure with extensive audio metadata.

### Region Structure

```xml
<region id="SoundBank">
  <node id="SoundBank">
    <children>
      <node id="Resource"> ... </node>
    </children>
  </node>
</region>
```

### File Locations

| Source | Path Pattern | Content |
|--------|-------------|---------|
| Shared | `Content/Assets/Sounds/Actions/[PAK]_Actions/_merged.lsx` | Action sound events |
| Shared | `Content/Assets/Sounds/.../_merged.lsx` | Other sound categories |

### Resource Attributes

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `ID` | FixedString | UUID primary key | `007cf46b-0179-4145-9765-a3f257e8f387` |
| `Name` | LSString | Sound name | `Action_Loop_ArcaneArcher_GraspingArrow_Stop_01` |
| `SoundEvent` | FixedString | Wwise event name | `Action_Loop_ArcaneArcher_GraspingArrow_Stop_01` |
| `SoundEventID` | uint32 | Wwise event hash ID | `2998283788` |
| `SoundEventUUID` | guid | Sound event UUID | `0e76e27e-4727-4ebe-8671-151056823e72` |
| `SoundBank` | FixedString | Parent Wwise bank name | `ACTIONS` |
| `SourceFile` | LSString | Wwise bank file (.bnk) | `Public/Shared/Assets/Sound/ACTIONS.bnk` |
| `Duration` | float | Sound duration in seconds (-1 = looping) | `5.930666`, `-1` |
| `MaxDistance` | float | Maximum audible distance (0 = unlimited) | `50`, `0` |
| `SoundCategory` | int8 | Sound category enum | `0` |
| `SoundCodec` | int8 | Audio codec enum | `7` |
| `Preload` | bool | Pre-load audio data | `False` |
| `Internal` | bool | Internal engine sound | `True` |
| `DisplayName` | LSString | _(optional)_ UI display name | _(empty)_ |
| `GMSoundCategory` | int8 | _(optional)_ Game Master category | `0` |
| `GMSubSection` | LSString | _(optional)_ Game Master UI section | _(empty)_ |
| `Localized` | bool | Localization flag | `False` |
| `_OriginalFileVersion_` | int64 | Engine version stamp | `144115205255725357` |

### Cross-References

| From | To | Via |
|------|----|-----|
| SoundBank.ID | SkeletonBank.Bones.MapValue.SoundObjectIndex | Bone sound triggers |
| SoundBank.SoundEventID | Wwise audio engine | Runtime sound playback |

### Notes

- 80 instances in Shared — covers all gameplay sound effects
- `Duration = -1` indicates a looping sound
- `SoundCodec` value `7` appears to be the standard codec
- `GMSoundCategory`/`GMSubSection` are Game Master mode attributes (rare)
