# Region: `IconUVList`

> **Folder**: `GUI/`
> **Primary Node**: [IconUV](IconUV.md)
>
> Icon UV coordinates, shares files with TextureAtlasInfo

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
<region id="IconUVList">
  <node id="root">
    <children>
      <node id="IconUV"> ... </node>
    </children>
  </node>
</region>
```

## Node Types

| Node | File | Description |
|------|------|-------------|
| IconUV | [IconUV.md](IconUV.md) | Primary node type |

## Cross-Region References

*(To be documented)*

## Caveats

- **Folder != Region**: This region lives in `GUI/` not `IconUVList/`
