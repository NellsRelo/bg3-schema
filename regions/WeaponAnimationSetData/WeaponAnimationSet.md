# Node: `WeaponAnimationSet`

> **Region**: [WeaponAnimationSetData](_REGION.md)
> **Folder**: `WeaponAnimationSetData/`

---

## Attributes

> 42 nodes in Shared (vanilla)

| Attribute | Type | Count | Examples | Notes |
|-----------|------|-------|----------|-------|
| `UUID` | guid | 42/42 | `7adcc1d1-6d19-4580-bc2e-0913164285ca` | Primary key |
| `AnimationSetUUID` | FixedString | 42/42 | `f491b41b-c173-43f7-ae34-9c426de2307e` | Animation set resource reference |
| `MainHand` | FixedString | 40/42 | `Crossbow1H`, `Piercing1H`, `Slashing1H` | Main hand weapon animation category |
| `OffHand` | FixedString | 23/42 | `Crossbow1H`, `Piercing1H`, `Slashing1H` | Off-hand weapon animation category |

## Cross-References

| From | To | Via |
|------|----|-----|
| WeaponAnimationSet.MainHand/OffHand | [EquipmentType](../EquipmentTypes/EquipmentType.md) | EquipmentType.WeaponType_OneHanded / WeaponType_TwoHanded |

## Caveats & Gotchas

- `MainHand` and `OffHand` values match `WeaponType_OneHanded`/`WeaponType_TwoHanded` from EquipmentTypes.
- `AnimationSetUUID` is stored as FixedString (not guid type) despite being a UUID.
- Combinations of MainHand + OffHand determine the full dual-wield animation set.

## Cross-References

| From | To | Via |
|------|----|-----|
| — | — | — |

## Caveats & Gotchas

*(To be documented)*

## Similarities to Other Nodes

*(To be documented)*
