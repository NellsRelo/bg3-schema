# Node: `ShortName`

> **Region**: [ShortNames](_REGION.md)
> **Folder**: `Animation/`
> **Source**: `Shared/Public/Shared/Animation/ShortNames.lsx`
> **Total Nodes**: ~8,789 (Shared only)

---

## Attributes

| Attribute | Type | Frequency | Examples | Notes |
|-----------|------|-----------|----------|-------|
| `UUID` | guid | x8789 | `beeabe70-56cd-4cb4-aa83-4f032dcfe146` | Primary key |
| `Name` | FixedString | x8789 | `CC_EquipmentStyle_Icon_Still_01`, `CC_Portrait_Still_01` | Animation short name identifier |
| `CategoryGuid` | guid | x8789 | `bed504fb-634d-4821-a975-5f76902b4c51` | FK → `ShortNameCategory.UUID` |

## Child Nodes

None.

## Patterns of Use

- Massive lookup table mapping animation short names to categories
- 8,789 entries — one of the largest regions in the game
- `CategoryGuid` links each short name to a `ShortNameCategory` for organization
- Names cover character creation (`CC_*`), combat, idle, dialogue, and many other animation contexts

## Cross-References

| From | To | Via |
|------|----|-----|
| `ShortName.CategoryGuid` | `ShortNameCategory.UUID` | FK |

## Caveats & Gotchas

- Very large file — 8,789 nodes makes this one of the biggest LSX regions

## Similarities to Other Nodes

Paired with `ShortNameCategory` — categories define groups, short names are the individual entries.
