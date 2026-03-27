# Node: `AbilityList`

> **Region**: [AbilityLists](_REGION.md)
> **Folder**: `Lists/`

---

## Attributes

| Attribute | Type | Frequency | Examples | Notes |
|-----------|------|-----------|----------|-------|
| `UUID` | guid | always | — | Primary key |
| `Name` | FixedString | always | `Human List`, `Half Elf List` | Descriptive list name |
| `Abilities` | LSString | always | `Strength, Dexterity, Constitution, ...` | **Comma-delimited** ability identifiers |

## Cross-References

| From | To | Via |
|------|----|-----|
| AbilityList.UUID | [Progression](../Progressions/Progression.md) | Selector `SelectAbilities(UUID,...)` / `SelectAbilityBonus(UUID,...)` |
| Ability names | ValueLists.txt | `Abilities` references ability names: Strength, Dexterity, Constitution, Intelligence, Wisdom, Charisma |

## Caveats & Gotchas

- **Delimiter: COMMAS** (consistent with PassiveList/SkillList).
- 5 entries in Shared.
- **SelectAbilities vs SelectAbilityBonus** — Both reference AbilityList UUIDs but have different parameter semantics. `SelectAbilities` lets the player choose N abilities with a fixed bonus amount. `SelectAbilityBonus` is the ASI-style selector (e.g., +2/+1 split) with a `BonusType` and `Amounts` parameter controlling the distribution.
- **Amounts parameter** — In `SelectAbilityBonus`, the `Amounts` field is a comma-separated int list representing max bonus per selection (e.g., `1` means cap of +1 per ability per pick). Despite being defined as `Int[]`, vanilla only uses a single value.

## Similarities to Other Nodes

- [SkillList](../SkillLists/SkillList.md) — Same comma-delimited list pattern for a different value domain.
- [PassiveList](../PassiveLists/PassiveList.md) — Same pattern, references Stats entry names.
- [EquipmentList](../EquipmentLists/EquipmentList.md) — Same pattern but uses semicolons and references item Stats names.
