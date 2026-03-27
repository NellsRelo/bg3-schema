# Node: `Rule`

> **Region**: [Rulebook](_REGION.md)
> **Folder**: `Shapeshift/`
> **Source**: `Gustav/Public/Gustav/Shapeshift/Rulebook.lsx`, also GustavDev, GustavX
> **Total Nodes**: ~3 (Gustav; additional in other packs)

---

## Attributes

| Attribute | Type | Frequency | Examples | Notes |
|-----------|------|-----------|----------|-------|
| `UUID` | guid | x3 | `d7ff7994-4c80-40cf-9498-fc790e5cc9d1` | Primary key |
| `RuleName` | LSString | x3 | `DisguiseHag`, `DisguiseChestOfMundane`, `DisguiseHag_Mayrina` | Rule identifier name |
| `ApplyVisual` | bool | x3 | `true` | Apply visual changes |
| `ChangeBodyType` | bool | x3 | `true`, `false` | Override body type |
| `ChangeIcon` | bool | x3 | `true` | Change character icon |
| `ChangeRace` | bool | x3 | `false`, `true` | Override race |
| `IgnoreCustomLooks` | bool | x3 | `true` | Ignore player custom appearance |
| `RemoveOldTags` | bool | x3 | `false`, `true` | Remove pre-existing tags |
| `RetainDisplayName` | bool | x3 | `false` | Keep original display name |
| `ApplyTagsFromTemplate` | bool | x3 | `false`, `true` | Copy tags from template |
| `ApplySpellsFromTemplate` | bool | x1 | `true` | Copy spells from template (sparse) |
| `BaseACOverride` | bool | x2 | `true` | Override base AC calculation |
| `BlockLevelUp` | bool | x1 | `true` | Prevent level-up while shapeshifted |
| `ChangeAi` | bool | x1 | `true` | Change AI behavior |
| `DisableEquipmentSlots` | bool | x1 | `true` | Disable equipment slots |
| `FootstepsType` | bool | x1 | `true` | Override footstep sounds |
| `KillEntityAtZeroHP` | bool | x1 | `true` | Kill (not revert) at 0 HP |
| `MuteEquipmentSound` | bool | x1 | `true` | Silence equipment sounds |
| `PassivesInheritanceType` | FixedString | x2 | `ReplaceOriginal` | How passives transfer |
| `RemovePrevSpells` | bool | x1 | `true` | Remove original spells |
| `ResistancesInheritanceType` | FixedString | x1 | `ReplaceOriginal` | How resistances transfer |
| `UnarmedAbilityFromTemplate` | bool | x1 | `true` | Use template's unarmed ability |
| `UseShapeshiftIdentity` | bool | x2 | `true` | Use new identity |
| `WildShapeHotBar` | bool | x1 | `true` | Use Wild Shape hotbar layout |

## Child Nodes

| Child | Count | Description |
|-------|-------|-------------|
| `AbilityChanges` | x12 | Ability score modifications (4 per disguise rule) |
| `Hp` | x2 | HP override settings |
| `Scale` | x1 | Size scale override |
| `Weight` | x1 | Weight override |

## Patterns of Use

- Defines shapeshift/disguise rules — what changes when a character transforms
- Each rule is a bundle of boolean flags controlling which aspects of the character are overridden
- Most attributes are sparse — only enabled for rules that need that specific feature
- `DisguiseHag` is the most complex rule (all features enabled)
- `DisguiseChestOfMundane` is the simplest (just visual change for Chest of the Mundane item)

## Caveats & Gotchas

- Many boolean attributes are sparse — absent = default (likely false)
- This is the **Shapeshift** rulebook, not the Rulesets/difficulty system
- `Rulebook.lsx` in `Shapeshift/` folder — don’t confuse with `Rulesets/`

## Similarities to Other Nodes

None — unique shapeshift/disguise rule system.
