# Region: `ActionResourceDefinitions`

> **Folder**: `ActionResourceDefinitions/`
> **Primary Node**: [ActionResourceDefinition](ActionResourceDefinition.md)
>
> Spell slots, rage charges, bardic inspiration, and all other action resources

---

## File Inventory

| Source | File | Entries | Version |
|--------|------|---------|---------|
| Shared | ActionResourceDefinitions.lsx | core D&D resources | — |
| SharedDev | ActionResourceDefinitions.lsx | extended resources | — |
| GustavDev | ActionResourceDefinitions.lsx | campaign resources | — |
| GustavX | ActionResourceDefinitions.lsx | EE subclass resources | — |

## Region Structure

```xml
<region id="ActionResourceDefinitions">
  <node id="root">
    <children>
      <node id="ActionResourceDefinition"> ... </node>
    </children>
  </node>
</region>
```

## Node Types

| Node | File | Description |
|------|------|-------------|
| ActionResourceDefinition | [ActionResourceDefinition.md](ActionResourceDefinition.md) | Resource: replenish rules, dice type, max values |

## Cross-Region References

| Target Region | Via | Purpose |
|---------------|-----|---------|
| [Progressions](../Progressions/_REGION.md) | `ActionResource(Name,Amount,Offset)` boost | Grant resources at level-up |
| [ActionResourceGroupDefinitions](../ActionResourceGroupDefinitions/_REGION.md) | Group membership | Spell slot grouping |

## Caveats

- **Four sources** contribute resources: Shared (core), SharedDev (extended), GustavDev (campaign), GustavX (EE subclasses).
- Referenced by name in Progression boosts, not by UUID.
