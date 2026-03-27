# Region: `ClassDescriptions`

> **Folder**: `ClassDescriptions/`
> **Primary Node**: [ClassDescription](ClassDescription.md)
>
> ~31–36 class/subclass entries (12 base classes + subclasses)

---

## File Inventory

| Source | File | Entries | Version |
|--------|------|---------|---------|
| Shared | ClassDescriptions.lsx | ~31 | 4.7.1 |
| SharedDev | ClassDescriptions.lsx | ~31 | 4.7.1 |
| GustavX | ClassDescriptions.lsx | ~36+ | 4.8.0 |

> Gustav and GustavDev do **not** have ClassDescriptions files.

## Region Structure

```xml
<region id="ClassDescriptions">
  <node id="root">
    <children>
      <node id="ClassDescription"> ... </node>
    </children>
  </node>
</region>
```

## Node Types

| Node | File | Description |
|------|------|-------------|
| ClassDescription | [ClassDescription.md](ClassDescription.md) | Class/subclass definition — attributes, spell config, UI |

## Cross-Region References

| Target Region | Via | Purpose |
|---------------|-----|---------|
| [Progressions](../Progressions/_REGION.md) | `ProgressionTableUUID` → `Progression.TableUUID` | Level-up features for this class |
| [SpellLists](../SpellLists/_REGION.md) | `SpellList` → `SpellList.UUID` | Class spell list |
| [Tags](../Tags/_REGION.md) | child `Tags.Object` → `Tags.UUID` | Classification tags |

## Caveats

- **Folder = Region**: `ClassDescriptions/` maps directly to `ClassDescriptions` region (no mismatch).
- **GustavX adds entries**: Extended Edition adds new classes/subclasses not in Shared.
- **ParentGuid hierarchy**: Subclasses reference their parent class via `ParentGuid`, forming a tree.
