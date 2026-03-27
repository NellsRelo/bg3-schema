# Region: `GameplayVFXs`

> **Folder**: `VFX/`
> **Primary Node**: [VFX](VFX.md)
>
> 50+ gameplay effects

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
<region id="GameplayVFXs">
  <node id="root">
    <children>
      <node id="VFX"> ... </node>
    </children>
  </node>
</region>
```

## Node Types

| Node | File | Description |
|------|------|-------------|
| VFX | [VFX.md](VFX.md) | Primary node type |

## Cross-Region References

*(To be documented)*

## Caveats

- **Folder != Region**: This region lives in `VFX/` not `GameplayVFXs/`
