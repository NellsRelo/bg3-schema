# Region: `PassivesVFX`

> **Folder**: `VFX/`
> **Primary Node**: [Passives](Passives.md)
>
> Cast/prepare VFX

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
<region id="PassivesVFX">
  <node id="root">
    <children>
      <node id="Passives"> ... </node>
    </children>
  </node>
</region>
```

## Node Types

| Node | File | Description |
|------|------|-------------|
| Passives | [Passives.md](Passives.md) | Primary node type |

## Cross-Region References

*(To be documented)*

## Caveats

- **Folder != Region**: This region lives in `VFX/` not `PassivesVFX/`
