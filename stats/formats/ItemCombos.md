# ItemCombos.txt

> **Path**: `Stats/Generated/ItemCombos.txt`
> **Format**: Paired `ItemCombination` + `ItemCombinationResult` entries
> **Packs**: Gustav, GustavDev, Shared, SharedDev

## Purpose

Defines crafting/alchemy recipes — how two items (or an item + category) combine, and what results are produced. Covers dye application, potion brewing, poison coating, and general item crafting.

## Format

Each recipe consists of two paired entries:

### ItemCombination

```
new ItemCombination "NAME"
data "Type 1" "Object"|"Category"
data "Object 1" "STATS_ENTRY_OR_CATEGORY"
data "Transform 1" "Transform"|"Consume"|"Boost"|"None"
data "Type 2" "Object"|"Category"
data "Object 2" "STATS_ENTRY_OR_CATEGORY"
data "Transform 2" "Transform"|"Consume"|"Dye"|"Boost"|"None"
data "DyeColorPresetResource" "UUID"    // optional, for dye recipes
```

### ItemCombinationResult

```
new ItemCombinationResult "NAME_N"
data "ResultAmount 1" "COUNT"
data "Result 1" "STATS_ENTRY_NAME"      // optional, for non-transform results
data "PreviewStatsID" "STATS_ENTRY_NAME" // optional, for UI preview
```

## Fields

### Combination Fields

| Field | Values | Notes |
|-------|--------|-------|
| `Type N` | `Object`, `Category` | Whether the ingredient is a specific item or a category |
| `Object N` | Stats entry name or category name | The ingredient identifier |
| `Transform N` | `Transform`, `Consume`, `Dye`, `Boost`, `None` | What happens to the ingredient |
| `DyeColorPresetResource` | UUID | Color preset for dye recipes |

### Result Fields

| Field | Notes |
|-------|-------|
| `ResultAmount N` | Number of items produced |
| `Result N` | Stats entry name of the result item |
| `PreviewStatsID` | Stats entry for UI preview tooltip |

## Examples

### Object + Object (Poison Crafting)

```
new ItemCombination "OBJ_BeerBarrel_QUEST_DEN_YMCPoison"
data "Type 1" "Object"
data "Object 1" "OBJ_BeerBarrel"
data "Transform 1" "Transform"
data "Type 2" "Object"
data "Object 2" "QUEST_DEN_YMCPoison"
data "Transform 2" "Consume"

new ItemCombinationResult "OBJ_BeerBarrel_QUEST_DEN_YMCPoison_1"
data "ResultAmount 1" "1"
data "Result 1" "OBJ_BeerBarrelPoisoned"
data "PreviewStatsID" "OBJ_BeerBarrelPoisoned"
```

### Object + Category (Dye Application)

```
new ItemCombination "OBJ_Dye_Azure"
data "Type 1" "Object"
data "Object 1" "OBJ_Dye_Azure"
data "Transform 1" "Consume"
data "Type 2" "Category"
data "Object 2" "DyableArmor"
data "Transform 2" "Dye"
data "DyeColorPresetResource" "85fc7553-b1ca-cb0c-600c-2d0a1fb4c06c"

new ItemCombinationResult "OBJ_Dye_Azure_1"
data "ResultAmount 1" "1"
```

## Notes

- Combination and result names follow a convention: result name = combination name + `_N` suffix
- Transform types: `Transform` (item changes form), `Consume` (item destroyed), `Dye` (applies color), `Boost` (item enhanced)
- Categories (e.g., `DyableArmor`) reference `ObjectCategory` values from Armor/Object stats entries
- Dye recipes always include `DyeColorPresetResource` UUID pointing to a color preset

## Cross-References

| From | To | Via |
|------|----|----|  
| `Object N` (Type = Object) | Weapon/Armor/Object stats | Entry name match (case-sensitive) |
| `Object N` (Type = Category) | `ObjectCategory`/`ComboCategory` fields on stats | Category name match |
| `Result N` | Weapon/Armor/Object stats | Entry name match |
| `DyeColorPresetResource` | Color presets | UUID reference |
| Armor/Object `.ComboCategory` | ItemCombos.txt | Category name (e.g., `"DyableArmor"`) |

## Caveats

- **Paired entries required**: Every `ItemCombination` must have a matching `ItemCombinationResult` with the `_N` suffix, or the recipe won't appear.
- **Cross-format name matching**: All item references are case-sensitive name matches. Mismatches cause the recipe to silently fail.
- **Transform types**: `Consume` destroys the ingredient. `Transform` converts it to the result. `Dye` applies color without consuming the target item. `Boost` enhances the target.
- **No inheritance**: ItemCombos don't support `using`. Recipes must be fully defined.
