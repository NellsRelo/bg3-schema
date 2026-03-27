# Node: `VisualLocatorAttachment`

> **Region**: [VisualLocatorAttachments](_REGION.md)
> **Folder**: `CharacterCreation/`

---

## Attributes

> 35 nodes in Shared (vanilla)

| Attribute | Type | Count | Examples | Notes |
|-----------|------|-------|----------|-------|
| `UUID` | guid | 35/35 | `165f4a6e-eada-4235-a731-635428e3c0a3` | Primary key |
| `DisplayName` | FixedString | 35/35 | `Piercing Tragus A (R)`, `Piercing Helix A (R)` | Human-readable locator name (NOT TranslatedString) |
| `LocatorName` | FixedString | 35/35 | `piercing_tragus_a_r`, `piercing_helix_a_r` | Skeleton bone locator name |

## Cross-References

| From | To | Via |
|------|----|-----|
| VisualLocatorAttachment.LocatorName | [CCSharedVisual](../CharacterCreationSharedVisuals/CharacterCreationSharedVisual.md).BoneName | Bone name matching |

## Caveats & Gotchas

- All 35 entries are piercing attachment points on the character skeleton.
- `DisplayName` is `FixedString` (not `TranslatedString`) — these are internal names, not localized.
- Locator names follow pattern: `piercing_{location}_{variant}_{side}` (e.g., `piercing_tragus_a_r`).

## Cross-References

| From | To | Via |
|------|----|-----|
| — | — | — |

## Caveats & Gotchas

*(To be documented)*

## Similarities to Other Nodes

*(To be documented)*
