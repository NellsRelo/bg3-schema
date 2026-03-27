# Node: `CharacterCreationSharedVisual`

> **Region**: [CharacterCreationSharedVisuals](_REGION.md)
> **Folder**: `CharacterCreation/`

---

## Attributes

> 405 nodes in Shared (vanilla)

| Attribute | Type | Count | Examples | Notes |
|-----------|------|-------|----------|-------|
| `UUID` | guid | 405/405 | `06d99409-955b-474b-91ed-6fb8a69e3d3d` | Primary key |
| `DisplayName` | TranslatedString | 405/405 | handle + version | Localized visual name |
| `SlotName` | FixedString | 405/405 | `Beard`, `Piercing` | Cosmetic slot |
| `VisualResource` | guid | 405/405 | `4e450c42-b084-fcee-a10a-a891ea91fe64` | GR2/visual resource (may be null UUID) |
| `BoneName` | FixedString | 222/405 | `piercing_lobe_b_r`, `piercing_helix_a_r` | Skeleton bone attachment point |

## Cross-References

| From | To | Via |
|------|----|-----|
| [CCAccessorySet](../CharacterCreationAccessorySets/CharacterCreationAccessorySet.md) | CCSharedVisual | VisualUUIDs child objects |
| [VisualLocatorAttachment](../VisualLocatorAttachments/VisualLocatorAttachment.md) | CCSharedVisual.BoneName | LocatorName matching |

## Caveats & Gotchas

- Beards and piercings are the main visual types.
- `VisualResource` can be null UUID for placeholder entries.
- `BoneName` is mainly used for piercings (bone attachment points on the model skeleton).

## Cross-References

| From | To | Via |
|------|----|-----|
| — | — | — |

## Caveats & Gotchas

*(To be documented)*

## Similarities to Other Nodes

*(To be documented)*
