# Node: `SkillList`

> **Region**: [SkillLists](_REGION.md)
> **Folder**: `Lists/`

---

## Attributes

| Attribute | Type | Frequency | Examples | Notes |
|-----------|------|-----------|----------|-------|
| `UUID` | guid | always | — | Primary key |
| `Name` | FixedString | always | `All Skills`, `Barbarian Skill List` | Descriptive list name |
| `Skills` | LSString | always | `Acrobatics, AnimalHandling, Arcana, ...` | **Comma-delimited** skill identifiers |

## Cross-References

| From | To | Via |
|------|----|-----|
| SkillList.UUID | [Progression](../Progressions/Progression.md) | Selector `SelectSkills(UUID,...)` / `SelectSkillsExpertise(UUID,...)` |
| Skill names | ValueLists.txt | `Skills` references skill names defined in the engine's `ValueLists` |

## Caveats & Gotchas

- **Delimiter: COMMAS** (consistent with PassiveList, AbilityList).
- 13 entries in Shared.
- **SelectSkills vs SelectSkillsExpertise** — Both reference SkillList UUIDs, but `SelectSkillsExpertise` has an optional `LimitToProficiency` parameter that restricts choices to already-proficient skills.
- **Skill names from ValueLists** — Skill identifiers (e.g., `Acrobatics`, `AnimalHandling`, `Arcana`) are defined in `ValueLists.txt` and must match exactly.

## Similarities to Other Nodes

- [PassiveList](../PassiveLists/PassiveList.md) — Same pattern, comma-delimited, but references Passive.txt entries.
- [SpellList](../SpellLists/SpellList.md) — Same pattern but uses **semicolons** (critical inconsistency).
- [AbilityList](../AbilityLists/AbilityList.md) — Same pattern, comma-delimited.
