# Node: `RulesetSelectionPreset`

> **Region**: [RulesetSelectionPresets](_REGION.md)
> **Folder**: `Ruleset/`
> **Vanilla entries**: 5 (Shared)

---

## Attributes

| Attribute | Type | Frequency | Examples | Notes |
|-----------|------|-----------|----------|-------|
| `UUID` | guid | 5/5 | `43bb2d5b-...` | Primary key |
| `Name` | LSString | 5/5 | `STORY`, `BALANCED`, `HARDCORE` | Internal preset name |
| `Asset` | LSString | 5/5 | `difficulty_01`, `difficulty_02`, `difficulty_03` | UI asset reference |
| `DisplayName` | TranslatedString | 5/5 | handle `h1952...` | UI display name |
| `Description` | TranslatedString | 5/5 | handle `h0391...` | UI description |
| `IsCustom` | bool | 1/5 | `true` | Marks the "Custom" preset |

## Child Nodes

| Child | Frequency | Notes |
|-------|-----------|-------|
| `Rulesets` | 5/5 | Contains child nodes referencing which Ruleset UUIDs are active |

## Patterns of Use

- Top-level difficulty presets shown in the new-game difficulty picker.
- Each preset contains a `Rulesets` child listing the active ruleset UUIDs.
- The `CUSTOM` preset has `IsCustom=true`.

## Cross-References

| From | To | Via |
|------|----|-----|
| RulesetSelectionPreset | Ruleset | `Rulesets` children |

## Caveats & Gotchas

- `IsCustom` only present on 1 of 5 entries.

## Similarities to Other Nodes

- Part of the Ruleset family.
