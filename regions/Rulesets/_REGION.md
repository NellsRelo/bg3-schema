# Region: `Rulesets`

> **Folder**: `Ruleset/`
> **Primary Node**: [Ruleset](Ruleset.md)
>
> 7 difficulty presets

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
<region id="Rulesets">
  <node id="root">
    <children>
      <node id="Ruleset"> ... </node>
    </children>
  </node>
</region>
```

## Node Types

| Node | File | Description |
|------|------|-------------|
| Ruleset | [Ruleset.md](Ruleset.md) | Primary node type |

## Cross-Region References

*(To be documented)*

## Caveats

- **Folder != Region**: This region lives in `Ruleset/` not `Rulesets/`
