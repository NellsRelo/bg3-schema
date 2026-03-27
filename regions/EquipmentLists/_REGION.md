# Region: `EquipmentLists`

> **Folder**: `Lists/`
> **Primary Node**: [EquipmentList](EquipmentList.md)

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
<region id="EquipmentLists">
  <node id="root">
    <children>
      <node id="EquipmentList"> ... </node>
    </children>
  </node>
</region>
```

## Node Types

| Node | File | Description |
|------|------|-------------|
| EquipmentList | [EquipmentList.md](EquipmentList.md) | Primary node type |

## Cross-Region References

- **Progressions** — referenced via `SelectEquipment(UUID)` selector in `Progression.Selectors`; grants starting equipment choices at level 1
- **ClassDescriptions** — `ClassEquipment` attribute references equipment list names (name-based, not UUID)
- **Templates** — equipment items referenced in lists must exist as `GameObjects` templates
- **SkillLists / AbilityLists** — sibling list types in the same `Lists/` folder; same structural pattern but different delimiters

## Caveats

- **Folder != Region**: This region lives in `Lists/` not `EquipmentLists/`
- **Semicolon delimiter** — unlike SkillLists and AbilityLists (which use commas), EquipmentLists use semicolons to separate items in the `Items` attribute
