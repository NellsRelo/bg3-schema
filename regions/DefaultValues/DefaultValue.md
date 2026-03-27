# Node: `DefaultValue`

> **Region**: [DefaultValues](_REGION.md)
> **Folder**: `DefaultValues/`
> **Note**: Data is split across 7 files (Abilities, Equipments, Feats, Passives, PreparedSpells, Skills, Spells)

---

## Attributes

| Attribute | Type | Frequency | Examples | Notes |
|-----------|------|-----------|----------|-------|
| `UUID` | guid | always | — | Primary key |
| `TableUUID` | guid | always | progression table UUID | Links to which class/race progression table applies |
| `Add` | LSString | always | `Dexterity;Wisdom`, `Perception;Stealth` | Semicolon-delimited items to add |
| `Level` | int32 | always | `1` | Character level this default applies at |
| `SelectorId` | LSString | sometimes | `BardInstrument`, `SkilledSkills` | Matches a Progression Selector name |
| `RaceUUID` | guid | rare | links to Race.UUID | Race-specific defaults |

## File Organization

| File | Content | Example Count |
|------|---------|---------------|
| `Abilities.lsx` | Default ability score distributions | 2 entries |
| `Skills.lsx` | Default skill proficiency selections | 29 entries |
| `Equipments.lsx` | Default equipment selections | 1 entry |
| `Passives.lsx` | Default passive selections | varies |
| `Spells.lsx` | Default spell known selections | varies |
| `PreparedSpells.lsx` | Default prepared spell selections | varies |
| `Feats.lsx` | Default feat selections | varies |

## Cross-References

| From | To | Via |
|------|----|-----|
| DefaultValue.TableUUID | [Progression](../Progressions/Progression.md) | Progression.TableUUID |
| DefaultValue.RaceUUID | [Race](../Races/Race.md) | Race.UUID |
| DefaultValue.SelectorId | Progression.Selectors | Selector function name |

## Caveats & Gotchas

- Provides auto-fill defaults for level-up choices — what the engine picks if the player doesn't choose.
- `Add` is semicolon-delimited (consistent with Progression boost/passive format).
- `SelectorId` must match the selector name in the corresponding Progression entry.

## Cross-References

| From | To | Via |
|------|----|-----|
| — | — | — |

## Caveats & Gotchas

*(To be documented)*

## Similarities to Other Nodes

*(To be documented)*
