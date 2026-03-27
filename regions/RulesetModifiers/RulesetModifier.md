# Node: `RulesetModifier`

> **Region**: [RulesetModifiers](_REGION.md)
> **Folder**: `Ruleset/`
> **Vanilla entries**: 26 (Shared)

---

## Attributes

| Attribute | Type | Frequency | Examples | Notes |
|-----------|------|-----------|----------|-------|
| `UUID` | guid | 26/26 | `338450d9-...` | Primary key |
| `Name` | LSString | 26/26 | `IRONMAN_MODE`, `AI_LETHALITY`, `CHARACTER_STATS_DIFFICULTY` | Internal modifier name |
| `Default` | LSString | 26/26 | `false`, `AILETHALITY_BALANCED`, `STATUS_MEDIUM` | Default value |
| `RulesetModifierType` | uint8 | 26/26 | `3`, `4` | Type of modifier (3=dropdown, 4=toggle?) |
| `DisplayName` | TranslatedString | 25/26 | handle `hc46a...` | Shown in settings UI |
| `Description` | TranslatedString | 25/26 | handle `h465d...` | Tooltip in settings UI |
| `ShowInCustom` | bool | 20/26 | `true` | Whether shown in custom difficulty |
| `Max` | float | 3/26 | `3`, `4` | Maximum slider value |
| `Min` | float | 3/26 | `-1`, `0.5`, `1` | Minimum slider value |
| `Step` | float | 3/26 | `0.1`, `0.5`, `1` | Slider increment |
| `EditableDuringGame` | bool | 2/26 | `false` | Whether changeable mid-game |
| `LoadModule` | LSString | 1/26 | `Honour` | Module to load when enabled |

## Child Nodes

*(None in vanilla data)*

## Patterns of Use

- Defines individual difficulty knobs (AI lethality, HP multipliers, camp costs, etc.).
- Slider modifiers use `Min`/`Max`/`Step`; discrete modifiers use `RulesetModifierOptions`.
- `LoadModule=Honour` triggers loading the Honour mode module.

## Cross-References

| From | To | Via |
|------|----|-----|
| RulesetModifierOptions | RulesetModifier | `Modifier` |
| RulesetValues | RulesetModifier | `Modifier` |

## Caveats & Gotchas

- `LoadModule` is extremely rare (1/26) but critical for Honour mode.

## Similarities to Other Nodes

- Part of the Ruleset family.
