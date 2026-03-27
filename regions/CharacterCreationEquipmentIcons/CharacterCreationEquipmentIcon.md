# Node: `CharacterCreationEquipmentIcon`

> **Region**: [CharacterCreationEquipmentIcons](_REGION.md)
> **Folder**: `CharacterCreation/`

---

## Attributes

> 12 nodes in Shared (vanilla)

| Attribute | Type | Count | Examples | Notes |
|-----------|------|-------|----------|-------|
| `UUID` | guid | 12/12 | `147167dd-bb00-4197-926a-97825618f455` | Primary key |
| `SlotName` | FixedString | 12/12 | `Footwear`, `Cloak`, `Gloves` | Equipment slot |
| `RootTemplate` | guid | 12/12 | `75a43caa-175d-446f-a879-77bb3697070c` | Character template for icon rendering |
| `EquipmentTemplate` | guid | 12/12 | `6ea46549-90eb-45fc-8ece-238cf8c4065c` | Equipment item template |
| `AnimationUUID` | guid | 12/12 | `beeabe70-56cd-4cb4-aa83-4f032dcfe146` | Pose animation for icon |
| `MeshIsTwoSided` | bool | 2/12 | `true` | Double-sided mesh rendering |

## Cross-References

| From | To | Via |
|------|----|-----|
| CCEquipmentIcon.RootTemplate | Templates | GameObjects.MapKey |
| CCEquipmentIcon.EquipmentTemplate | Templates | Item template UUID |

## Caveats & Gotchas

- Used to render equipment preview icons in character creation.
- Only 12 entries covering the main equipment slots.

## Cross-References

| From | To | Via |
|------|----|-----|
| — | — | — |

## Caveats & Gotchas

*(To be documented)*

## Similarities to Other Nodes

*(To be documented)*
