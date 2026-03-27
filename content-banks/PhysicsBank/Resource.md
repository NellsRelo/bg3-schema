# Node: `Resource`

> **Region**: [PhysicsBank](_REGION.md)
> **Child Depth**: 1 (flat — no child nodes)

---

## Attributes

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `ID` | FixedString | UUID primary key | `2da5bcca-587e-dd4f-5fc3-9276d840d36a` |
| `Name` | LSString | Physics asset name | `BLD_City_Road_Paving_Rubble_A` |
| `SourceFile` | LSString | Physics binary file (.bin) | `Public/Shared/Assets/Tilesets/City/.../.bin` |
| `Template` | FixedString | Template reference path | `Public/Shared/Assets/Tilesets/City/...` |
| `Localized` | bool | Localization flag | `False` |
| `_OriginalFileVersion_` | int64 | Engine version stamp | `144115196665791066` |

## Child Nodes

_(None — flat resource structure)_

## Cross-References

| From | To | Via |
|------|----|-----|
| Resource.ID | GameObjects | `PhysicsTemplate` |
| Resource.ID | [TileSetBank](../TileSetBank/_REGION.md) | `Tile.PhysicsGUID` |
