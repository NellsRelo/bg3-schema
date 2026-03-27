# Region: `TooltipExtraTexts`

> **Folder**: `TooltipExtras/`
> **Primary Node**: [TooltipExtraTexts](TooltipExtraTexts.md)

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
<region id="TooltipExtraTexts">
  <node id="root">
    <children>
      <node id="TooltipExtraTexts"> ... </node>
    </children>
  </node>
</region>
```

## Node Types

| Node | File | Description |
|------|------|-------------|
| TooltipExtraTexts | [TooltipExtraTexts.md](TooltipExtraTexts.md) | Primary node type |

## Cross-Region References

- **Stats TXT** — spells and passives reference `TooltipDamageList` or `TooltipStatusApply` by name in their Stats definitions, which link to entries here
- **DealDamage functor** — the three-way connection: Stats TXT spell → `DealDamage()` functor → `TooltipDamageList` entry here → UI tooltip display
- **Localization** — tooltip text uses localization handles for display strings
- **Progressions** — passives granted by Progressions may reference TooltipExtraTexts for their damage/status display

## Caveats

- **Folder != Region**: This region lives in `TooltipExtras/` not `TooltipExtraTexts/`
- **Name-based referencing** — Stats TXT references these entries by string name, not UUID. Typos cause silent tooltip failures (damage/status just won't appear in the UI)
