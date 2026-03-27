# Region: `RulesetValues`

> **Folder**: `Ruleset/`
> **Primary Node**: [RulesetValue](RulesetValue.md)
>
> ~36 preset values

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
<region id="RulesetValues">
  <node id="root">
    <children>
      <node id="RulesetValue"> ... </node>
    </children>
  </node>
</region>
```

## Node Types

| Node | File | Description |
|------|------|-------------|
| RulesetValue | [RulesetValue.md](RulesetValue.md) | Primary node type |

## Cross-Region References

*(To be documented)*

## Caveats

- **Folder != Region**: This region lives in `Ruleset/` not `RulesetValues/`
