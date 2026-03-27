# Node: `God`

> **Region**: [Gods](_REGION.md)
> **Folder**: `Gods/`

---

## Attributes

| Attribute | Type | Frequency | Examples | Notes |
|-----------|------|-----------|----------|-------|
| `UUID` | guid | always | — | Primary key |
| `Name` | FixedString | always | `Selune`, `Shar`, `Tempus`, `Tyr`, `Helm` | Internal name |
| `DisplayName` | TranslatedString | always | handle + version | Localized deity name |
| `Description` | TranslatedString | always | handle + version | Localized description |

## Child Nodes

### Tags (typically 2 per God)

| Attribute | Type | Frequency | Notes |
|-----------|------|-----------|-------|
| `Object` | guid | always | Tag 1: specific god ID; Tag 2: alignment (Good/Evil/Neutral) |

## Cross-References

| From | To | Via |
|------|----|-----|
| God.UUID | [Race](../Races/Race.md) | Race.ExcludedGods.Object |
| God.UUID | [Origin](../Origins/Origin.md) | Origin.GodUUID |
| God.UUID | [ClassDescription](../ClassDescriptions/ClassDescription.md) | ClassDescription.HasGod (boolean flag) |
| God.Tags.Object | [Tags](../Tags/Tags.md) | Tags.UUID |

## Caveats & Gotchas

- **21 deities** in Shared (vanilla).
- **Two Tags per God** — first is the god-specific tag, second is the alignment tag (Good/Evil/Neutral). Not documented which is which — check the tag's own name.
- **ExcludedGods on Race** — Some races exclude certain gods (e.g., Drow typically exclude good-aligned deities via [Race](../Races/Race.md).ExcludedGods).
- **Deity selection** — Only classes with `ClassDescription.HasGod=true` (Clerics, Paladins) present the deity selection screen in character creation. The available deities = all Gods MINUS the character's race ExcludedGods.
- **Tags drive dialog conditions** — God tags are checked in dialog conditions and Osiris scripts. A custom deity mod must create corresponding Tags for dialog/quest compatibility.
- **God-specific subclass mechanics** — Cleric domains are subclasses, but the god selection is separate from subclass selection. The connection between a god and a domain is narrative only — mechanically, any Cleric can worship any available god regardless of domain.

## Similarities to Other Nodes

- [Race](../Races/Race.md) restricts available gods via `ExcludedGods` children.
- [Origin](../Origins/Origin.md) sets a default god via `GodUUID`.
- [Background](../Backgrounds/Background.md), [ClassDescription](../ClassDescriptions/ClassDescription.md) share the same `Tags` child node pattern.
