# Node: `EquipmentType`

> **Region**: [EquipmentTypes](_REGION.md)
> **Folder**: `EquipmentTypes/`

---

## Attributes

| Attribute | Type | Frequency | Examples | Notes |
|-----------|------|-----------|----------|-------|
| `UUID` | guid | always | — | Primary key |
| `Name` | FixedString | always | `Helmet`, `Unarmed`, `Battleaxe`, `Dagger`, `Longsword`, `Shield` | Equipment type name |
| `WeaponType_OneHanded` | FixedString | common | `Unarmed1H`, `Slashing1H`, `Small1H`, `Piercing1H` | 1H animation category |
| `WeaponType_TwoHanded` | FixedString | common | `Generic2H`, `Sword2H`, `Polearm2H`, `Crossbow2H` | 2H animation category |
| `BoneMainSheathed` | FixedString | common | `Dummy_Sheath_Upper_L`, `Dummy_Sheath_Hip_L` | Bone attachment when sheathed |
| `BoneMainUnsheathed` | FixedString | common | `Dummy_L_Hand`, `Dummy_R_Hand` | Bone attachment when drawn |
| `BoneOffHandSheathed` | FixedString | common | `Dummy_Sheath_Upper_L`, `Dummy_Sheath_Hip_R` | Off-hand sheathed bone |
| `BoneOffHandUnsheathed` | FixedString | common | `Dummy_L_Hand`, `Dummy_R_Hand` | Off-hand drawn bone |
| `BoneVersatileSheathed` | FixedString | rare | `Dummy_Sheath_Upper_R` | Versatile grip sheathed |
| `BoneVersatileUnsheathed` | FixedString | rare | `Dummy_R_Hand` | Versatile grip drawn |
| `SourceBoneSheathed` | FixedString | common | `Dummy_Sheath` | Source bone for sheathing |
| `SourceBoneAlternativeUnsheathed` | FixedString | rare | `Dummy_Attachment_Rage` | Alt draw bone (rage mode) |
| `SourceBoneVersatileSheathed` | FixedString | common | `Dummy_Sheath`, `Dummy_Sheath_Versatile` | Versatile sheath source |
| `SourceBoneVersatileUnsheathed` | FixedString | rare | `Dummy_Attachment_Versatile` | Versatile draw source |
| `SoundAttackType` | FixedString | common | `Slashing`, `Piercing`, `Bludgeoning`, `Crossbow`, `Bow` | Attack audio profile |
| `SoundEquipmentType` | FixedString | common | `Sword`, `Axe`, `Blunt`, `Polearm`, `Crossbow`, `Bow` | Equip/draw audio |

## Cross-References

| From | To | Via |
|------|----|-----|
| EquipmentType.Name | [WeaponAnimationSet](../WeaponAnimationSetData/WeaponAnimationSet.md) | MainHand/OffHand categories |
| EquipmentType.Name | Stats Weapon/Armor data | `Proficiency Group` field |

## Caveats & Gotchas

- **Bone attributes** use `Dummy_` skeleton attachment points — these are model-specific bone names.
- **WeaponType_*** values map to animation set categories, not damage types.
- `SourceBoneAlternativeUnsheathed` is only used for special states (e.g., Rage mode drawing).
