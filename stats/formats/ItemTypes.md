# ItemTypes.txt

> **Path**: `Stats/Generated/ItemTypes.txt`
> **Format**: `new itemtype` with comma-separated parameters
> **Packs**: Shared only

## Purpose

Defines the base item rarity types with their display colors, icons, scaling properties, and sort order. Referenced by the `Rarity` field in Armor, Weapon, and Object stat entries.

## Format

```
new itemtype "NAME","HEX_COLOR","ICON","SCALE",RARITY1,RARITY2,ORDER
minlevel LEVEL
new boostgroup dropChance CHANCE
```

## Parameters

| Position | Name | Type | Notes |
|----------|------|------|-------|
| 1 | Name | String | Rarity display name |
| 2 | Color | Hex RGB | Display color (e.g., `"ffffff"`, `"00a900"`) |
| 3 | Icon | String | Icon resource name (empty for Common) |
| 4 | Scale | Float | Scale factor (always `"1.000"`) |
| 5 | Rarity1 | Enum | Primary rarity class |
| 6 | Rarity2 | Enum | Secondary rarity class |
| 7 | Order | Int | Sort order (0=Common, 1=Rare, 2=Uncommon, etc.) |

## Vanilla Definitions

| Name | Color | Icon | Order | Notes |
|------|-------|------|-------|-------|
| Common | `ffffff` (white) | *(none)* | 0 | Default rarity |
| Uncommon | `00a900` (green) | `Item_Magical` | 2 | |
| Rare | `33ccff` (blue) | `Item_Rare` | 1 | |
| Epic | `a346e9` (purple) | `Item_Epic` | 5 | |
| Legendary | `d1007c` (pink) | `Item_Legendary` | 6 | |
| Divine | `ebc808` (gold) | `Item_Divine` | 3 | |
| Unique | `c7a758` (amber) | `Item_Unique` | 4 | |

## Full Example

```
new itemtype "Rare","33ccff","Item_Rare","1.000",Rare,Rare,1
minlevel 1
new boostgroup dropChance 1
```

## Notes

- All vanilla item types have `minlevel 1` and `dropChance 1`
- The `Order` field does **not** correspond to rarity power — it controls sort/display order
- Color values are RGB hex without `#` prefix
- These definitions are the authority for the 7 rarity tiers used throughout the loot system
