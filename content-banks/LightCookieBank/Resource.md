# Node: `Resource`

> **Region**: [LightCookieBank](_REGION.md)
> **Child Depth**: 2 (Resource → Data ×128)

---

## Node Hierarchy

```
Resource
└── Data                     ← repeated ~128 times (coverage grid)
    └── Object (bool)
```

## Attributes

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `ID` | FixedString | UUID primary key | `766c5cbd-...` |
| `Name` | LSString | Cookie name | `Gobo_Bamboo_A` |
| `TextureName` | guid | UUID → [TextureBank](../TextureBank/_REGION.md) | `37870237-...` |
| `BrightnessThreshold` | int32 | Coverage threshold | `10` |
| `Localized` | bool | Localization flag | `False` |
| `_OriginalFileVersion_` | int64 | Engine version stamp | ... |

## Child: Data (Coverage Grid)

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `Object` | bool | Grid cell coverage (True = shadow) | `True` |

## Cross-References

| From | To | Via |
|------|----|-----|
| Resource.TextureName | [TextureBank](../TextureBank/_REGION.md) | Cookie texture source |
