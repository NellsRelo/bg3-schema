# Region: `DisturbanceProperties`

> **Folder**: `Disturbances/`
> **Primary Node**: [DisturbanceProperty](DisturbanceProperty.md)
>
> Folder != region - 15 flags

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
<region id="DisturbanceProperties">
  <node id="root">
    <children>
      <node id="DisturbanceProperty"> ... </node>
    </children>
  </node>
</region>
```

## Node Types

| Node | File | Description |
|------|------|-------------|
| DisturbanceProperty | [DisturbanceProperty.md](DisturbanceProperty.md) | Primary node type |

## Cross-Region References

*(To be documented)*

## Caveats

- **Folder != Region**: This region lives in `Disturbances/` not `DisturbanceProperties/`
