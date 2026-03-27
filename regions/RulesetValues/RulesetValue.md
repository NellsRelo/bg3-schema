# Node: `RulesetValue`

> **Region**: [RulesetValues](_REGION.md)
> **Folder**: `Ruleset/`
> **Vanilla entries**: 39 (Shared)

---

## Attributes

| Attribute | Type | Frequency | Examples | Notes |
|-----------|------|-----------|----------|-------|
| `UUID` | guid | 39/39 | `a1873e6d-...` | Primary key |
| `Modifier` | guid | 39/39 | `968ce114-...` | References RulesetModifier UUID |
| `Ruleset` | guid | 39/39 | `993bc2a5-...` | References Ruleset UUID |
| `Value` | LSString | 39/39 | `AILETHALITY_FORGIVING`, `false`, `2` | The value for this modifier in this ruleset |

## Child Nodes

*(None in vanilla data)*

## Patterns of Use

- Junction table: assigns a specific `Value` to a `Modifier` within a `Ruleset`.
- Values are strings — can be enum names (`AILETHALITY_FORGIVING`), booleans (`false`), or numbers (`2`).

## Cross-References

| From | To | Via |
|------|----|-----|
| RulesetValue | Ruleset | `Ruleset` |
| RulesetValue | RulesetModifier | `Modifier` |

## Caveats & Gotchas

- `Value` is always `LSString` regardless of the actual data type — runtime parses it dynamically.

## Similarities to Other Nodes

- Part of the Ruleset family.
