# Node: `AnimationSetPriority`

> **Region**: [AnimationSetPriorities](_REGION.md)
> **Folder**: `AnimationOverrides/`
> **Source**: `Gustav/Public/Gustav/AnimationOverrides/AnimationSetPriorities.lsx`
> **Total Nodes**: ~1 (Gustav only)

---

## Attributes

| Attribute | Type | Frequency | Examples | Notes |
|-----------|------|-----------|----------|-------|
| `UUID` | guid | x1 | `b301afa2-e21e-47ea-84ec-eb9737afb82e` | Primary key |
| `Name` | LSString | x1 | `Companion` | Named priority set |
| `Priority` | int32 | x1 | `30` | Priority value for animation override |
| `ReferenceId` | guid | x1 | `c87c64cd-0164-4b1a-8406-a5795f7cb070` | Reference to another entity |

## Child Nodes

| Child | Count | Description |
|-------|-------|-------------|
| `AddidionalObjects` | x5 | Additional objects affected by this priority set (note: typo in vanilla data) |

## Patterns of Use

- Only 1 node in vanilla — defines animation set priority for companions
- `AddidionalObjects` child nodes (x5) list additional objects that share this animation priority
- **Note**: `AddidionalObjects` has a typo in vanilla data (should be "Additional")

## Caveats & Gotchas

- Only exists in Gustav pack
- Typo in child node name: `AddidionalObjects` (not `AdditionalObjects`)

## Similarities to Other Nodes

Related to the animation system (`ShortName`, `ShortNameCategory`, `WeaponAnimationSet`).
