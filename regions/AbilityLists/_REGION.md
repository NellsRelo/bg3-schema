# Region: `AbilityLists`

> **Folder**: `Lists/`
> **Primary Node**: [AbilityList](AbilityList.md)
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
<region id="AbilityLists">
  <node id="root">
    <children>
      <node id="AbilityList"> ... </node>
    </children>
  </node>
</region>
```

## Node Types

| Node | File | Description |
|------|------|-------------|
| AbilityList | [AbilityList.md](AbilityList.md) | Primary node type |

## Cross-Region References

- **Progressions** — referenced via `SelectAbilities(UUID,count)` and `SelectAbilityBonus(UUID,maxBonus,count)` selectors in `Progression.Selectors`
- **Races** — racial ability score increases are granted through AbilityList references in racial Progressions
- **SkillLists** — sibling list type in the same `Lists/` folder; same UUID + comma-separated values pattern
- **EquipmentLists** — sibling list type in `Lists/`; same structural pattern

## Caveats

- **Folder != Region**: This region lives in `Lists/` not `AbilityLists/`
- **Two selector functions** — `SelectAbilities` offers a free-choice pick, while `SelectAbilityBonus` constrains the maximum bonus amount. Using the wrong one causes unexpected ability score behavior
