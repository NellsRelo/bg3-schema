# Node: `CharacterCreationAccessorySet`

> **Region**: [CharacterCreationAccessorySets](_REGION.md)
> **Folder**: `CharacterCreation/`

---

## Attributes

> 41 nodes in Shared (vanilla)

| Attribute | Type | Count | Examples | Notes |
|-----------|------|-------|----------|-------|
| `UUID` | guid | 41/41 | `f73c803d-7b7e-4703-9004-382b8c588b70` | Primary key |
| `DisplayName` | TranslatedString | 41/41 | handle + version | Localized accessory set name |
| `SlotName` | FixedString | 41/41 | `Piercing` | Cosmetic slot |
| `CharacterCreationSet` | bool | 41/41 | `true`, `false` | Whether visible in CC |
| `RaceUUID` | guid | 19/41 | links to Race.UUID | Race-specific accessory sets |

## Child Nodes

### VisualUUIDs

| Node | Count | Notes |
|------|-------|-------|
| `VisualUUIDs` | 217 entries | Individual visual references within the set |

Child structure: `VisualUUIDs` → child `Object` guid entries

### DefaultForRootTemplates

| Node | Count | Notes |
|------|-------|-------|
| `DefaultForRootTemplates` | 1 entry | Default template association |

## Cross-References

| From | To | Via |
|------|----|-----|
| CCAccessorySet.RaceUUID | [Race](../Races/Race.md) | Race.UUID |
| CCAccessorySet.VisualUUIDs | [CCSharedVisual](../CharacterCreationSharedVisuals/CharacterCreationSharedVisual.md) | Visual UUID references |

## Caveats & Gotchas

- `CharacterCreationSet=true` means it appears in the CC UI; `false` entries are used internally.
- Most accessory sets are piercings.

## Cross-References

| From | To | Via |
|------|----|-----|
| — | — | — |

## Caveats & Gotchas

*(To be documented)*

## Similarities to Other Nodes

*(To be documented)*
