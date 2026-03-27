# Region: `ProgressionDescriptions`

> **Folder**: `Progressions/`
> **Primary Node**: [ProgressionDescription](ProgressionDescription.md)
>
> Tooltip text for level-up features

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
<region id="ProgressionDescriptions">
  <node id="root">
    <children>
      <node id="ProgressionDescription"> ... </node>
    </children>
  </node>
</region>
```

## Node Types

| Node | File | Description |
|------|------|-------------|
| ProgressionDescription | [ProgressionDescription.md](ProgressionDescription.md) | Primary node type |

## Cross-Region References

- **Progressions** — ProgressionDescription entries describe features granted by Progressions; linked by `ProgressionTableId` (matching `Progression.TableUUID`) and optionally by `SelectorId` / `PassivePrototype`
- **FeatDescriptions** — sibling description region following the same localization pattern; covers Feats instead of Progression features
- **Localization** — `DisplayName`, `Description`, and `ExactMatch`/`ParamMatch` text all use localization handles

## Caveats

- **Folder != Region**: This region lives in `Progressions/` not `ProgressionDescriptions/`
- **Cascading specificity** — the engine resolves descriptions via a specificity cascade: ExactMatch (most specific) → ParamMatch → SelectorId → ProgressionTableId (broadest). Missing a level in the cascade can cause wrong or blank tooltip text
