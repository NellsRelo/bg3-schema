# Region: `Templates`

> **Folder**: `RootTemplates/`
> **Primary Node**: [GameObjects](GameObjects.md)
>
> Massive - characters, items, levels

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
<region id="Templates">
  <node id="root">
    <children>
      <node id="GameObjects"> ... </node>
    </children>
  </node>
</region>
```

## Node Types

| Node | File | Description |
|------|------|-------------|
| GameObjects | [GameObjects.md](GameObjects.md) | Primary node type |

## Cross-Region References

| Target Region | Via | Purpose |
|---------------|-----|----------|
| [Races](../Races/_REGION.md) | `GameObjects.Race` | Race UUID for character templates |
| [Tags](../Tags/_REGION.md) | `GameObjects.Tags.Object` | Tag classification |
| [Origins](../Origins/_REGION.md) | `Origin.GlobalTemplate` → `GameObjects.MapKey` | Origin character template |
| Stats TXT (Armor/Weapon/Object/Character) | `GameObjects.Stats` | Name-based item/character stats |
| TreasureTable.txt | `GameObjects.Treasures` | Loot table assignment |
| Equipment.txt | `GameObjects.Equipment` | Starting equipment set |

## Caveats

- **Folder != Region**: This region lives in `RootTemplates/` not `Templates/`
- **Largest region**: Tens of thousands of entities across all sources. Each `_merged.lsx` is 30–40+ MB.
- **Polymorphic**: GameObjects attributes vary entirely by `Type` (item, character, scenery, trigger, surface, projectile, etc.).
- **Template inheritance**: `ParentTemplateId` provides true property inheritance — unique to this region.
- **MapKey, not UUID**: Primary identifier is `MapKey` (FixedString), not the typical `UUID` (guid) used by other regions.
