# Region: `Backgrounds`

> **Folder**: `Backgrounds/`
> **Primary Node**: [Background](Background.md)
>
> 12 backgrounds (Shared)

---

## File Inventory

| Source | File | Entries | Version |
|--------|------|---------|---------|
| Shared | Backgrounds.lsx | 12 | — |
| SharedDev | Backgrounds.lsx | 12 | — |

> **Multi-region folder**: `Backgrounds/` also contains BackgroundGoals.lsx (region `BackgroundGoals`, Gustav only).

## Region Structure

```xml
<region id="Backgrounds">
  <node id="root">
    <children>
      <node id="Background"> ... </node>
    </children>
  </node>
</region>
```

## Node Types

| Node | File | Description |
|------|------|-------------|
| Background | [Background.md](Background.md) | Background: passives, tags |

## Cross-Region References

| Target Region | Via | Purpose |
|---------------|-----|---------|
| [Origins](../Origins/_REGION.md) | `Background.UUID` ← `Origin.BackgroundUUID` | Origin default background |
| [BackgroundGoals](../BackgroundGoals/_REGION.md) | `Background.UUID` ← `BackgroundGoal.BackgroundUUID` | Inspiration goals |
| [Tags](../Tags/_REGION.md) | `Tags.Object` | Background classification |

## Caveats

- **Shared-only** for Backgrounds. Gustav's Backgrounds/ folder only contains BackgroundGoals.
- **Multi-region folder** — same folder has `Backgrounds` and `BackgroundGoals` regions.
