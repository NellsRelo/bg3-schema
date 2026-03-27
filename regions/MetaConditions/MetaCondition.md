# Node: `MetaCondition`

> **Region**: [MetaConditions](_REGION.md)
> **Folder**: `Spell/`
> **Vanilla entries**: 1 (Shared)

---

## Attributes

| Attribute | Type | Frequency | Examples | Notes |
|-----------|------|-----------|----------|-------|
| `UUID` | guid | 1/1 | `0814bcfc-...` | Primary key |
| `Name` | LSString | 1/1 | `IgnoreInvulnerable` | Condition name |
| `ConditionType` | FixedString | 1/1 | `Target` | What the condition applies to |
| `Filter` | LSString | 1/1 | `(HasFunctor(...) or ...) and AreaRadiusGreaterThan(0) and ...` | Spell filter expression |
| `AdditionalConditions` | LSString | 1/1 | `(not HasHPLessThan(1) and not ...) or HasAttribute(...)` | Extra conditions to inject |
| `OverrideOriginalCondition` | bool | 1/1 | `false` | Whether to replace or augment the original |

## Child Nodes

*(None in vanilla data)*

## Patterns of Use

- Only 1 vanilla entry: `IgnoreInvulnerable`.
- Used to inject conditions into matching spells (those with DealDamage/Status/Summon functors in AoE).
- Allows overriding or augmenting spell target conditions globally.

## Cross-References

| From | To | Via |
|------|----|-----|
| MetaCondition | Spells (stats) | `Filter` matches spell properties |

## Caveats & Gotchas

- `Filter` and `AdditionalConditions` are complex condition expression strings.
- Very sparse in vanilla (1 entry) but powerful for mods.

## Similarities to Other Nodes

*(None)*
