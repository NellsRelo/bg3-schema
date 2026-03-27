# Node: `Ruleset`

> **Region**: [Rulesets](_REGION.md)
> **Folder**: `Ruleset/`
> **Vanilla entries**: 7 (Shared)

---

## Attributes

| Attribute | Type | Frequency | Examples | Notes |
|-----------|------|-----------|----------|-------|
| `UUID` | guid | 7/7 | `993bc2a5-...` | Primary key |
| `Name` | LSString | 7/7 | `DIFFICULTY_EASY`, `DIFFICULTY_MEDIUM`, `DIFFICULTY_HARD` | Internal difficulty name |
| `Type` | uint8 | 7/7 | `1` | Ruleset type (all vanilla use `1`) |
| `DisplayName` | TranslatedString | 6/7 | handle `hdf7b...` | Shown in UI |
| `Description` | TranslatedString | 6/7 | handle `h3665...` | UI tooltip |
| `ShowInCustom` | bool | 5/7 | `true` | Whether shown in custom difficulty picker |

## Child Nodes

*(None in vanilla data)*

## Patterns of Use

- Defines the difficulty presets (Explorer, Balanced, Tactician, etc.).
- Referenced by `RulesetValues` to assign modifier values per difficulty.

## Cross-References

| From | To | Via |
|------|----|-----|
| RulesetValues | Ruleset | `Ruleset` |
| RulesetSelectionPresets | Ruleset | `Rulesets` child |

## Caveats & Gotchas

- One entry lacks DisplayName/Description (likely the base/internal ruleset).

## Similarities to Other Nodes

- Part of the Ruleset family: Rulesets, RulesetValues, RulesetModifiers, RulesetModifierOptions, RulesetSelectionPresets.
