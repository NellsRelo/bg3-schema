# Node: `EquipmentList`

> **Region**: [EquipmentLists](_REGION.md)
> **Folder**: `Lists/`
> **Vanilla entries**: 1 (Shared; also present in GustavX)

---

## Attributes

| Attribute | Type | Frequency | Examples | Notes |
|-----------|------|-----------|----------|-------|
| `UUID` | guid | 1/1 | `aab8c5b5-...` | Primary key |
| `Name` | FixedString | 1/1 | `Bard instruments` | Human-readable list name |
| `Items` | LSString | 1/1 | `ARM_Instrument_Drum;ARM_Instrument_Flute;...` | Semicolon-separated item stat names |

## Child Nodes

*(None in vanilla data)*

## Patterns of Use

- Only 1 vanilla entry: "Bard instruments" containing 5 instrument items.
- `Items` is a semicolon-separated list of stat-entry names (not UUIDs).

## Cross-References

| From | To | Via |
|------|----|-----|
| EquipmentList | Items (stats) | `Items` semicolon-separated names |

## Caveats & Gotchas

- Very sparse in vanilla — only 1 entry. Mods may add more.
- **Items uses semicolons** — Same delimiter as [SpellList](../SpellLists/SpellList.md), unlike the comma-delimited PassiveList/SkillList/AbilityList.
- **Name-based references** — Item names in the `Items` field are case-sensitive references to Stats TXT entries (typically in `Armor.txt` or `Weapon.txt`).
- **Referenced by SelectEquipment selector** — `SelectEquipment(EquipmentListUUID, Amount, [SelectorId])` in [Progression](../Progressions/Progression.md) or [Feat](../Feats/Feat.md) selectors presents a picker for the player to choose equipment from this list.

## Similarities to Other Nodes

- [SpellList](../SpellLists/SpellList.md) — Similar semicolon-separated list format but for spells.
- [PassiveList](../PassiveLists/PassiveList.md), [SkillList](../SkillLists/SkillList.md), [AbilityList](../AbilityLists/AbilityList.md) — Same pattern but comma-delimited.
- All "List" regions serve as **grouping mechanisms** referenced by [Progression](../Progressions/Progression.md) Selectors.
