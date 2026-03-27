# Region: `SkillLists`

> **Folder**: `Lists/`
> **Primary Node**: [SkillList](SkillList.md)
>
> Delimiter: commas

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
<region id="SkillLists">
  <node id="root">
    <children>
      <node id="SkillList"> ... </node>
    </children>
  </node>
</region>
```

## Node Types

| Node | File | Description |
|------|------|-------------|
| SkillList | [SkillList.md](SkillList.md) | Primary node type |

## Cross-Region References

- **Progressions** — referenced via `SelectSkills(UUID,count)` and `SelectSkillsExpertise(UUID,count)` selectors in `Progression.Selectors`
- **AbilityLists** — sibling list type in the same `Lists/` folder; both follow the same UUID + comma-separated values pattern
- **EquipmentLists** — sibling list type in `Lists/`; same structural pattern
- **ClassDescriptions** — class skill proficiencies are ultimately granted through SkillList references in Progressions

## Caveats

- **Folder != Region**: This region lives in `Lists/` not `SkillLists/`
- **Delimiter is commas** — skill names in the `Skills` attribute are comma-separated (unlike EquipmentLists which use semicolons)
