# Node: `Resource`

> **Region**: [TileSetBank](_REGION.md)
> **Child Depth**: 3 (Resource → TileSet → Tile)

---

## Node Hierarchy

```
Resource
└── TileSet                        ← single child
    ├── IsRoof (bool)              ← roof flag
    └── Tile                       ← repeated (individual tiles)
        ├── TileGUID               (guid) ← tile identifier
        ├── VisualGUID             (FixedString) ← UUID → VisualBank
        ├── PhysicsGUID            (FixedString) ← UUID → PhysicsBank
        └── InvisibleClimbingHelperPhysicsGUID (FixedString) ← climbing collision
```

## Attributes

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `ID` | FixedString | UUID primary key | `f7de2f7d-d19f-1c0a-40c5-3009c4d2efb5` |
| `Name` | LSString | Tile set name | `WALL_GEN_Rope_A` |
| `EditorSourceFile` | LSString | Editor source file (.set) | `Editor/Mods/Gustav/TileSet/WALL_GEN_Rope_A.set` |
| `Localized` | bool | Localization flag | `False` |
| `_OriginalFileVersion_` | int64 | Engine version stamp | `144115196665791066` |

## Child: TileSet

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `IsRoof` | bool | Whether this is a roof tile set | `False` |

## TileSet → Tile

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `TileGUID` | guid | Tile identifier UUID | `6cef9527-...` |
| `VisualGUID` | FixedString | UUID → [VisualBank](../VisualBank/_REGION.md) | `7f421a96-...` |
| `PhysicsGUID` | FixedString | UUID → [PhysicsBank](../PhysicsBank/_REGION.md) | `9eb00d29-...` |
| `InvisibleClimbingHelperPhysicsGUID` | FixedString | Climbing collision UUID | `00000000-...` |

## Cross-References

| From | To | Via |
|------|----|-----|
| Tile.VisualGUID | [VisualBank](../VisualBank/_REGION.md) | Tile visual mesh |
| Tile.PhysicsGUID | [PhysicsBank](../PhysicsBank/_REGION.md) | Tile physics collision |
