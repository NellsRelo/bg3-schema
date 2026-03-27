# Stats Reference (.txt Format)

> BG3 Stats files use a key-value `.txt` format with `using` inheritance.
> They live in `Public/{ModName}/Stats/Generated/Data/`.

## Directory Structure

```
stats/
  README.md               ← you are here
  reference/
    inheritance.md       ← using, merge, load order rules
    functors-boosts.md   ← complete functor & boost reference
    functor-contexts.md  ← StatsFunctorContext entity mapping
  types/
    SpellData.md         ← SpellData type fields (185 fields, 9 subtypes)
    StatusData.md        ← StatusData type fields (110 fields, 11 subtypes)
    Weapon.md            ← Weapon type fields (60 fields)
    Character.md         ← Character type fields (58 fields)
    Armor.md             ← Armor type fields (52 fields)
    Object.md            ← Object type fields (47 fields)
    InterruptData.md     ← InterruptData type fields (30 fields)
    PassiveData.md       ← PassiveData type fields (29 fields)
    CriticalHitTypeData.md ← CriticalHitTypeData fields (13 fields)
  formats/
    Modifiers.md         ← Complete field definitions for all 9 types (from Structure/Modifiers.txt)
    ValueLists.md        ← All ~90 enum/valuelist definitions (from Structure/Base/ValueLists.txt)
    Equipment.md         ← Equipment.txt format (starting loadouts)
    SpellSet.md          ← SpellSet.txt format (spell collections)
    ItemCombos.md        ← ItemCombos.txt format (crafting recipes)
    TreasureTable.md     ← TreasureTable.txt format (loot tables)
    ItemTypes.md         ← ItemTypes.txt format (7 rarity definitions)
    ObjectCategoriesItemComboPreviewData.md ← Crafting preview UI data
    SpecialDataFiles.md  ← BloodTypes, ItemColor, Data.txt, XPData, ItemProgressionNames/Visuals
```

## File Format

Stats entries follow this pattern:

```
new entry "EntryName"
type "TypeName"
using "ParentEntry"
data "FieldName" "Value"
```

## Key Concepts

- **Inheritance**: `using "ParentEntry"` — shallow merge, last-write-wins. See [inheritance.md](reference/inheritance.md).
- **Functors**: Action expressions like `ApplyStatus(BURNING,2,1)`. See [functors-boosts.md](reference/functors-boosts.md).
- **Boosts**: Passive stat modifiers like `Proficiency(LightArmor)`. See [functors-boosts.md](reference/functors-boosts.md).
- **Contexts**: Where functors fire — `OnAttack`, `OnCast`, etc. See [functor-contexts.md](reference/functor-contexts.md).
- **Schema definition**: [Modifiers.md](formats/Modifiers.md) — every valid field per type + value types.
- **Enum reference**: [ValueLists.md](formats/ValueLists.md) — all ~90 valuelist/enum definitions.

## Typed Data Files

| Type | Field Count | File Pattern | Primary Use | Doc |
|------|------------|-------------|-------------|-----|
| SpellData | 185 | `Spell_*.txt` | Spell definitions (9 subtypes) | [SpellData.md](types/SpellData.md) |
| StatusData | 110 | `Status_*.txt` | Status effects (11 subtypes) | [StatusData.md](types/StatusData.md) |
| Weapon | 60 | `Weapon.txt` | Weapon stat blocks | [Weapon.md](types/Weapon.md) |
| Character | 58 | `Character.txt` | NPC/creature stat blocks | [Character.md](types/Character.md) |
| Armor | 52 | `Armor.txt` | Armor stat blocks | [Armor.md](types/Armor.md) |
| Object | 47 | `Object.txt` | Consumable/misc items | [Object.md](types/Object.md) |
| InterruptData | 30 | `Interrupt.txt` | Interrupt/reactions | [InterruptData.md](types/InterruptData.md) |
| PassiveData | 29 | `Passive.txt` | Passive features | [PassiveData.md](types/PassiveData.md) |
| CriticalHitTypeData | 13 | `CriticalHitTypes.txt` | Critical hit VFX | [CriticalHitTypeData.md](types/CriticalHitTypeData.md) |

## Non-Typed Format Files

| Format | Content | Doc |
|--------|---------|-----|
| Equipment.txt | Starting equipment loadouts | [Equipment.md](formats/Equipment.md) |
| SpellSet.txt | Spell set collections | [SpellSet.md](formats/SpellSet.md) |
| ItemCombos.txt | Crafting recipe combinations | [ItemCombos.md](formats/ItemCombos.md) |
| TreasureTable.txt | Loot table definitions | [TreasureTable.md](formats/TreasureTable.md) |
| ItemTypes.txt | 7 item rarity definitions | [ItemTypes.md](formats/ItemTypes.md) |
| ObjectCategoriesItemComboPreviewData.txt | Crafting preview data | [ObjectCategoriesItemComboPreviewData.md](formats/ObjectCategoriesItemComboPreviewData.md) |

## Special Data Files

Non-standard formats — see [SpecialDataFiles.md](formats/SpecialDataFiles.md):

| File | Format | Content |
|------|--------|---------|
| BloodTypes.txt | `new bloodtype` + CSV VFX | Blood visual effects per creature type |
| ItemColor.txt | `new itemcolor` + 3 hex | Item dye color palettes |
| Data.txt | `key "NAME","VALUE"` | Game configuration constants |
| XPData.txt | `key "LevelN","VALUE"` | XP thresholds per level |
| ItemProgressionNames.txt | `new namegroup` + `add name` | Localized weapon tier names |
| ItemProgressionVisuals.txt | `new itemgroup` + `add levelgroup/rootgroup/namegroup` | Visual templates per weapon tier |
