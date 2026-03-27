# Region: `TextureAtlasInfo`

> **Folder**: `GUI/`
> **Primary Node**: [TextureAtlasInfo](TextureAtlasInfo.md)
>
> Texture atlas metadata, shares files with IconUVList

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
<region id="TextureAtlasInfo">
  <node id="root">
    <children>
      <node id="TextureAtlasInfo"> ... </node>
    </children>
  </node>
</region>
```

## Node Types

| Node | File | Description |
|------|------|-------------|
| TextureAtlasInfo | [TextureAtlasInfo.md](TextureAtlasInfo.md) | Primary node type |

## Cross-Region References

*(To be documented)*

## Caveats

- **Folder != Region**: This region lives in `GUI/` not `TextureAtlasInfo/`
