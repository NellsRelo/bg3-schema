# Region: `LevelMapValues`

> **Folder**: `Levelmaps/`
> **Primary Node**: [LevelMapSeries](LevelMapSeries.md)
>
> Cantrip/spell scaling

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
<region id="LevelMapValues">
  <node id="root">
    <children>
      <node id="LevelMapSeries"> ... </node>
    </children>
  </node>
</region>
```

## Node Types

| Node | File | Description |
|------|------|-------------|
| LevelMapSeries | [LevelMapSeries.md](LevelMapSeries.md) | Primary node type |

## Cross-Region References

*(To be documented)*

## Caveats

- **Folder != Region**: This region lives in `Levelmaps/` not `LevelMapValues/`
