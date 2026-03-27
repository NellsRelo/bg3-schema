# Region: `Progressions`

> **Folder**: `Progressions/`
> **Primary Node**: [Progression](Progression.md)
>
> Level-up feature table, 500+ entries across all sources

---

## File Inventory

| Source | File | Entries | Version |
|--------|------|---------|---------|
| Shared | Progressions.lsx | 100+ | 4.5.0 |
| SharedDev | Progressions.lsx | 100+ | 4.5.0 |
| Gustav | Progressions.lsx | 50+ | 4.5.0 |
| GustavDev | Progressions.lsx | 50+ | 4.5.0 |
| GustavX | Progressions.lsx | 100+ | 4.5.0 |

> **Note**: ProgressionDescriptions reside in the same folder but are a separate region — see [ProgressionDescriptions](../ProgressionDescriptions/_REGION.md).

## Region Structure

```xml
<region id="Progressions">
  <node id="root">
    <children>
      <node id="Progression"> ... </node>
    </children>
  </node>
</region>
```

## Node Types

| Node | File | Description |
|------|------|-------------|
| Progression | [Progression.md](Progression.md) | Level-up feature row: boosts, passives, selectors, subclass forks |

## Cross-Region References

| Target Region | Via | Purpose |
|---------------|-----|----------|
| [ClassDescriptions](../ClassDescriptions/_REGION.md) | `TableUUID` → `ClassDescription.ProgressionTableUUID` | Which class this table belongs to |
| [SpellLists](../SpellLists/_REGION.md) | Selector GUIDs → `SpellList.UUID` | Spells available at this level |
| [PassiveLists](../PassiveLists/_REGION.md) | Selector GUIDs → `PassiveList.UUID` | Passives selectable at this level |
| [SkillLists](../SkillLists/_REGION.md) | Selector GUIDs → `SkillList.UUID` | Skills selectable at this level |
| [AbilityLists](../AbilityLists/_REGION.md) | Selector GUIDs → `AbilityList.UUID` | Abilities selectable at this level |

## Caveats

- **Multi-source folder**: Progressions/ also contains ProgressionDescriptions.lsx (separate region `ProgressionDescriptions`).
- **All five sources have data**: Every source (Shared, SharedDev, Gustav, GustavDev, GustavX) contributes Progression entries.
- **Level caps**: Vanilla only goes to Level 12. Entries beyond Level 12 are mod-only.
