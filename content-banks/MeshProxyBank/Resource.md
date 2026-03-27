# Node: `Resource`

> **Region**: [MeshProxyBank](_REGION.md)
> **Child Depth**: 1 (flat — no child nodes)

---

## Attributes

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `ID` | FixedString | UUID primary key | `125d8105-...` |
| `Name` | LSString | Proxy mesh name | `VFX_Proxy_CRA_Crash_Shockwave_Trees_01` |
| `SourceFile` | LSString | GR2 source file | `Public/Shared/Assets/.../file.GR2` |
| `Template` | FixedString | Template mesh reference | `Public/Shared/Assets/.../file.MeshName.0` |
| `Localized` | bool | _(optional)_ Localization flag | `False` |
| `_OriginalFileVersion_` | int64 | Engine version stamp | ... |

## Child Nodes

_(None — flat resource structure)_
