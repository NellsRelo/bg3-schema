# Node: `PassiveList`

> **Region**: [PassiveLists](_REGION.md)
> **Folder**: `Lists/`

---

## Attributes

| Attribute | Type | Frequency | Examples | Notes |
|-----------|------|-----------|----------|-------|
| `UUID` | guid | always | — | Primary key |
| `Name` | FixedString | always | `Fighter fighting style`, `Warlock invocations` | Descriptive list name |
| `Passives` | LSString | always | `FightingStyle_Archery,FightingStyle_Defense,...` | **Comma-delimited** passive identifiers |

## Cross-References

| From | To | Via |
|------|----|-----|
| PassiveList.UUID | [Progression](../Progressions/Progression.md) | Selector `SelectPassives(UUID,...)` / `ReplacePassives(UUID,...)` |
| Passive identifiers | Stats PassiveData | PassiveData entry names |

## Caveats & Gotchas

- **Delimiter: COMMAS** — Unlike SpellList which uses semicolons. **Critical inconsistency** — this is the #1 delimiter-related bug in modding. Always verify delimiter type per-region.
- 17 entries in Shared (vanilla).
- **Cross-format reference**: Passive identifiers are **name-based references** (case-sensitive) to `Passive.txt` entries in Stats. A misspelled passive name causes silent failure.
- **SelectPassives vs ReplacePassives** — When referenced by `SelectPassives(UUID, N)` in a [Progression](../Progressions/Progression.md), the player chooses N passives from the list. `ReplacePassives(UUID, N)` allows swapping previously chosen passives. The PassiveList itself is identical in both cases.
- **Passives from Stats TXT**: Each identifier resolves to a `PassiveData` entry in `Passive.txt` which defines the actual mechanics: `Boosts`, `Conditions`, `StatsFunctors`, `Properties` (`IsHidden`, `OncePerTurn`, etc.), and tooltip information.

## Similarities to Other Nodes

- [SpellList](../SpellLists/SpellList.md) — Same pattern (UUID + name-based list) but uses semicolons and references Spell entries.
- [SkillList](../SkillLists/SkillList.md) — Same pattern, comma-delimited, references skill names from ValueLists.
- [AbilityList](../AbilityLists/AbilityList.md) — Same pattern, comma-delimited, references ability names.
