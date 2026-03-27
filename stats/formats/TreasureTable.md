# TreasureTable.txt

> **Path**: `Stats/Generated/TreasureTable.txt`
> **Format**: `new treasuretable` / `new subtable` / `object category` commands
> **Packs**: Gustav, GustavDev, Shared, SharedDev

## Purpose

Defines loot distribution tables used by containers, NPCs, and encounters. Tables can reference other tables (via `T_` prefix) to create hierarchical loot structures.

## Format

```
treasure itemtypes "Common","Uncommon","Rare","Epic","Legendary","Divine","Unique"

new treasuretable "NAME"
new subtable "AMOUNT_RANGE"
object category "CATEGORY",W_COM,W_UNC,W_RARE,W_EPIC,W_LEG,W_DIV,W_UNI,W_EXT
```

## Keywords

| Keyword | Purpose |
|---------|---------|
| `treasure itemtypes` | Declares the rarity column order (appears once at file start) |
| `new treasuretable "NAME"` | Starts a new loot table |
| `new subtable "RANGE"` | Defines a subtable with amount range (e.g., `"1,1"` or `"2,1;3,1;4,1"`) |
| `object category "NAME",...` | Adds a category with per-rarity weights |

## Subtable Amount Range

The subtable range uses the format `"MIN,COUNT"` or multiple options separated by `;`:

- `"1,1"` — Exactly 1 item
- `"2,1;3,1;4,1"` — Equally likely to drop 2, 3, or 4 items
- `"1,2;2,1"` — 2/3 chance of 1, 1/3 chance of 2

## Object Category Weights

After the category name, 8 comma-separated weight values correspond to the rarity columns:

```
object category "NAME", Common, Uncommon, Rare, Epic, Legendary, Divine, Unique, Extra
```

Weight `0` means that rarity is not possible for this category. Higher values increase relative probability.

## Examples

```
new treasuretable "Gold_Pocket_Random"
new subtable "1,1"
object category "T_Empty",1,0,0,0,0,0,0,0
object category "T_Gold_Meager",1,0,0,0,0,0,0,0
object category "T_Gold_Pocket_Poor",3,0,0,0,0,0,0,0
object category "T_Gold_Pocket_Modest",2,0,0,0,0,0,0,0
object category "T_Gold_Pocket_Normal",1,0,0,0,0,0,0,0
```

## Notes

- Categories prefixed with `T_` reference other treasure tables (recursive)
- Categories prefixed with `I_` reference specific item stats entries
- Plain category names reference `ObjectCategory` values from item stats
- Empty tables (no subtables) serve as null references
- `_TradeItems` is a common base for trader inventories
- The `treasure itemtypes` header appears once at the top and defines the column semantics for all weight arrays

## Cross-References

| From | To | Via |
|------|----|----|  
| `object category "NAME"` | Weapon/Armor/Object `.ObjectCategory` | Category name match |
| `T_` prefix categories | Other treasure tables | Recursive table reference |
| `I_` prefix categories | Specific item stats entries | Direct item reference |
| `ClassDescription.ClassEquipment` (LSX) | Equipment.txt | Equipment set name |

## Caveats

- **Load order**: Treasure tables can be extended by mods. The `using` pattern doesn't apply here — mods add new `new treasuretable` blocks that supplement (not replace) existing tables.
- **Weight semantics**: Weight values are relative within a subtable. A category with weight `3` is 3× more likely than one with weight `1`. Use `0` to exclude a rarity.
- **Recursive depth**: `T_` references can chain deeply. Circular references will cause infinite loops at load.
- **Cross-format name matching**: Category names must match `ObjectCategory` values from stats entries exactly (case-sensitive).
