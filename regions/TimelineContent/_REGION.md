# Region: `TimelineContent`

> **Folder**: `Timeline/`
> **Primary Node**: [TimelineContent](TimelineContent.md)
>
> Multi-region per file

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
<region id="TimelineContent">
  <node id="root">
    <children>
      <node id="TimelineContent"> ... </node>
    </children>
  </node>
</region>
```

## Node Types

| Node | File | Description |
|------|------|-------------|
| TimelineContent | [TimelineContent.md](TimelineContent.md) | Primary node type |

## Cross-Region References

*(To be documented)*

## Caveats

- **Folder != Region**: This region lives in `Timeline/` not `TimelineContent/`
