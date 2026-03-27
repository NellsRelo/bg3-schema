# Node: `ItemThrowParams`

> **Region**: [ItemThrowParams](_REGION.md)
> **Folder**: `ItemThrowParams/`
> **Vanilla entries**: 8 (Shared)

---

## Attributes

| Attribute | Type | Frequency | Examples | Notes |
|-----------|------|-----------|----------|-------|
| `UUID` | guid | 8/8 | `07a075f8-...` | Primary key |
| `Conditions` | LSString | 8/8 | `Item() and Tagged('WPN_DAGGER')` | Condition expression matching items |
| `Priority` | int32 | 8/8 | `1`, `2`, `3` | Higher = checked first |
| `RotationAxis` | FixedString | 8/8 | `YAxisNegative`, `None` | Axis of spin during throw |
| `MaxDistForZeroRotations` | int32 | 7/8 | `1`, `2` | Max distance for no-spin throw |
| `MaxDistForOneRotation` | int32 | 7/8 | `3`, `10`, `15` | Max distance for one-spin throw |
| `MaxDistForTwoRotations` | int32 | 7/8 | `9`, `20`, `30` | Max distance for two-spin throw |
| `StartAngleY` | int32 | 3/8 | `0` | Initial Y rotation angle |
| `StartAngleZ` | int32 | 3/8 | `90` | Initial Z rotation angle |

## Child Nodes

*(None in vanilla data)*

## Patterns of Use

- Conditions use Tag-based matching: `Tagged('WPN_DAGGER')`, `Tagged('ARROW')`, etc.
- Items are categorized by weapon type (daggers, medium weapons, polearms, etc.).
- Rotation parameters control how items visually spin when thrown.

## Cross-References

| From | To | Via |
|------|----|-----|
| ItemThrowParams | Tags | `Conditions` string references tag names |

## Caveats & Gotchas

- `Conditions` use XML-escaped apostrophes (`&apos;`) in the LSX files.
- Not all entries have rotation distance params (1 of 8 lacks them).

## Similarities to Other Nodes

*(None)*
