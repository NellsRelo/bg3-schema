# Node: `CharacterCreationPassiveAppearance`

> **Region**: [CharacterCreationPassiveAppearances](_REGION.md)
> **Folder**: `CharacterCreation/`

---

## Attributes

> 30 nodes in Shared (vanilla)

| Attribute | Type | Count | Examples | Notes |
|-----------|------|-------|----------|-------|
| `UUID` | guid | 30/30 | `9e6241bb-d443-4150-b28d-26803d092f16` | Primary key |
| `Passive` | FixedString | 30/30 | `DraconicAncestry_Black`, `DraconicAncestry_Blue`, `DraconicAncestry_Brass` | Stats passive name this appearance maps to |
| `RaceUUID` | guid | 15/30 | links to Race.UUID | Race-specific visual overrides (Dragonborn) |

## Child Nodes

| Node | Count | Notes |
|------|-------|-------|
| `AccessorySetUUIDs` | 50 entries | Accessory set references per passive |
| `AppearanceMaterialUUIDs` | 70 entries | Material references per passive |
| `ColorMaterialUUIDs` | 101 entries | Color material references per passive |

## Cross-References

| From | To | Via |
|------|----|-----|
| CCPassiveAppearance.Passive | Stats PassiveData | Entry name match |
| CCPassiveAppearance.RaceUUID | [Race](../Races/Race.md) | Race.UUID |
| AccessorySetUUIDs | [CCAccessorySet](../CharacterCreationAccessorySets/CharacterCreationAccessorySet.md) | UUID references |
| AppearanceMaterialUUIDs | [CCAppearanceMaterial](../CharacterCreationAppearanceMaterials/CharacterCreationAppearanceMaterial.md) | UUID references |

## Caveats & Gotchas

- All 30 vanilla entries are Draconic Ancestry passives — maps dragon type visual appearances.
- Links passive selection (e.g., `DraconicAncestry_Black`) to visual accessories, materials, and colors.
- `RaceUUID` is only set for half the entries (Dragonborn-specific).

## Cross-References

| From | To | Via |
|------|----|-----|
| — | — | — |

## Caveats & Gotchas

*(To be documented)*

## Similarities to Other Nodes

*(To be documented)*
