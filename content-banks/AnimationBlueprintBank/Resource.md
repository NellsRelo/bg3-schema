# Node: `Resource`

> **Region**: [AnimationBlueprintBank](_REGION.md)
> **Child Depth**: 2 (Resource → Params)

---

## Node Hierarchy

```
Resource
└── Params    ← empty node (parameters defined in source file)
```

## Attributes

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `ID` | FixedString | UUID primary key | `679facd7-ed88-06f4-0782-11a95a5daf96` |
| `Name` | LSString | Blueprint name | `BOOK_Wizards_Tome_Notebook_Cinematic_A_Base` |
| `SourceFile` | LSString | LSABP source file | `Editor/Mods/Shared/Assets/Blueprints/Objects_Common.lsabp` |
| `PreviewVisualResourceID` | guid | Editor preview visual UUID | `00000000-0000-0000-0000-000000000000` |
| `Localized` | bool | Localization flag | `False` |
| `_OriginalFileVersion_` | int64 | Engine version stamp | `144115188075855919` |

## Child Nodes

### Params

Always empty — actual parameters are compiled into the `.lsabp` file.

## Cross-References

| From | To | Via |
|------|----|-----|
| Resource.ID | [VisualBank](../VisualBank/_REGION.md) | `BlueprintInstanceResourceID` |
| Resource.PreviewVisualResourceID | [VisualBank](../VisualBank/_REGION.md) | Editor preview |
