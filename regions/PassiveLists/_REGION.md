# Region: `PassiveLists`

> **Folder**: `Lists/`
> **Primary Node**: [PassiveList](PassiveList.md)
>
> 18 passive lists (Shared). Delimiter: **commas**.

---

## File Inventory

| Source | File | Entries | Version |
|--------|------|---------|---------|
| Shared | PassiveLists.lsx | 18 | — |
| SharedDev | PassiveLists.lsx | varies | — |
| GustavX | PassiveLists.lsx | varies | — |

## Region Structure

```xml
<region id="PassiveLists">
  <node id="root">
    <children>
      <node id="PassiveList"> ... </node>
    </children>
  </node>
</region>
```

## Node Types

| Node | File | Description |
|------|------|-------------|
| PassiveList | [PassiveList.md](PassiveList.md) | List of passive identifiers (comma-delimited) |

## Cross-Region References

| Target Region | Via | Purpose |
|---------------|-----|---------|
| [Progressions](../Progressions/_REGION.md) | `PassiveList.UUID` ← `SelectPassives(UUID,...)`/`ReplacePassives(UUID,...)` | Level-up passive selection |

## Caveats

- **Delimiter: COMMAS** — Unlike SpellList which uses semicolons. **Critical inconsistency**.
- **Multi-region folder** — Same `Lists/` folder as SpellLists and others.
