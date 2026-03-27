# Node: `Resource`

> **Region**: [TimelineSceneBank](_REGION.md)
> **Child Depth**: 2 (Resource → Labels)

---

## Node Hierarchy

```
Resource
└── Labels                   ← repeated, optional (scene labels/tags)
    └── Object (FixedString)
```

## Attributes

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `ID` | FixedString | UUID primary key | `0059442a-...` |
| `Name` | LSString | Scene name | `_Add_EXT_NIGHT_Px1_Hyena` |
| `SourceFile` | string | Source file path | `Public/.../X.lsx` |
| `SceneType` | uint8 | Scene type (1=dialog, 2=cinematic, 4=ambient) | `1` |
| `AdditionalSpeakerCount` | int32 | Extra speakers beyond default (0-5) | `1` |
| `_OriginalFileVersion_` | int64 | Engine version stamp | `144115207403209026` |

## Child: Labels

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `Object` | FixedString | Scene label/tag | `EXT_NIGHT` |

## Caveats

- `SourceFile` uses type `string` (not `LSString`) — unusual among bank types
