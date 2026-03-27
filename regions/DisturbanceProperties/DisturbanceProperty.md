# Node: `DisturbanceProperty`

> **Region**: [DisturbanceProperties](_REGION.md)
> **Folder**: `Disturbances/`
> **Source**: `Shared/Public/Shared/Disturbances/DisturbanceProperties.lsx`
> **Total Nodes**: ~15 (Shared only)

---

## Attributes

| Attribute | Type | Frequency | Examples | Notes |
|-----------|------|-----------|----------|-------|
| `UUID` | guid | x15 | `db918cfb-a484-437c-93bb-8bc36fe98a9c` | Primary key |
| `Name` | FixedString | x15 | `BackgroundReaction`, `SecondaryCanJoinConfrontation`, `NoSceneManagerInterrupt` | Boolean-style flag name |

## Child Nodes

None.

## Patterns of Use

- Defines named boolean properties that control AI disturbance/alertness behaviors
- Names suggest behavior toggles: `BackgroundReaction`, `SecondaryCanJoinConfrontation`, `NoSceneManagerInterrupt`
- Likely referenced by templates or AI scripts to control NPC responses to disturbances

## Caveats & Gotchas

- Only 2 attributes per node — just UUID + Name; the boolean meaning is implied by context

## Similarities to Other Nodes

Simple name-only lookup table, similar to `EquipmentType` or `ActionResourceGroupDefinition`.
