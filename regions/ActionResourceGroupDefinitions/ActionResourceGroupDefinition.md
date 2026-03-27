# Node: `ActionResourceGroupDefinition`

> **Region**: [ActionResourceGroupDefinitions](_REGION.md)
> **Folder**: `ActionResourceGroupDefinitions/`

---

## Attributes

> 1 node in Shared (vanilla)

| Attribute | Type | Count | Examples | Notes |
|-----------|------|-------|----------|-------|
| `UUID` | guid | 1/1 | `03b17647-161a-42e1-9660-5ba517e80ad2` | Primary key |
| `Name` | LSString | 1/1 | `SpellSlotsGroup` | Group name |
| `ActionResourceDefinitions` | LSString | 1/1 | semicolon-separated UUIDs | Member action resource UUIDs |

## Cross-References

| From | To | Via |
|------|----|-----|
| ActionResourceGroupDefinition.ActionResourceDefinitions | [ActionResourceDefinition](../ActionResourceDefinitions/ActionResourceDefinition.md) | UUID references (semicolon-delimited) |

## Caveats & Gotchas

- Only 1 vanilla group: `SpellSlotsGroup` — groups all spell slot resource tiers together.
- `ActionResourceDefinitions` contains semicolon-separated ActionResourceDefinition UUIDs.
- Mods can add new groups for custom resource systems.

## Cross-References

| From | To | Via |
|------|----|-----|
| — | — | — |

## Caveats & Gotchas

*(To be documented)*

## Similarities to Other Nodes

*(To be documented)*
