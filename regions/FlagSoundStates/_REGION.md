# Region: `FlagSoundStates`

> **Folder**: `Sound/`
> **Primary Node**: [FlagSoundState](FlagSoundState.md)
>
> Wwise audio switches

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
<region id="FlagSoundStates">
  <node id="root">
    <children>
      <node id="FlagSoundState"> ... </node>
    </children>
  </node>
</region>
```

## Node Types

| Node | File | Description |
|------|------|-------------|
| FlagSoundState | [FlagSoundState.md](FlagSoundState.md) | Primary node type |

## Cross-Region References

*(To be documented)*

## Caveats

- **Folder != Region**: This region lives in `Sound/` not `FlagSoundStates/`
