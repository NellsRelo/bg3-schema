# Region: `SpellLists`

> **Folder**: `Lists/`
> **Primary Node**: [SpellList](SpellList.md)
>
> 50+ spell lists (Shared), used by Progression selectors. Delimiter: **semicolons**.

---

## File Inventory

| Source | File | Entries | Version |
|--------|------|---------|---------|
| Shared | SpellLists.lsx | 50+ | — |
| SharedDev | SpellLists.lsx | varies | — |
| GustavX | SpellLists.lsx | varies | — |

> **Multi-region folder**: `Lists/` contains 12 different regions.

## Region Structure

```xml
<region id="SpellLists">
  <node id="root">
    <children>
      <node id="SpellList"> ... </node>
    </children>
  </node>
</region>
```

## Node Types

| Node | File | Description |
|------|------|-------------|
| SpellList | [SpellList.md](SpellList.md) | List of spell identifiers (semicolon-delimited) |

## Cross-Region References

| Target Region | Via | Purpose |
|---------------|-----|---------|
| [ClassDescriptions](../ClassDescriptions/_REGION.md) | `SpellList.UUID` ← `ClassDescription.SpellList` | Class spell list |
| [Progressions](../Progressions/_REGION.md) | `SpellList.UUID` ← `SelectSpells(UUID,...)`/`AddSpells(UUID)` | Level-up spell selection |

## Caveats

- **Delimiter: SEMICOLONS** — Unlike PassiveList/SkillList which use commas.
- **Multi-region folder** — `Lists/` has 12 regions.
