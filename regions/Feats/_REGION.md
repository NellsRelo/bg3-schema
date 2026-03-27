# Region: `Feats`

> **Folder**: `Feats/`
> **Primary Node**: [Feat](Feat.md)
>
> Empty in vanilla — mods populate this with mechanical feat definitions

---

## File Inventory

| Source | File | Entries | Version |
|--------|------|---------|---------|
| Shared | Feats.lsx | 0 (empty container) | — |
| Shared | FeatDescriptions.lsx | 23 | — |
| Shared | FeatSoundStates.lsx | metadata | — |
| SharedDev | Feats.lsx | 0 (empty) | — |
| SharedDev | FeatDescriptions.lsx | 23 | — |
| SharedDev | FeatSoundStates.lsx | metadata | — |

> **Multi-region folder**: `Feats/` contains 3 different regions: `Feats`, `FeatDescriptions`, `FeatSoundStates`.

## Region Structure

```xml
<region id="Feats">
  <node id="root">
    <children>
      <node id="Feat"> ... </node>
    </children>
  </node>
</region>
```

## Node Types

| Node | File | Description |
|------|------|-------------|
| Feat | [Feat.md](Feat.md) | Mechanical feat: requirements, selectors, passives |

## Cross-Region References

| Target Region | Via | Purpose |
|---------------|-----|---------|
| [FeatDescriptions](../FeatDescriptions/_REGION.md) | `Name` → `FeatDescription.ExactMatch` | Display name/description |
| [SpellLists](../SpellLists/_REGION.md) | Selector GUIDs | Spells granted by feat |
| [PassiveLists](../PassiveLists/_REGION.md) | Selector GUIDs | Passives granted by feat |

## Caveats

- **Empty in vanilla**: `Feats.lsx` has zero entries. All vanilla feat mechanics are built into the engine. Mods use this region to define custom feats.
- **Multi-region folder**: Same folder has `FeatDescriptions` and `FeatSoundStates` regions.
