# Node: `CharacterCreationAppearanceMaterial`

> **Region**: [CharacterCreationAppearanceMaterials](_REGION.md)
> **Folder**: `CharacterCreation/`

---

## Attributes

> 183 nodes in Shared (vanilla)

| Attribute | Type | Count | Examples | Notes |
|-----------|------|-------|----------|-------|
| `UUID` | guid | 183/183 | `00894ccc-31ee-4527-94d5-a408cccb3583` | Primary key |
| `DisplayName` | TranslatedString | 183/183 | handle + version | Localized material name |
| `MaterialType` | FixedString | 183/183 | `Tattoo` | Material category |
| `Name` | FixedString | 183/183 | `Tattoo_0`, `Tattoo_1`, `Tattoo_2` | Internal name |
| `MaterialPresetUUID` | guid | 183/183 | material preset reference (often null UUID) | Links to MaterialPresetBank |
| `UIColor` | LSString | 100/183 | `#FF000000`, `#FF0A001C` | Hex color for UI preview |
| `FemaleCameraName` | FixedString | 77/183 | `Camera_01`, `Camera_02` | CC camera angle for female |
| `FemaleRootTemplate` | guid | 77/183 | template UUID | Female body template |
| `MaleCameraName` | FixedString | 77/183 | `Camera_01`, `Camera_02` | CC camera angle for male |
| `MaleRootTemplate` | guid | 77/183 | template UUID | Male body template |
| `DragonbornFemaleRootTemplate` | guid | 17/183 | template UUID | Dragonborn female-specific template |
| `DragonbornMaleRootTemplate` | guid | 17/183 | template UUID | Dragonborn male-specific template |

## Cross-References

| From | To | Via |
|------|----|-----|
| CCAppearanceMaterial.MaterialPresetUUID | MaterialPresetBank | Content bank reference |
| [CCPassiveAppearance](../CharacterCreationPassiveAppearances/CharacterCreationPassiveAppearance.md) | CCAppearanceMaterial | AppearanceMaterialUUIDs child |

## Caveats & Gotchas

- All 183 vanilla entries are tattoo materials (`MaterialType=Tattoo`).
- Dragonborn-specific templates are separate from the standard male/female templates.
- `MaterialPresetUUID` is often the null UUID (`00000000-...`) for entries without a preset.

## Cross-References

| From | To | Via |
|------|----|-----|
| — | — | — |

## Caveats & Gotchas

*(To be documented)*

## Similarities to Other Nodes

*(To be documented)*
