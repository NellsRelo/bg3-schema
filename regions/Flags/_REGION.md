# Region: `Flags`

> **Folder**: `Flags/`
> **Primary Node**: [Flags](Flags.md)
>
> ~26K UUID-named files

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
<region id="Flags">
  <node id="root">
    <children>
      <node id="Flags"> ... </node>
    </children>
  </node>
</region>
```

## Node Types

| Node | File | Description |
|------|------|-------------|
| Flags | [Flags.md](Flags.md) | Primary node type |

## Cross-Region References

- **Gossips** — `ConditionFlags` and `ResultFlags` directly reference Flag UUIDs to gate and trigger gossip lines
- **Crime** — crime state (detected, forgiven, etc.) is tracked through global flags
- **Dialog** — dialog nodes use flag conditions extensively for branching
- **Osiris** — `SetFlag()`, `ClearFlag()`, `GetFlag()` are core scripting primitives; flags bridge data ↔ runtime
- **Templates** — flag-based conditions can appear in template scripting overrides

## Caveats

- **~26K files** — the largest region by file count; each flag is a separate UUID-named `.lsx` file. Bulk operations require tooling
- **Global state** — flags are global (not scoped to entities by default); naming conventions (e.g. `GLO_`, `YOURMOD_`) are the only namespacing mechanism
- **Silent reference breakage** — if a flag UUID is referenced by Gossips, Dialog, or Osiris but the flag file is missing, behavior silently degrades
- **Naming conventions matter** — prefixes like `GLO_`, `FOR_`, `TUT_`, `YOURMOD_` are critical for organization at scale
