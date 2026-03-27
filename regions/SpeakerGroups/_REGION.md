# Region: `SpeakerGroups`

> **Folder**: `Voice/`
> **Primary Node**: [SpeakerGroup](SpeakerGroup.md)
>
> Race/creature/faction groups

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
<region id="SpeakerGroups">
  <node id="root">
    <children>
      <node id="SpeakerGroup"> ... </node>
    </children>
  </node>
</region>
```

## Node Types

| Node | File | Description |
|------|------|-------------|
| SpeakerGroup | [SpeakerGroup.md](SpeakerGroup.md) | Primary node type |

## Cross-Region References

*(To be documented)*

## Caveats

- **Folder != Region**: This region lives in `Voice/` not `SpeakerGroups/`
