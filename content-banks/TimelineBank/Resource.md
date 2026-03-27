# Node: `Resource`

> **Region**: [TimelineBank](_REGION.md)
> **Child Depth**: 2 (Resource → DependencyCache)

---

## Node Hierarchy

```
Resource
└── DependencyCache          ← repeated (resource dependencies)
    └── Object (guid)
```

## Attributes

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `ID` | FixedString | UUID primary key | `01d95486-...` |
| `Name` | LSString | Timeline name | `GEB_AD_Noticed_AttackedAnimal` |
| `SourceFile` | LSString | Compiled timeline file (.lsf) | `Public/Shared/Timeline/Generated/X.lsf` |
| `EditorSourceFile` | LSString | Editor source file (.tml) | `Editor/Mods/.../X.tml` |
| `DialogResourceId` | guid | UUID → [DialogBank](../DialogBank/_REGION.md) | `c62f94b6-...` |
| `IsGenerated` | bool | Whether automatically generated | `True` |
| `EditorTimelineType` | int32 | Timeline type (0=standard, 4/5=cinematic) | `0` |
| `BodyPartMocap` | int32 | Body part mocap flags (1=face, 3=body+face) | `3` |
| `FadeOutDuration` | float | _(optional)_ Fade-out time (-1 = no fade) | `0`, `-1` |
| `FadeOutOnEnd` | bool | _(optional)_ Fade to black on end | `False` |
| `Localized` | bool | _(optional)_ Localization flag | `False` |
| `_OriginalFileVersion_` | int64 | Engine version stamp | `144115207403209032` |

## Child: DependencyCache

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `Object` | guid | UUID of dependent resource | `c62f94b6-...` |

## Cross-References

| From | To | Via |
|------|----|-----|
| Resource.ID | [TimelineSceneBank](../TimelineSceneBank/_REGION.md) | Scene composition |
| Resource.DialogResourceId | [DialogBank](../DialogBank/_REGION.md) | Dialog link |
