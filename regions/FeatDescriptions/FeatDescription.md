# Node: `FeatDescription`

> **Region**: [FeatDescriptions](_REGION.md)
> **Folder**: `Feats/`

---

## Attributes

| Attribute | Type | Frequency | Examples | Notes |
|-----------|------|-----------|----------|-------|
| `UUID` | guid | always | — | Primary key |
| `FeatId` | guid | always | unique feat identifier | Mechanical feat reference |
| `ExactMatch` | FixedString | always | `AbilityScoreIncrease`, `Athlete`, `GreatWeaponMaster`, `Tough` | Matches [Feat.Name](../Feats/Feat.md) |
| `DisplayName` | TranslatedString | always | handle + version | Localized feat name |
| `Description` | TranslatedString | always | handle + version | Localized feat description |

## Cross-References

| From | To | Via |
|------|----|-----|
| FeatDescription.ExactMatch | [Feat](../Feats/Feat.md) | Feat.Name |
| FeatDescription.FeatId | Progression selectors | Internal engine reference |

## Caveats & Gotchas

- **21 vanilla entries** — One per vanilla feat.
- **ExactMatch** is the string link to the mechanical `Feat.Name` (not a UUID). Case-sensitive.
- **FeatId** is a guid that may differ from the Feat.UUID — it's an internal engine reference used by the progression/feat selection system.
- **Missing FeatDescription = invisible feat** — If a custom Feat has no matching FeatDescription (where `ExactMatch == Feat.Name`), the feat appears in the selection UI with no name or description, making it effectively unusable.
- **TranslatedString handles** — Both `DisplayName` and `Description` require corresponding localization entries in `.loca.xml`. Missing handles show `[...]` placeholders.

## Similarities to Other Nodes

- [ProgressionDescription](../ProgressionDescriptions/ProgressionDescription.md) serves the same "display text provider" role for [Progression](../Progressions/Progression.md) entries.
- Both use `ExactMatch` as the primary linking mechanism to their mechanical counterpart.
