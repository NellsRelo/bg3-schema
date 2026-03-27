# Equipment.txt

> **Path**: `Stats/Generated/Equipment.txt`
> **Format**: Imperative `add` commands
> **Packs**: Gustav, GustavDev, GustavX, Shared, SharedDev

## Purpose

Defines starting equipment loadouts for NPCs and player character creation classes. Each equipment set specifies weapon set configurations and a sequence of equipment groups, each containing one item entry.

## Format

```
new equipment "NAME"
add initialweaponset "Melee"|"Ranged"
add equipmentgroup
add equipment entry "STATS_ENTRY_NAME"
add equipmentgroup
add equipment entry "STATS_ENTRY_NAME"
...
```

## Keywords

| Keyword | Purpose |
|---------|---------|
| `new equipment "NAME"` | Starts a new equipment set |
| `add initialweaponset "TYPE"` | Sets starting weapon set (Melee or Ranged) |
| `add equipmentgroup` | Starts a new equipment slot group |
| `add equipment entry "NAME"` | Adds item to the current group (references Armor/Weapon/Object stats entry) |

## Example

```
new equipment "EQP_CC_Barbarian"
add initialweaponset "Melee"
add equipmentgroup
add equipment entry "WPN_Greataxe"
add equipmentgroup
add equipment entry "OBJ_Potion_Healing"
add equipmentgroup
add equipment entry "OBJ_Potion_Healing"
add equipmentgroup
add equipment entry "OBJ_Scroll_Revivify"
add equipmentgroup
add equipment entry "ARM_Shoes_Barbarian"
add equipmentgroup
add equipment entry "ARM_Barbarian"
add equipmentgroup
add equipment entry "WPN_Handaxe"
add equipmentgroup
add equipment entry "WPN_Handaxe"
add equipmentgroup
add equipment entry "OBJ_Keychain"
add equipmentgroup
add equipment entry "OBJ_Bag_AlchemyPouch"
add equipmentgroup
add equipment entry "ARM_Camp_Body"
add equipmentgroup
add equipment entry "ARM_Camp_Shoes"

## Cross-References

| From | To | Via |
|------|----|----|  
| `add equipment entry "NAME"` | Weapon/Armor/Object stats | Entry name match (case-sensitive) |
| `ClassDescription.ClassEquipment` (LSX) | Equipment.txt | Equipment set name |
| `Character stats` | Equipment.txt | Set name from `ClassEquipment` field |

## Caveats

- **Entry name matching**: Equipment entry names reference stats entries by exact name (case-sensitive). A mismatch results in the item not being granted.
- **Equipment group = slot**: Each `add equipmentgroup` / `add equipment entry` pair represents one slot. Multiple entries in the same group are NOT alternatives — only the last entry is used.
- **Initial weapon set**: `"Melee"` or `"Ranged"` determines which weapon set is active on spawn. Characters with both melee and ranged weapons should include both sets.
- **No inheritance**: Equipment files don't support `using`. To modify starter equipment, redefine the entire set.
add equipmentgroup
add equipment entry "OBJ_Backpack_CampSupplies"
```

## Notes

- Equipment groups are ordered — each group corresponds to a slot in order of assignment
- Entry names reference stats entries from `Armor.txt`, `Weapon.txt`, or `Object.txt`
- Empty equipment sets (e.g., `_PC_Equipment`) serve as base/parent references
- The `initialweaponset` determines which weapon set is active by default
