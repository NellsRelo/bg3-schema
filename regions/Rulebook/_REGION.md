# Region: `Rulebook`

> **Folder**: `Shapeshift/`
> **Primary Node**: [Rule](Rule.md)
>
> Folder != region - wildshape/disguise

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
<region id="Rulebook">
  <node id="root">
    <children>
      <node id="Rule"> ... </node>
    </children>
  </node>
</region>
```

## Node Types

| Node | File | Description |
|------|------|-------------|
| Rule | [Rule.md](Rule.md) | Primary node type |

## Cross-Region References

*(To be documented)*

## Caveats

- **Folder != Region**: This region lives in `Shapeshift/` not `Rulebook/`
