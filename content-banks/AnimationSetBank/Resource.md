# Node: `Resource`

> **Region**: [AnimationSetBank](_REGION.md)
> **Child Depth**: 4 (Resource → AnimationSet → AnimationBank → AnimationSubSets)

---

## Node Hierarchy

```
Resource
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

## Attributes

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `ID` | FixedString | UUID primary key | `5222629b-e173-3988-b8ac-78168977d2a4` |
| `Name` | LSString | Animation set name | `AUTOMN_M_CINE_Base` |
| `SourceFile` | LSString | Source file path | _(empty)_ |
| `PreviewVisualResourceID` | guid | Editor preview visual | `00000000-0000-0000-0000-000000000000` |
| `Localized` | bool | Localization flag | `False` |
| `_OriginalFileVersion_` | int64 | Engine version stamp | `144115198813274412` |

## Child: AnimationBank (Container)

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `FallBackAnimation` | guid | Fallback animation UUID | `00000000-0000-0000-0000-000000000000` |
| `ShortNameSetId` | guid | Short name set reference | `00000000-0000-0000-0000-000000000000` |

## AnimationSubSets → Object

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `MapKey` | FixedString | Subset identifier key | _(empty or UUID)_ |
| `FallBackSubSet` | FixedString | Fallback subset key | _(empty)_ |

## Animation → Object

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `MapKey` | FixedString | Animation key UUID | `e3475a7e-ecfa-43c2-bcba-a0e2ea8e1dcb` |
| `ID` | FixedString | UUID → [AnimationBank](../AnimationBank/_REGION.md) resource | `1b7c20b4-a3d5-bfca-de4a-375c3333cbd7` |

## Cross-References

| From | To | Via |
|------|----|-----|
| Resource.ID | [VisualBank](../VisualBank/_REGION.md) | `AnimationWaterfall.Object` |
| Animation.ID | [AnimationBank](../AnimationBank/_REGION.md) | Individual animation clip |
