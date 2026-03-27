# Node: `CrowdCharacterTemplates`

> **Region**: [CrowdCharacterTemplates](_REGION.md)
> **Folder**: `CrowdCharacters/`
> **Vanilla entries**: 26 (SharedDev)

---

## Attributes

| Attribute | Type | Frequency | Examples | Notes |
|-----------|------|-----------|----------|-------|
| `UUID` | guid | 26/26 | `73a33ffa-...` | Primary key |
| `Name` | FixedString | 26/26 | `BASE_Humans_Male_Crowd_Poor_A` | Template name (race+gender+wealth) |
| `CharacterTemplateUUID` | guid | 26/26 | `1807912e-...` | References root template |
| `ClothsColorsUUID` | guid | 26/26 | `68126a94-...` | References CrowdCharacterClothsColors |
| `EyeColorsUUID` | guid | 26/26 | `f676fed7-...` | References CrowdCharacterEyeColors |
| `SkinColorsUUID` | guid | 26/26 | `abd89b8b-...` | References CrowdCharacterSkinColors |

## Child Nodes

*(None in vanilla data)*

## Patterns of Use

- Assembles crowd NPCs from template + color palettes.
- Names encode: `BASE_{Race}_{Gender}_Crowd_{Wealth}_{Variant}`.
- All 26 entries have all attributes (no optional fields).

## Cross-References

| From | To | Via |
|------|----|-----|
| CrowdCharacterTemplates | GameObjects | `CharacterTemplateUUID` |
| CrowdCharacterTemplates | CrowdCharacterClothsColors | `ClothsColorsUUID` |
| CrowdCharacterTemplates | CrowdCharacterEyeColors | `EyeColorsUUID` |
| CrowdCharacterTemplates | CrowdCharacterSkinColors | `SkinColorsUUID` |

## Caveats & Gotchas

- Only for crowd system — not used by player or companion characters.

## Similarities to Other Nodes

- **CompanionPresets**: Similar "assemble from parts" pattern but for companion characters.
