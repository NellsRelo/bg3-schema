# Node: `Resource`

> **Region**: [SplineSetBank](_REGION.md)
> **Child Depth**: 3 (Resource → TileSet → Tile)

---

## Node Hierarchy

```
Resource
└── TileSet
    └── Tile                       ← repeated (individual tiles)
        ├── TileGUID               (guid)
        └── VisualGUID             (FixedString) ← UUID → VisualBank
```

## Attributes

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `ID` | FixedString | UUID primary key | ... |
| `Name` | LSString | Spline set name | `WALL_HB_GBN_FamiliarFort_Battlement_A` |
| `EditorSourceFile` | LSString | Editor source file (.set) | `Editor/Mods/Gustav/TileSet/...` |
| `Localized` | bool | Localization flag | `False` |
| `_OriginalFileVersion_` | int64 | Engine version stamp | ... |

## Child: TileSet

_(Container — no own attributes)_

## TileSet → Tile

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `TileGUID` | guid | Tile identifier UUID | `a8c19b26-...` |
| `VisualGUID` | FixedString | UUID → [VisualBank](../VisualBank/_REGION.md) | `f5b2e318-...` |

_(Note: Unlike TileSetBank, SplineSetBank tiles have **no** `PhysicsGUID` or `InvisibleClimbingHelperPhysicsGUID`)_

## Cross-References

| From | To | Via |
|------|----|-----|
| Tile.VisualGUID | [VisualBank](../VisualBank/_REGION.md) | Tile visual mesh |
