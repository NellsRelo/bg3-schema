# Region: `Tags`

> **Folder**: `Tags/`
> **Primary Node**: [Tags](Tags.md)
>
> ~1K UUID-named files

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
<region id="Tags">
  <node id="root">
    <children>
      <node id="Tags"> ... </node>
    </children>
  </node>
</region>
```

## Node Types

| Node | File | Description |
|------|------|-------------|
| Tags | [Tags.md](Tags.md) | Primary node type |

## Cross-Region References

- **Templates** — `GameObjects` reference Tags by UUID; tags drive racial identity, equipment categories, AI behavior, and dialog conditions
- **Races** — `RaceTags` attribute directly references Tag UUIDs
- **Origins** — companion identity tags gate dialog, reactions, and Osiris scripting checks
- **Crime** — `CrimeTags` link crime configs to tag-based regions/NPCs
- **Flags** — tags and flags often coordinate: a tag identifies *what* an entity is, a flag tracks *state* changes
- **Progressions** — tag-based features can be granted via `PassivesAdded` or `Boosts`
- **Osiris** — `IsTagged(object, tag)` is a core query for scripted events
- **Script Extender** — `entity.Tag.Tags` provides runtime tag access

## Caveats

- **UUID-referenced everywhere** — Tags are referenced by UUID across Templates, Races, Origins, Crime, Dialog, and Osiris. Changing a tag UUID breaks all dependents silently
- **~1K files, one tag per file** — each tag lives in its own UUID-named `.lsx` file; bulk edits require tooling
- **Categories are conventions, not engine-enforced** — the `Categories` attribute is a comma-separated string (e.g. `"Code,Dialog"`) but the engine doesn't validate values
- **Custom mod tags** — mods that add new tags must generate unique UUIDs and avoid collisions with vanilla tag UUIDs
