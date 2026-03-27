# Region: `FactionManager`

> **Folder**: `Factions/`
> **Primary Node**: [Relation](Relation.md)
>
> Directional source-target relations

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
<region id="FactionManager">
  <node id="root">
    <children>
      <node id="Relation"> ... </node>
    </children>
  </node>
</region>
```

## Node Types

| Node | File | Description |
|------|------|-------------|
| Relation | [Relation.md](Relation.md) | Primary node type |

## Cross-Region References

*(To be documented)*

## Caveats

- **Folder != Region**: This region lives in `Factions/` not `FactionManager/`
