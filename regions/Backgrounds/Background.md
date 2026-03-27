# Node: `Background`

> **Region**: [Backgrounds](_REGION.md)
> **Folder**: `Backgrounds/`

---

## Attributes

| Attribute | Type | Frequency | Examples | Notes |
|-----------|------|-----------|----------|-------|
| `UUID` | guid | always | — | Primary key |
| `DisplayName` | TranslatedString | always | handle + version | Localized background name |
| `Description` | TranslatedString | always | handle + version | Localized description |
| `Passives` | LSString | always | `Background_Acolyte`, `Background_Charlatan` | Background passive feature |

## Child Nodes

### Tags

| Attribute | Type | Frequency | Notes |
|-----------|------|-----------|-------|
| `Object` | guid | always | Background tag UUID |

## Cross-References

| From | To | Via |
|------|----|-----|
| Background.UUID | [Origin](../Origins/Origin.md) | Origin.BackgroundUUID |
| Background.UUID | [BackgroundGoal](../BackgroundGoals/BackgroundGoal.md) | BackgroundGoal.BackgroundUUID |
| Background.Tags.Object | [Tags](../Tags/Tags.md) | Tags.UUID |

## Caveats & Gotchas

- **11 vanilla backgrounds** in Shared.
- `Passives` field is a single passive name, not semicolon-delimited (unlike Progression/Origin). However, mods may use semicolons for multiple passives.
- **Passives is a name-based reference** (case-sensitive) to `Passive.txt` entries. A misspelled passive name means the background grants nothing — with no error in-game.
- **BackgroundGoals** — Inspiration goals for each background are in a separate region ([BackgroundGoals](../BackgroundGoals/_REGION.md)) in the same folder, linked via `BackgroundGoal.BackgroundUUID` → `Background.UUID`. These are **Gustav-only** — mods adding inspiration goals need to handle the Gustav source path.
- **Tags** — Each background has classification tags used in dialog conditions and Osiris scripts. Custom backgrounds should include appropriate tags.
- **No ProgressionTableUUID** — Unlike [ClassDescription](../ClassDescriptions/ClassDescription.md) and [Race](../Races/Race.md), backgrounds do not have progression tables. Background features are granted solely via the `Passives` field.

## Similarities to Other Nodes

- [Origin](../Origins/Origin.md) references backgrounds via `BackgroundUUID`.
- Same `Tags` child node pattern as [ClassDescription](../ClassDescriptions/ClassDescription.md), [Race](../Races/Race.md), [God](../Gods/God.md).
