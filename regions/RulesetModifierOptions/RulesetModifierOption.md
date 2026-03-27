# Node: `RulesetModifierOption`

> **Region**: [RulesetModifierOptions](_REGION.md)
> **Folder**: `Ruleset/`
> **Vanilla entries**: 18 (Shared)

---

## Attributes

| Attribute | Type | Frequency | Examples | Notes |
|-----------|------|-----------|----------|-------|
| `UUID` | guid | 18/18 | `6950af0d-...` | Primary key |
| `Modifier` | guid | 18/18 | `968ce114-...` | References RulesetModifier UUID |
| `Name` | LSString | 18/18 | `AILETHALITY_FORGIVING`, `AILETHALITY_BALANCED` | Option name/key |
| `Value` | LSString | 18/18 | `AILETHALITY_FORGIVING`, `AILETHALITY_BALANCED` | Value assigned when selected |
| `DisplayName` | TranslatedString | 18/18 | handle `h5b00...` | Shown in UI dropdown |
| `Description` | TranslatedString | 15/18 | handle `ha66b...` | Tooltip text |
| `ShowInCustom` | bool | 12/18 | `true` | Whether shown in custom difficulty |

## Child Nodes

*(None in vanilla data)*

## Patterns of Use

- Each option belongs to a `Modifier` and provides one selectable value.
- `Name` and `Value` are typically identical (the enum constant).

## Cross-References

| From | To | Via |
|------|----|-----|
| RulesetModifierOption | RulesetModifier | `Modifier` |

## Caveats & Gotchas

- Not all options have Description or ShowInCustom.

## Similarities to Other Nodes

- Part of the Ruleset family.
