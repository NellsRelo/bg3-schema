# Region: `Crime`

> **Folder**: `Stats/`
> **Primary Node**: [Crime](Crime.md)
>
> Crime system config

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
<region id="Crime">
  <node id="root">
    <children>
      <node id="Crime"> ... </node>
    </children>
  </node>
</region>
```

## Node Types

| Node | File | Description |
|------|------|-------------|
| Crime | [Crime.md](Crime.md) | Primary node type |

## Cross-Region References

- **Tags** — `CrimeTags` attributes reference Tag UUIDs to scope crimes to regions or NPC types
- **Templates** — crime-relevant objects (containers, doors) have crime-related attributes (`CanBeLootedInCombat`, etc.)
- **Flags** — crime state (detected, witnessed, forgiven) is tracked via global flags
- **Gossips** — crime events can trigger companion gossip dialog through flag dependencies
- **Osiris** — `DB_CrimeEnabled`, `PROC_Crime_Start`, `CrimeIsRegistered` events drive the crime system at runtime

## Caveats

- **Folder != Region**: This region lives in `Stats/` not `Crime/`
- **Complex multi-node structure** — Crime entries often have deeply nested children (CrimeActions, CrimeConditions) that must be structurally correct or the crime config is silently ignored
