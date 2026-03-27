# Region: `FactionContainer`

> **Folder**: `Factions/`
> **Primary Node**: [Faction](Faction.md)
>
> Hierarchical tree via ParentGuid

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
<region id="FactionContainer">
  <node id="root">
    <children>
      <node id="Faction"> ... </node>
    </children>
  </node>
</region>
```

## Node Types

| Node | File | Description |
|------|------|-------------|
| Faction | [Faction.md](Faction.md) | Primary node type |

## Cross-Region References

*(To be documented)*

## Caveats

- **Folder != Region**: This region lives in `Factions/` not `FactionContainer/`
