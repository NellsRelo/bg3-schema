# Node: `Resource`

> **Region**: [ScriptBank](_REGION.md)
> **Child Depth**: 2 (Resource → Parameters)

---

## Node Hierarchy

```
Resource
└── Parameters    ← empty node (parameters defined in script file)
```

## Attributes

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `ID` | FixedString | UUID primary key | `01d15b11-...` |
| `Name` | LSString | Script name | `DOS2_GEN_ItemSetMaterial` |
| `SourceFile` | LSString | Script source file | `Public/Shared/Scripts/GEN_ItemSetMaterial.itemScript` |
| `_OriginalFileVersion_` | int64 | Engine version stamp | `144537400540922156` |

## Child Nodes

### Parameters

Always empty — actual parameters are defined within the script file itself.
