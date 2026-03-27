# Animation Content Banks

> Animation content banks define animation clips, state machines, skeletons, blend spaces,
> cloth physics colliders, and inverse kinematics rigs. These banks are referenced by
> VisualBank and CharacterVisualBank to bring characters and objects to life.

---

## AnimationBank

> Defines individual animation clips — single animation sequences bound to a skeleton.
> Flat resource structure — no child nodes.

### Region Structure

```xml
<region id="AnimationBank">
  <node id="AnimationBank">
    <children>
      <node id="Resource"> ... </node>
    </children>
  </node>
</region>
```

### File Locations

| Source | Path Pattern | Content |
|--------|-------------|---------|
| Shared | `Content/Assets/Characters/.../_merged.lsx` | Character animation clips |
| Shared | `Content/Assets/Buildings/.../_merged.lsx` | Object animations (doors, levers) |
| Shared | `Content/Assets/Items/.../_merged.lsx` | Item animations |

### Resource Attributes

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `ID` | FixedString | UUID primary key | `0633bd42-4d72-6581-e111-5e64f7fc55f8` |
| `Name` | LSString | Animation name (convention driven) | `BIRD_Eagle_Rig_CINE_Idle_01` |
| `SourceFile` | LSString | GR2 source path | `Public/Shared/Assets/.../_Construction/....GR2` |
| `Template` | FixedString | Animation template ref | `Public/Shared/Assets/.../_Construction/....Anim.0` |
| `SkeletonResource` | FixedString | UUID → SkeletonBank | `9b42fe29-1ad4-bf0c-4149-054d7f4eadde` |
| `PreviewVisualResource` | FixedString | UUID → VisualBank (editor preview) | `2ec332b3-5f3a-f7d9-0b80-4d6b6aad380a` |
| `Duration` | float | Clip duration in seconds | `16.666668` |
| `TimeStep` | float | Time step per frame | `0.005555556` |
| `Looping` | bool | Whether animation loops | `False` |
| `IsPoseBank` | bool | Is this a pose (static frame) | `False` |
| `Offset` | float | Start offset | `0` |
| `SupportingLeg` | uint8 | Which leg supports (IK hint) | `0` |
| `AnchorHand` | uint8 | Which hand anchors (weapon hand) | `0` |
| `LeftTransitionAnimation` | FixedString | UUID → AnimationBank (left transition) | _(empty)_ |
| `RightTransitionAnimation` | FixedString | UUID → AnimationBank (right transition) | _(empty)_ |
| `AdditiveLoopingAnimationID` | FixedString | _(optional)_ Additive loop overlay | _(empty)_ |
| `AdditiveLoopingBlendTime` | float | _(optional)_ Additive blend time | `0` |
| `AdditiveLoopingStart` | float | _(optional)_ Additive start time | `0` |
| `Localized` | bool | _(optional)_ Localization flag | `False` |
| `_OriginalFileVersion_` | int64 | Engine version stamp | `144115205255725257` |

### Cross-References

| From | To | Via |
|------|----|-----|
| AnimationBank.ID | AnimationSetBank.Animation.Object.ID | Animation set member |
| AnimationBank.ID | VisualBank.AnimationWaterfall.Object | Visual animation waterfall |
| AnimationBank.SkeletonResource | SkeletonBank.ID | Skeleton binding |
| AnimationBank.PreviewVisualResource | VisualBank.ID | Editor preview mesh |

### Naming Conventions

Animation names follow a hierarchical convention:
- `{CREATURE}_{RIG}_{CONTEXT}_{ACTION}_{VARIANT}`
- **Creature**: `BIRD`, `HUM`, `DWR`, `MFL`, `GNO`, etc.
- **Context**: `CINE` (cinematic), `GP` (gameplay), `CC` (character creation)
- **Action**: `Idle`, `Walk`, `Run`, `Attack`, `Cast`, `Death`, etc.

---

## AnimationBlueprintBank

> Defines animation state machine blueprints — the logic that controls animation transitions.
> Each blueprint references a compiled `.lsabp` file.

### Region Structure

```xml
<region id="AnimationBlueprintBank">
  <node id="AnimationBlueprintBank">
    <children>
      <node id="Resource"> ... </node>
    </children>
  </node>
</region>
```

### Node Hierarchy

```
AnimationBlueprintBank (region + root node)
└── Resource
    └── Params    ← empty node (parameters defined in source file)
```

### Resource Attributes

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `ID` | FixedString | UUID primary key | `679facd7-ed88-06f4-0782-11a95a5daf96` |
| `Name` | LSString | Blueprint name | `BOOK_Wizards_Tome_Notebook_Cinematic_A_Base` |
| `SourceFile` | LSString | LSABP source file | `Editor/Mods/Shared/Assets/Blueprints/Objects_Common.lsabp` |
| `PreviewVisualResourceID` | guid | Editor preview visual UUID | `00000000-0000-0000-0000-000000000000` |
| `Localized` | bool | Localization flag | `False` |
| `_OriginalFileVersion_` | int64 | Engine version stamp | `144115188075855919` |

### Cross-References

| From | To | Via |
|------|----|-----|
| AnimationBlueprintBank.ID | VisualBank.BlueprintInstanceResourceID | Visual animation blueprint |
| AnimationBlueprintBank.PreviewVisualResourceID | VisualBank.ID | Editor preview |

### Notes

- 140 instances in Shared — used for complex animation state machines (combat, interactions, cinematics)
- The `Params` child node is always empty in the data — actual parameters are compiled into the `.lsabp` file
- `PreviewVisualResourceID` is often null UUID (`00000000-...`)

---

## AnimationSetBank

> Groups multiple animations into named sets with subset categorization.
> Referenced by `VisualBank.AnimationWaterfall` — controls which animations are available to a visual.

### Region Structure

```xml
<region id="AnimationSetBank">
  <node id="AnimationSetBank">
    <children>
      <node id="Resource"> ... </node>
    </children>
  </node>
</region>
```

### Node Hierarchy

```
AnimationSetBank (region + root node)
└── Resource
    └── AnimationSet
        └── AnimationBank                     ← not a bank reference — a map container
            ├── FallBackAnimation              (guid) ← fallback animation UUID
            ├── ShortNameSetId                 (guid) ← short name set reference
            └── AnimationSubSets
                └── Object                     ← repeated (map entries)
                    ├── FallBackSubSet         (FixedString) ← fallback subset
                    ├── MapKey                 (FixedString) ← subset key
                    └── Animation
                        └── Object             ← repeated (animation map entries)
                            ├── ID             (FixedString) ← UUID → AnimationBank
                            └── MapKey         (FixedString) ← animation key UUID
```

### Resource Attributes

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `ID` | FixedString | UUID primary key | `5222629b-e173-3988-b8ac-78168977d2a4` |
| `Name` | LSString | Animation set name | `AUTOMN_M_CINE_Base` |
| `SourceFile` | LSString | Source file path | _(empty)_ |
| `PreviewVisualResourceID` | guid | Editor preview visual | `00000000-0000-0000-0000-000000000000` |
| `Localized` | bool | Localization flag | `False` |
| `_OriginalFileVersion_` | int64 | Engine version stamp | `144115198813274412` |

### AnimationBank (Container) Attributes

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `FallBackAnimation` | guid | Fallback animation UUID | `00000000-0000-0000-0000-000000000000` |
| `ShortNameSetId` | guid | Short name set reference | `00000000-0000-0000-0000-000000000000` |

### AnimationSubSets → Object Attributes

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `MapKey` | FixedString | Subset identifier key | _(empty or UUID)_ |
| `FallBackSubSet` | FixedString | Fallback subset key | _(empty)_ |

### Animation → Object Attributes

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `MapKey` | FixedString | Animation key UUID | `e3475a7e-ecfa-43c2-bcba-a0e2ea8e1dcb` |
| `ID` | FixedString | UUID → AnimationBank resource | `1b7c20b4-a3d5-bfca-de4a-375c3333cbd7` |

### Cross-References

| From | To | Via |
|------|----|-----|
| AnimationSetBank.ID | VisualBank.AnimationWaterfall.Object | Visual animation set |
| AnimationSetBank.Animation.ID | AnimationBank.ID | Individual animation clip |

### Notes

- 120 instances in Shared — animation sets bundle related clips (all idle variants, all attack variants, etc.)
- The deeply nested `AnimationBank` node inside `AnimationSet` is a **map container**, not a reference to the AnimationBank region
- `MapKey` fields are UUIDs that serve as animation slot identifiers (e.g., what animation plays for a specific situation)

---

## SkeletonBank

> Defines skeleton/rig resources — bone hierarchies that animations are applied to.
> Referenced by `VisualBank.SkeletonResource` and `AnimationBank.SkeletonResource`.

### Region Structure

```xml
<region id="SkeletonBank">
  <node id="SkeletonBank">
    <children>
      <node id="Resource"> ... </node>
    </children>
  </node>
</region>
```

### Node Hierarchy

```
SkeletonBank (region + root node)
└── Resource
    └── Bones                              ← repeated map entries (optional)
        ├── MapKey (FixedString)           ← bone name
        └── MapValue
            ├── SoundObjectActivationRange (float)
            └── SoundObjectIndex           (uint8)
```

### Resource Attributes

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `ID` | FixedString | UUID primary key | `8484b732-8a7d-6678-5384-84b33f48f279` |
| `Name` | LSString | Skeleton name | `BLD_Village_House_Door_A_Wood_Scenery_B_Explode_Base` |
| `SourceFile` | LSString | GR2 source path | `Public/Shared/Assets/Buildings/.../....GR2` |
| `Template` | FixedString | Skeleton template ref | `Public/Shared/Assets/Buildings/.../....Dummy_Root.0` |
| `PreviewAnimationResource` | FixedString | UUID → AnimationBank (editor preview) | _(empty)_ |
| `PreviewVisualResource` | FixedString | UUID → VisualBank (editor preview) | _(empty)_ |
| `ClothColliderResourceID` | FixedString | _(optional)_ UUID → ClothColliderBank | _(empty or UUID)_ |
| `DynamicPhysicsResourceID` | FixedString | Dynamic physics ref | `1ed36695-03da-85ef-dcd0-b06a018584e5` |
| `IKRigResourceID` | FixedString | UUID → IKRigBank | `00000000-0000-0000-0000-000000000000` |
| `RagdollResourceID` | FixedString | Ragdoll physics ref | `00000000-...` |
| `SoftbodyResourceID` | FixedString | Softbody physics ref | `00000000-...` |
| `SpringResourceID` | FixedString | Spring physics ref | `00000000-...` |
| `Localized` | bool | Localization flag | `False` |
| `_OriginalFileVersion_` | int64 | Engine version stamp | `144115188075855902` |

### Child: Bones (Map Structure)

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `MapKey` | FixedString | Bone name | `Dummy_R_HandFX` |
| `MapValue.SoundObjectActivationRange` | float | Sound trigger radius | `40` |
| `MapValue.SoundObjectIndex` | uint8 | Sound object index | `1`, `2`, `3` |

### Cross-References

| From | To | Via |
|------|----|-----|
| SkeletonBank.ID | VisualBank.SkeletonResource | Visual skeleton |
| SkeletonBank.ID | AnimationBank.SkeletonResource | Animation skeleton target |
| SkeletonBank.ClothColliderResourceID | ClothColliderBank.ID | Cloth collision |
| SkeletonBank.IKRigResourceID | IKRigBank.ID | IK rig |

### Notes

- **Most common bank type** — 243 instances in Shared (every animated object needs a skeleton)
- `Bones` children are optional — only present when bones have sound object associations
- Many physics reference fields accept null UUIDs (`00000000-...`) when not used

---

## IKRigBank

> Defines inverse kinematics rig configurations — controls how bone chains solve
> (e.g., foot placement on terrain, hand reaching for objects).

### Region Structure

```xml
<region id="IKRigBank">
  <node id="IKRigBank">
    <children>
      <node id="Resource"> ... </node>
    </children>
  </node>
</region>
```

### Node Hierarchy

```
IKRigBank (region + root node)
└── Resource
    ├── BoneCategories            ← empty node
    └── BoneProperties            ← repeated map entries (per bone)
        ├── MapKey (FixedString)  ← bone name
        └── MapValue
            └── IKBone
                ├── DoF           (int64) ← degrees of freedom bitmask
                ├── Enabled       (bool)
                ├── Weight        (fvec3) ← per-axis weight
                └── Limits        ← repeated (per axis constraint)
                    ├── Axis      (uint8) ← axis index
                    ├── Enabled   (bool)
                    ├── Max       (fvec3) ← rotation max
                    └── Min       (fvec3) ← rotation min
```

### Resource Attributes

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `ID` | FixedString | UUID primary key | `3dd1bb68-7f06-c7bc-0521-b3be9b4eb90b` |
| `Name` | LSString | IK rig name | `Animals_Heads_IKRig` |
| `SourceFile` | LSString | Source file path | _(empty)_ |
| `Localized` | bool | Localization flag | `False` |
| `_OriginalFileVersion_` | int64 | Engine version stamp | `144115198813274313` |

### BoneProperties → IKBone Attributes

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `DoF` | int64 | Degrees of freedom bitmask (7 = all axes) | `7` |
| `Enabled` | bool | IK solving enabled for this bone | `True`, `False` |
| `Weight` | fvec3 | Per-axis IK weight | `1 1 1` |

### BoneProperties → IKBone → Limits Attributes

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `Axis` | uint8 | Rotation axis (0/1/2 = X/Y/Z) | `0` |
| `Enabled` | bool | Limit enabled | `True` |
| `Max` | fvec3 | Maximum rotation | `20 20 20` |
| `Min` | fvec3 | Minimum rotation | `-20 -20 -20` |

### Cross-References

| From | To | Via |
|------|----|-----|
| IKRigBank.ID | SkeletonBank.IKRigResourceID | Skeleton IK rig |

### Notes

- Only 1 instance in Shared — IK rigs are shared across many skeletons
- `BoneCategories` child node is always empty in data
- `DoF` value of 7 (binary 111) enables all three rotation axes

---

## ClothColliderBank

> Defines cloth simulation collision shapes — sphere + capsule primitives attached to skeleton bones
> that cloth physics will collide against.

### Region Structure

```xml
<region id="ClothColliderBank">
  <node id="ClothColliderBank">
    <children>
      <node id="Resource"> ... </node>
    </children>
  </node>
</region>
```

### Node Hierarchy

```
ClothColliderBank (region + root node)
└── Resource
    └── Spheres                       ← repeated (one per collision sphere)
        ├── AttachedName (FixedString) ← bone to attach to
        ├── Name         (FixedString) ← sphere name
        ├── Position     (fvec3)       ← offset from bone
        ├── Radius       (float)       ← collision radius
        └── Links                      ← optional (capsule connections)
            └── Link     (FixedString) ← target bone name
```

### Resource Attributes

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `ID` | FixedString | UUID primary key | `f29e4d2d-...` |
| `Name` | LSString | Collider set name | `MFL_M_NKD_Body_ClothCollider` |
| `SourceFile` | LSString | Source file path | _(empty)_ |
| `_OriginalFileVersion_` | int64 | Engine version stamp | `144115207403208706` |

### Child: Spheres

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `AttachedName` | FixedString | Skeleton bone name | `Toes_L`, `Chest_M`, `Hip_R` |
| `Name` | FixedString | Sphere identifier (matches bone) | `Toes_L` |
| `Position` | fvec3 | Offset from bone origin | `-0.10327445 -1.937151E-07 -4.7683716E-07` |
| `Radius` | float | Collision sphere radius | `0.1`, `0.25` |

### Spheres → Links (Optional)

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `Link` | FixedString | Target bone name (forms capsule) | `Ankle_L`, `Root_M` |

### Cross-References

| From | To | Via |
|------|----|-----|
| ClothColliderBank.ID | SkeletonBank.ClothColliderResourceID | Skeleton cloth collision |
| ClothColliderBank.ID | VisualBank.ClothColliderResourceID | Visual cloth collision |

### Notes

- 10 instances in Shared — primarily for humanoid characters (cloaks, robes, hair)
- **Spheres alone** define simple sphere colliders; **Spheres + Links** define capsule colliders (two linked spheres form a capsule)
- Leaf bones (shoulders, spine, root) may have no Links — they act as simple sphere colliders

---

## BlendSpaceBank

> Defines 2D blend spaces for animation interpolation — maps parameter values to animation positions
> for smooth blending (e.g., speed → walk/run blend, angle → directional movement).

### Region Structure

```xml
<region id="BlendSpaceBank">
  <node id="BlendSpaceBank">
    <children>
      <node id="Resource"> ... </node>
    </children>
  </node>
</region>
```

### Node Hierarchy

```
BlendSpaceBank (region + root node)
└── Resource
    └── Inputs                      ← repeated (blend space sample points)
        ├── AnimationID (FixedString) ← UUID → AnimationBank
        ├── Position    (fvec2)       ← 2D position in blend space
        └── ShortNameID (FixedString) ← animation short name UUID
```

### Resource Attributes

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `ID` | FixedString | UUID primary key | `09fa116f-66b3-03a2-4e89-00bf733e658b` |
| `Name` | LSString | Blend space name | `Trav_EndDown` |
| `XAxisName` | LSString | X axis label | `Ladder Climbing Angle` |
| `YAxisName` | LSString | Y axis label | `N/a` |
| `MinXValue` | float | X axis minimum | `0` |
| `MaxXValue` | float | X axis maximum | `25` |
| `MinYValue` | float | Y axis minimum | `0` |
| `MaxYValue` | float | Y axis maximum | `1` |
| `XElements` | int32 | Grid elements on X axis | `2` |
| `YElements` | int32 | Grid elements on Y axis | `2` |
| `Localized` | bool | _(optional)_ Localization flag | `False` |
| `_OriginalFileVersion_` | int64 | Engine version stamp | `144115188075855891` |

### Child: Inputs

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `AnimationID` | FixedString | UUID → AnimationBank (or empty) | `6d20e2d6-ac44-8675-89fb-01494561baf3` |
| `Position` | fvec2 | Position in X/Y blend space | `25 0`, `0 0` |
| `ShortNameID` | FixedString | Animation short name reference | `9aa73082-b0ce-4243-b893-4598f15ea717` |

### Cross-References

| From | To | Via |
|------|----|-----|
| BlendSpaceBank.Inputs.AnimationID | AnimationBank.ID | Blend space animation source |

### Notes

- Only 3 instances in Shared — used for traversal animations (ladder climbing, etc.)
- Blend spaces interpolate between animation clips based on runtime parameter values

---

## FCurveBank

> Defines animation function curves — keyframe curves used for procedural animation
> (root motion, camera shake, etc.).

### Region Structure

```xml
<region id="FCurveBank">
  <node id="FCurveBank">
    <children>
      <node id="Resource"> ... </node>
    </children>
  </node>
</region>
```

### Node Hierarchy

```
FCurveBank (region + root node)
└── Resource
    ├── CurveKeys                  ← repeated (keyframe entries)
    │   ├── CurveKeyConstraintType     (int32)
    │   ├── CurveKeyInterpolationType  (int32)
    │   ├── CurveKeyLeftTangent        (float)
    │   ├── CurveKeyPosition           (fvec2) ← (time, value)
    │   └── CurveKeyRightTangent       (float)
    └── CurveLimits                ← single child (axis bounds)
        ├── MaxX (float)
        ├── MaxY (float)
        ├── MinX (float)
        └── MinY (float)
```

### Resource Attributes

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `ID` | FixedString | UUID primary key | `0f165107-d5d5-67ab-a35a-46b90b50dd73` |
| `Name` | LSString | Curve name | `DODGE_RootMovementYAxisCurve` |
| `Localized` | bool | Localization flag | `False` |
| `_OriginalFileVersion_` | int64 | Engine version stamp | `144115188075855891` |

### Child: CurveKeys

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `CurveKeyPosition` | fvec2 | (time, value) keyframe | `0 -0.05081273` |
| `CurveKeyInterpolationType` | int32 | Interpolation (0=step, 1=linear, 2=cubic) | `2` |
| `CurveKeyConstraintType` | int32 | Tangent constraint type | `0`, `2` |
| `CurveKeyLeftTangent` | float | Left (in) tangent | `2.4170623` |
| `CurveKeyRightTangent` | float | Right (out) tangent | `-0.7245303` |

### Child: CurveLimits

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `MinX` | float | Minimum time | `0` |
| `MaxX` | float | Maximum time | `0` |
| `MinY` | float | Minimum value | `0` |
| `MaxY` | float | Maximum value | `0` |

### Notes

- 8 instances in Shared — primarily for combat root motion curves (dodge, knockback)
- `CurveKeyPosition.x` = time, `CurveKeyPosition.y` = value
- Interpolation types: 0 = step (hold), 1 = linear, 2 = cubic (hermite/bezier)
