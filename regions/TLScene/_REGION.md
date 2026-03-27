# Region: `TLScene`

> **Folder**: `Timeline/`
> **Primary Node**: [TLScene](TLScene.md)
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
<region id="TLScene">
  <node id="root">
    <children>
      <node id="TLScene"> ... </node>
    </children>
  </node>
</region>
```

## Node Types

| Node | File | Description |
|------|------|-------------|
| TLScene | [TLScene.md](TLScene.md) | Primary node type |

## Cross-Region References

*(To be documented)*

## Caveats

- **Folder != Region**: This region lives in `Timeline/` not `TLScene/`
