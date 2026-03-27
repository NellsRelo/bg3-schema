# Node: `CharacterCreationAppearanceVisual`

> **Region**: [CharacterCreationAppearanceVisuals](_REGION.md)
> **Folder**: `CharacterCreation/`

---

## Attributes

> 598 nodes in Shared (vanilla)

| Attribute | Type | Count | Examples | Notes |
|-----------|------|-------|----------|-------|
| `UUID` | guid | 598/598 | `b24d2bbc-f40a-4c61-a8c5-6575d78be612` | Primary key |
| `DisplayName` | TranslatedString | 598/598 | handle + version | Localized visual name |
| `SlotName` | FixedString | 598/598 | `Hair`, `Head`, `Beard` | Cosmetic slot this visual occupies |
| `VisualResource` | guid | 598/598 | `bf6ea9d0-db38-d44c-8cbd-12e6aca03044` | GR2/visual resource reference |
| `BodyShape` | uint8 | 589/598 | `0`, `1` | Body build filter (0=Regular, 1=Strong) |
| `BodyType` | uint8 | 589/598 | `0`, `1` | Body type filter (0=Masculine, 1=Feminine) |
| `RaceUUID` | guid | 589/598 | links to Race.UUID | Race this visual belongs to |
| `DefaultSkinColor` | guid | 218/598 | `00000000-0000-0000-0000-000000000000` | Default skin color override |
| `IconIdOverride` | FixedString | 80/598 | `0_Hair_66c89035-...` | CC icon override |
| `RootTemplate` | guid | 9/598 | `7d427a86-81f0-418d-a32a-3b5676c86bfa` | Template override |

## Cross-References

| From | To | Via |
|------|----|-----|
| CCAppearanceVisual.RaceUUID | [Race](../Races/Race.md) | Race.UUID |
| Race.Visuals.Object | CCAppearanceVisual | CCAppearanceVisual.UUID |

## Caveats & Gotchas

- Filtered by `BodyShape` + `BodyType` + `RaceUUID` to determine which visuals are available for a given character.
- `DefaultSkinColor` is often the null UUID (`00000000-...`).
- SharedDev adds more entries for companion-specific visuals.

## Similarities to Other Nodes

- [CharacterCreationSharedVisual](../CharacterCreationSharedVisuals/CharacterCreationSharedVisual.md) also maps SlotName → VisualResource with race/body filters.

## Cross-References

| From | To | Via |
|------|----|-----|
| — | — | — |

## Caveats & Gotchas

*(To be documented)*

## Similarities to Other Nodes

*(To be documented)*
