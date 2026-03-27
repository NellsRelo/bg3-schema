# Region: `Gods`

> **Folder**: `Gods/`
> **Primary Node**: [God](God.md)
>
> 18 deities

---

## File Inventory

| Source | File | Entries | Version |
|--------|------|---------|---------|
| Shared | Gods.lsx | 18 | — |
| SharedDev | Gods.lsx | 18 | — |

## Region Structure

```xml
<region id="Gods">
  <node id="root">
    <children>
      <node id="God"> ... </node>
    </children>
  </node>
</region>
```

## Node Types

| Node | File | Description |
|------|------|-------------|
| God | [God.md](God.md) | Deity: name, tags (god ID + alignment) |

## Cross-Region References

| Target Region | Via | Purpose |
|---------------|-----|---------|
| [Races](../Races/_REGION.md) | `God.UUID` ← `Race.ExcludedGods.Object` | Race-deity restrictions |
| [Origins](../Origins/_REGION.md) | `God.UUID` ← `Origin.GodUUID` | Origin patron deity |
| [ClassDescriptions](../ClassDescriptions/_REGION.md) | `ClassDescription.HasGod` (bool) | Classes that select a deity |
| [Tags](../Tags/_REGION.md) | `God.Tags.Object` | God ID + alignment tags |

## Caveats

- **Shared-only** — Gods are only defined in Shared/SharedDev.
