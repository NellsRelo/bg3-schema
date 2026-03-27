# Region: `MetaConditions`

> **Folder**: `Spell/`
> **Primary Node**: [MetaCondition](MetaCondition.md)
>
> Spell condition overlays

---

## File Inventory

| Source | File | Entries | Version |
|--------|------|---------|---------|
| Shared | *.lsx | — | — |
| SharedDev | *.lsx | — | — |
| Gustav | *.lsx | — | — |
| GustavDev | *.lsx | — | — |
| GustavX | *.lsx | — | — |

## Region Structure

```xml
<region id="MetaConditions">
  <node id="root">
    <children>
      <node id="MetaCondition"> ... </node>
    </children>
  </node>
</region>
```

## Node Types

| Node | File | Description |
|------|------|-------------|
| MetaCondition | [MetaCondition.md](MetaCondition.md) | Primary node type |

## Cross-Region References

*(To be documented)*

## Caveats

- **Folder != Region**: This region lives in `Spell/` not `MetaConditions/`
