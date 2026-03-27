# Region: `Gossips`

> **Folder**: `Gossips/`
> **Primary Node**: [Gossip](Gossip.md)
>
> Gustav only

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
<region id="Gossips">
  <node id="root">
    <children>
      <node id="Gossip"> ... </node>
    </children>
  </node>
</region>
```

## Node Types

| Node | File | Description |
|------|------|-------------|
| Gossip | [Gossip.md](Gossip.md) | Primary node type |

## Cross-Region References

- **Flags** — `ConditionFlags` gate when a gossip can trigger; `ResultFlags` are set/cleared when a gossip fires. Both reference Flag UUIDs
- **Dialog** — gossip entries trigger dialog scenes; `DialogUUID` links to the actual dialog tree
- **Origins** — companion gossips are speaker-specific; `SpeakerGroup` and `Priority` determine which companion speaks
- **Tags** — tag-based conditions can appear in gossip speaker requirements

## Caveats

- **Gustav-only** — gossip entries are campaign-specific content
- **Priority system** — when multiple gossips are eligible, the highest `Priority` value wins. Duplicate priorities can cause non-deterministic speaker selection
- **Flag dependency chains** — gossips can chain via ResultFlags → ConditionFlags on other gossips. Broken flag references cause silent failures (gossip simply never triggers)
