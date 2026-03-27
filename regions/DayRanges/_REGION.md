# Region: `DayRanges`

> **Folder**: `Calendar/`
> **Primary Node**: [DayRange](DayRange.md)
>
> Forgotten Realms calendar

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
<region id="DayRanges">
  <node id="root">
    <children>
      <node id="DayRange"> ... </node>
    </children>
  </node>
</region>
```

## Node Types

| Node | File | Description |
|------|------|-------------|
| DayRange | [DayRange.md](DayRange.md) | Primary node type |

## Cross-Region References

*(To be documented)*

## Caveats

- **Folder != Region**: This region lives in `Calendar/` not `DayRanges/`
