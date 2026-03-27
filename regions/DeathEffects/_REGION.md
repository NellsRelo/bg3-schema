# Region: `DeathEffects`

> **Folder**: `VFX/`
> **Primary Node**: [DeathEffect](DeathEffect.md)
>
> Per-damage-type death VFX

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
<region id="DeathEffects">
  <node id="root">
    <children>
      <node id="DeathEffect"> ... </node>
    </children>
  </node>
</region>
```

## Node Types

| Node | File | Description |
|------|------|-------------|
| DeathEffect | [DeathEffect.md](DeathEffect.md) | Primary node type |

## Cross-Region References

*(To be documented)*

## Caveats

- **Folder != Region**: This region lives in `VFX/` not `DeathEffects/`
