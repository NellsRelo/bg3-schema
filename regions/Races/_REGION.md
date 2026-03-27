# Region: `Races`

> **Folder**: `Races/`
> **Primary Node**: [Race](Race.md)
>
> ~24 races (12 base + 12 sub-races) with deep color child node hierarchies

---

## File Inventory

| Source | File | Entries | Version |
|--------|------|---------|---------|
| Shared | Races.lsx | ~24 | — |
| SharedDev | Races.lsx | ~24 | — |

> Gustav, GustavDev, and GustavX do **not** have Races files.

## Region Structure

```xml
<region id="Races">
  <node id="root">
    <children>
      <node id="Race"> ... </node>
    </children>
  </node>
</region>
```

## Node Types

| Node | File | Description |
|------|------|-------------|
| Race | [Race.md](Race.md) | Race/sub-race: attributes, color palettes, deity restrictions, tags |

## Cross-Region References

| Target Region | Via | Purpose |
|---------------|-----|---------|
| [Progressions](../Progressions/_REGION.md) | `ProgressionTableUUID` → `Progression.TableUUID` | Racial features per level |
| [Gods](../Gods/_REGION.md) | `ExcludedGods.Object` → `God.UUID` | Deities not available for this race |
| [Tags](../Tags/_REGION.md) | `Tags.Object` → `Tags.UUID` | Race classification tags |
| [CC Presets](../CharacterCreationPresets/_REGION.md) | Color UUIDs → preset entries | Character creation color palettes |

## Caveats

- **Shared-only region**: Races are only defined in Shared/SharedDev. Mods add races via Shared source.
- **Deep child hierarchy**: Each Race node can contain 0–80+ color child nodes (SkinColors, EyeColors, HairColors, etc.).
- **Sub-race linking**: Sub-races use `ParentGuid` to reference the base race and `DisplayTypeUUID` for UI grouping.
