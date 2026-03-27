# Region: `DialogBank`

> **Category**: Scene
> **Primary Node**: [Resource](Resource.md)
>
> Defines dialog tree resources — metadata entries that reference dialog `.lsj` files.
> Dialog content itself is in the source files; the bank registers them for the engine.

---

## File Inventory

| Source | Path Pattern | Content |
|--------|-------------|---------|
| Shared | `Content/Assets/Dialogs/.../_merged.lsx` | Generic/combat dialogs (9 files) |
| Gustav | `Content/Assets/Dialogs/.../_merged.lsx` | Campaign dialogs (104 files) |

**9 files in Shared, 104 in Gustav** containing DialogBank regions.

## Region Structure

```xml
<region id="DialogBank">
  <node id="DialogBank">
    <children>
      <node id="Resource"> ... </node>
    </children>
  </node>
</region>
```

## Node Types

| Node | File | Description |
|------|------|-------------|
| Resource | [Resource.md](Resource.md) | One per dialog tree — contains speaker slot metadata |

## Cross-Region References

| From | To | Via |
|------|----|-----|
| DialogBank.ID | [TimelineBank](../TimelineBank/_REGION.md) | `DialogResourceId` — timeline dialog link |
| DialogBank.SourceFile | Dialog `.lsj` files | Actual dialog content |

## Attribute Naming Note

Several DialogBank attributes use **lowercase camelCase** (`automated`, `isBehaviour`, `isWorld`) — unusual compared to other banks which use PascalCase. This appears to be a legacy naming convention.
