# Object

> **Type identifier**: `Object`
> **Source file**: `Stats/Generated/Data/Object.txt`
> **Modifier definition**: [Modifiers.md](../formats/Modifiers.md#object) (47 fields)

---

## Overview

Defines consumable items, scrolls, potions, keys, quest items, throwables, camp supplies, and miscellaneous objects. Covers everything that isn't a weapon, armor, or character. Objects share many fields with Armor/Weapon (resistances, value, rarity) but add consumable-specific fields like `SupplyValue`, `AddToBottomBar`, and `ItemUseType`.

## Entry Format

```
new entry "OBJ_Scroll_Revivify"
type "Object"
using "OBJ_Scroll_Base"
data "RootTemplate" "1a3e0e3c-..."
data "MinLevel" "5"
data "Weight" "0.05"
data "ValueLevel" "5"
data "ValueUUID" "91696f37-..."
data "Rarity" "Uncommon"
data "UseCosts" "ActionPoint:1"
data "ObjectCategory" "MagicScroll_3"
data "InventoryTab" "Magical"
```

## Pack Distribution

| Pack | Notes |
|------|-------|
| Shared | Primary — scrolls, potions, consumables, gems, junk |
| SharedDev | Development entries |

---

## Form Reference — All Fields

> Complete field table for form/editor construction. 47 fields defined in [Modifiers.md](../formats/Modifiers.md#object). ✓ = observed in vanilla data.

| Field | Type | Observed |
|-------|------|:--------:|
| `AcidResistance` | ResistanceFlags | ✓ |
| `AddToBottomBar` | YesNo | ✓ |
| `Armor` | ConstantInt | ✓ |
| `BludgeoningResistance` | ResistanceFlags | ✓ |
| `ColdResistance` | ResistanceFlags | ✓ |
| `ComboCategory` | FixedString | ✓ |
| `DarkvisionRange` | ConstantInt | ✓ |
| `DefaultBoosts` | FixedString | ✓ |
| `FallingHitEffect` | FixedString | ✓ |
| `FallingLandEffect` | FixedString | ✓ |
| `FireResistance` | ResistanceFlags | ✓ |
| `Flags` | AttributeFlags | ✓ |
| `ForceResistance` | ResistanceFlags | ✓ |
| `FOV` | ConstantInt | ✓ |
| `GameSize` | FixedString | ✓ |
| `IgnoredByAI` | YesNo | |
| `InventoryTab` | InventoryTabs | ✓ |
| `ItemUseType` | ItemUseTypes | ✓ |
| `Level` | ConstantInt | ✓ |
| `LightningResistance` | ResistanceFlags | ✓ |
| `MaxAmount` | ConstantInt | ✓ |
| `MaxLevel` | ConstantInt | |
| `MinAmount` | ConstantInt | ✓ |
| `MinimumDetectionRange` | ConstantInt | ✓ |
| `MinLevel` | ConstantInt | ✓ |
| `NecroticResistance` | ResistanceFlags | ✓ |
| `ObjectCategory` | FixedString | ✓ |
| `PassivesOnEquip` | FixedString | ✓ |
| `PersonalStatusImmunities` | StatusIDs | ✓ |
| `PiercingResistance` | ResistanceFlags | ✓ |
| `PoisonResistance` | ResistanceFlags | ✓ |
| `Priority` | ConstantInt | ✓ |
| `PsychicResistance` | ResistanceFlags | ✓ |
| `RadiantResistance` | ResistanceFlags | ✓ |
| `Rarity` | Rarity | ✓ |
| `Requirements` | Requirements | |
| `RootTemplate` | FixedString | ✓ |
| `Sight` | ConstantInt | ✓ |
| `SlashingResistance` | ResistanceFlags | ✓ |
| `SoundSize` | FixedString | ✓ |
| `StatusInInventory` | FixedString | ✓ |
| `SupplyValue` | ConstantInt | ✓ |
| `ThunderResistance` | ResistanceFlags | ✓ |
| `Unique` | ConstantInt | ✓ |
| `UseConditions` | Conditions | ✓ |
| `UseCosts` | FixedString | ✓ |
| `ValueLevel` | ConstantInt | ✓ |
| `ValueOverride` | ConstantInt | ✓ |
| `ValueRounding` | ConstantInt | ✓ |
| `ValueScale` | ConstantFloat | ✓ |
| `ValueUUID` | Guid | ✓ |
| `VerticalFOV` | ConstantInt | |
| `Vitality` | ConstantInt | ✓ |
| `Weight` | ConstantFloat | ✓ |

### Boost Fields & Observed Boosts

| Boost Field | Purpose |
|-------------|--------|
| `DefaultBoosts` | Default boosts for the object |

**Boosts used in vanilla (5):** `CriticalHit` · `DamageReduction` · `IgnoreFallDamage` · `Invulnerable` · `Tag`

### Functor Fields & Observed Functors

None — Object does not have functor-accepting fields.

---

## Complete Field Reference

### Combat Stats

#### `Armor`
- **Type**: ConstantInt
- **Values**: `"0"`
- **Notes**: Object AC. Almost always `"0"` for consumables. Only relevant for destroyable objects placed in the world.

#### `Vitality`
- **Type**: ConstantInt
- **Values**: `"-1"` (indestructible), `"1"` (fragile), `"10"`, `"24"`, `"50"`, `"100"` (durable)
- **Notes**: Hit points. `"-1"` = cannot be destroyed. Higher values for objects meant to survive combat (barrels, crates).

### Resistances

All resistance fields use the **ResistanceFlags** enum from [ValueLists](../formats/ValueLists.md).

Valid values: `"Resistant"`, `"Immune"`, `"Vulnerable"`, `"None"`, `""` (empty = default)

| Field | Damage Type | Examples |
|-------|-------------|---------|
| `AcidResistance` | Acid | `"Immune"`, `"Resistant"`, `"Vulnerable"` |
| `BludgeoningResistance` | Bludgeoning | `"Immune"`, `"Vulnerable"`, `"Resistant"` |
| `ColdResistance` | Cold | `"Immune"` |
| `FireResistance` | Fire | `"Immune"`, `"Vulnerable"`, `"Resistant"` |
| `ForceResistance` | Force | `"Immune"`, `"Vulnerable"` |
| `LightningResistance` | Lightning | `"Immune"`, `"Resistant"` |
| `NecroticResistance` | Necrotic | `"Immune"`, `"Resistant"` |
| `PiercingResistance` | Piercing | `"Resistant"`, `"Immune"`, `"Vulnerable"` |
| `PoisonResistance` | Poison | `"Immune"`, `"Vulnerable"` |
| `PsychicResistance` | Psychic | `"Immune"` |
| `RadiantResistance` | Radiant | `"Resistant"`, `"Immune"` |
| `SlashingResistance` | Slashing | `"Immune"`, `"Vulnerable"`, `"Resistant"` |
| `ThunderResistance` | Thunder | `"Immune"`, `"None"` |

**Notes**: Resistances on objects determine how they react when caught in area effects. Explosive barrels are typically Vulnerable to Fire and Immune to Poison. `"None"` explicitly clears inherited resistance.

### Consumable Properties

#### `AddToBottomBar`
- **Type**: YesNo
- **Values**: `"Yes"`, `""` (absent = No)
- **Notes**: Whether the item appears in the bottom hotbar for quick access. Set on frequently-used consumables (potions, scrolls).

#### `ItemUseType`
- **Type**: ItemUseTypes (enum from [ValueLists](../formats/ValueLists.md))
- **Values**: `"None"`, `"Common"`
- **Notes**: Classifies item use behavior. `"Common"` for standard consumables, `"None"` for non-usable objects.

#### `SupplyValue`
- **Type**: ConstantInt
- **Values**: `"0"`
- **Notes**: Camp supply value. How many camp supply points this item provides when added to the supply chest. `"0"` for non-food items.

#### `IgnoredByAI`
- **Type**: YesNo
- **Notes**: Whether the AI ignores this object for targeting/pickup. Not observed in vanilla Object data.

### Identity & Template

#### `RootTemplate`
- **Type**: FixedString
- **Values**: `"a1645f21-4934-4225-882f-b1e002874782"` (UUID format)
- **Notes**: UUID linking to a GameObjects template in `RootTemplates/_merged.lsx`. Defines the item's visual model, icon, and physics.

#### `Rarity`
- **Type**: Rarity (enum from [ValueLists](../formats/ValueLists.md))
- **Values**: `"Uncommon"`, `"Rare"`
- **Notes**: Absent = Common. Most consumables are Common. Higher-tier scrolls and special items may be Uncommon or Rare.

#### `Unique`
- **Type**: ConstantInt
- **Notes**: Boolean (0/1). Marks unique/named objects. Not observed in vanilla Object data.

#### `ObjectCategory`
- **Type**: FixedString
- **Values**: `"JunkArtificial"`, `"JunkBio"`, `"PreciousGem"`, `"PreciousGem_2"` through `"PreciousGem_7"`, `"FishingRod"`, `"Luxury"`, `"MagicScroll"`, `"MagicScroll_2"`, `"MagicScroll_3"`, `"MagicScroll_Necro_3"`, `"MagicScroll_Illusion"`, `"MagicScroll_Utility"`
- **Notes**: Category for treasure table lookup in `TreasureTable.txt`. Numbered suffixes (e.g., `PreciousGem_2`) represent tier/rarity within the category. `JunkArtificial`/`JunkBio` for vendorable junk items.

#### `ComboCategory`
- **Type**: FixedString
- **Values**: `"ConstructPart"`
- **Notes**: Crafting combination category for `ItemCombos.txt`. Rarely used on objects.

#### `Priority`
- **Type**: ConstantInt
- **Values**: `"1"`
- **Notes**: Resolution priority. Rarely set.

### Inventory

#### `InventoryTab`
- **Type**: InventoryTabs (enum from [ValueLists](../formats/ValueLists.md))
- **Values**: `"Auto"`, `"Misc"`, `"Magical"`
- **Notes**: Inventory tab assignment. `"Auto"` lets the game decide based on object type.

#### `MinAmount` / `MaxAmount`
- **Type**: ConstantInt
- **Values**: `"1"`
- **Notes**: Stack limits. Most objects use `"1"`.

### Value & Pricing

#### `ValueUUID`
- **Type**: Guid
- **Values**: `"91696f37-5a03-4f10-b636-2e5e2096a594"`
- **Notes**: UUID referencing a value/pricing table.

#### `ValueLevel`
- **Type**: ConstantInt
- **Values**: `"1"`, `"2"`, `"3"`, `"5"`, `"8"`, `"10"`
- **Notes**: Value tier. Higher = more expensive. Scroll value levels roughly correspond to spell level.

#### `ValueScale`
- **Type**: ConstantFloat
- **Values**: `"0.9"`, `"1"`, `"1.1"`, `"1.2"`
- **Notes**: Price multiplier. Values near 1.0; slight variations for balancing.

#### `ValueOverride`
- **Type**: ConstantInt
- **Values**: `"1"` (nearly worthless), `"10"`, `""` (absent = use formula)
- **Notes**: Absolute gold value override. Small values for junk items.

#### `ValueRounding`
- **Type**: ConstantInt
- **Values**: `"0"`, `"1"`
- **Notes**: Value rounding method.

### Level

#### `Level`
- **Type**: ConstantInt
- **Notes**: Object power level. Not observed in vanilla — uses `MinLevel` instead.

#### `MinLevel`
- **Type**: ConstantInt
- **Values**: `"1"`, `"5"`, `"7"`, `"8"`, `"9"`
- **Notes**: Minimum level for availability. Higher-level scrolls/potions use higher MinLevel values.

#### `MaxLevel`
- **Type**: ConstantInt
- **Notes**: Maximum level for scaling. Not observed in vanilla Object data.

### Weight

#### `Weight`
- **Type**: ConstantFloat
- **Values**: `"0"` (weightless keys), `"0.05"` (scrolls), `"0.1"` (potions), `"1"` (tools), `"10"` (heavy objects), `"50"` (barrels), `"100"`, `"250"` (very heavy)
- **Notes**: Weight in game units. Affects carrying capacity and throw distance. Scrolls are very light (0.05), barrels are heavy (50+).

### Status & Conditions

#### `UseConditions`
- **Type**: Conditions
- **Values**: `"not IsSummon()"`
- **Notes**: Boolean condition restricting who can use the item. `not IsSummon()` prevents summoned creatures from using consumables.

#### `UseCosts`
- **Type**: FixedString
- **Values**: `"ActionPoint:1"`, `"BonusActionPoint:1"`, `"Movement:6"`, `""` (empty)
- **Notes**: Resource cost to use the item. Format: `ResourceType:Amount`. Most potions cost a Bonus Action, scrolls cost an Action. `Movement:6` for items requiring physical effort.

#### `StatusInInventory`
- **Type**: FixedString
- **Values**: `"HAS_SHOVEL"`
- **Notes**: Status applied while item is in inventory. Used for items that have passive effects when carried (e.g., shovel enables digging).

#### `PersonalStatusImmunities`
- **Type**: StatusIDs
- **Values**: `"SG_Condition;BLEEDING;MAG_ATTACK_DEBUFF"`, `"SG_Condition;BLEEDING;BURNING;FLAMING_SPHERE;WILD_MAGIC_BURNING;MAG_ATTACK_DEBUFF"`
- **Notes**: Semicolon-separated status immunities. Used on objects that should be immune to certain conditions (e.g., a barrel immune to bleeding).

#### `DefaultBoosts`
- **Type**: FixedString
- **Values**: `"CriticalHit(AttackTarget,Failure,Never);CriticalHit(AttackTarget,Success,Never)"`
- **Notes**: Default boost expressions. The example prevents critical hits on/from the object.

#### `PassivesOnEquip`
- **Type**: FixedString
- **Notes**: Passive abilities granted when equipped. Not observed in vanilla Object data.

### Flags & Physical

#### `Flags`
- **Type**: AttributeFlags (flags enum from [ValueLists](../formats/ValueLists.md))
- **Values**: `"Grounded"`, `"Torch;Grounded;InvulnerableAndInteractive"`, `"Grounded;Floating;IgnoreClouds;ThrownImmunity;InvulnerableAndInteractive"`
- **Notes**: Semicolon-separated. `Grounded` = can't be pushed/thrown, `InvulnerableAndInteractive` = can't be destroyed but can be interacted with, `ThrownImmunity` = can't be thrown, `Floating` = hovers, `IgnoreClouds` = ignores cloud effects.

#### `GameSize`
- **Type**: FixedString
- **Values**: `"Tiny"`, `"Small"`, `"Medium"`, `"Large"`
- **Notes**: Object size category. Affects throw mechanics and spatial interactions.

#### `SoundSize`
- **Type**: FixedString
- **Values**: `"Tiny"`, `"Medium"`, `"Large"`, `"Huge"`
- **Notes**: Sound category for impact sounds.

### Perception (Inherited from shared modifier set)

#### `Sight`
- **Type**: ConstantInt
- **Values**: `"0"`
- **Notes**: Sight range. Always `"0"` for objects — objects don't see.

#### `FOV` / `VerticalFOV`
- **Type**: ConstantInt
- **Values**: `"0"`
- **Notes**: Field of view. Always `"0"` for objects.

#### `DarkvisionRange`
- **Type**: ConstantInt
- **Values**: `"0"`
- **Notes**: Darkvision range. Always `"0"` for objects.

#### `MinimumDetectionRange`
- **Type**: ConstantInt
- **Values**: `"0"`
- **Notes**: Minimum detection range. Always `"0"` for objects.

### VFX

#### `FallingHitEffect`
- **Type**: FixedString
- **Values**: `"VFX_Combat_Bludgeoning_Damage_Critical_01"`
- **Notes**: VFX on hitting something when falling/thrown.

#### `FallingLandEffect`
- **Type**: FixedString
- **Values**: `"VFX_Combat_Force_Land_01"`
- **Notes**: VFX on landing after being thrown.

### Unobserved Fields

These fields are defined in Modifiers.txt but not observed in vanilla Object data:

- **`Requirements`** — Equipment requirements (objects aren't "equipped" in the traditional sense)
- **`Level`** — Uses `MinLevel` instead

---

## Cross-References

| From | To | Via |
|------|----|----|
| Object.RootTemplate | GameObjects | UUID → `MapKey` in RootTemplates |
| Object.ValueUUID | Value tables | Pricing lookup |
| Object.ObjectCategory | TreasureTable | Loot table categories |
| Object.ComboCategory | ItemCombos | Crafting category |
| Object.StatusInInventory | StatusData | Status name reference |
| Object.PersonalStatusImmunities | StatusData | Status/group IDs |
| Object.DefaultBoosts | Boosts reference | [functors-boosts.md](../reference/functors-boosts.md) |
| Object (Stats attribute) | GameObjects | GameObjects.Stats references entry name |

## Caveats & Gotchas

- **Vitality -1**: Setting Vitality to `"-1"` makes an object indestructible. This is different from using `InvulnerableAndInteractive` flag (which also prevents damage but keeps interaction).
- **Perception fields**: Sight, FOV, DarkvisionRange, MinimumDetectionRange are all `"0"` on objects. They exist because object shares the modifier set with Character/Weapon, not because objects can see.
- **UseCosts format**: Uses `ResourceType:Amount` — note the colon separator, not equals. `Movement:6` costs 6m of movement, `ActionPoint:1` costs 1 action.
- **ObjectCategory tiers**: Numbered suffixes (e.g., `PreciousGem_2`) represent value tiers within the same category. Higher numbers ≠ higher rarity; they map to different TreasureTable weight entries.
- **AddToBottomBar**: Only set on items that should be easily accessible during combat. Don't set on quest items or junk.
- **Conditional boost scope**: `IF(Condition):Boost1(args);Boost2(args)` — the `IF()` only applies to `Boost1`. Repeat for each: `IF(Condition):Boost1(args);IF(Condition):Boost2(args)`.
- **Cross-format name matching**: `GameObjects.Stats` references Object entry names and is **case-sensitive**. Mismatches fail silently.
- **Inheritance load order**: `using "ParentObject"` requires the parent in the same file or an earlier-loaded file. Forward references fail silently.
- **SupplyValue for camp supplies**: Items usable as camp supplies need a positive `SupplyValue`. This determines their contribution toward the long rest supply total.
- **Consumable patterns**: Scrolls typically use `Unique` rarity with `UseCosts "ActionPoint:1"`. Potions use `UseCosts "BonusActionPoint:1"`. Thrown items may add `Movement:N` costs.
- **Resistance fields**: `Resistances` on objects follow the same syntax as Character (e.g., `"Fire,Immune;Bludgeoning,Resistant"`). Used for destructible objects like barrels.

---

## Scripting & Runtime Notes

### Script Extender (SE) Lua

```lua
-- Read object stats
local stat = Ext.Stats.Get("OBJ_Potion_Healing")
local useCosts = stat.UseCosts

-- Modify at runtime (MUST sync after)
stat.UseCosts = "BonusActionPoint:1"
Ext.Stats.Sync("OBJ_Potion_Healing")

-- Access via entity
local entity = Ext.Entity.Get(itemGuid)
local statsName = entity.Stats.Name  -- e.g., "OBJ_Potion_Healing"
```

> **CRITICAL:** `Ext.Stats.Sync()` is mandatory after any runtime change — without it modifications are invisible.

### Osiris Events

| Event | Signature | Relevance |
|-------|-----------|----------|
| `StatusApplied` | `(obj, status, causee, storyId)` | Fires when object's consumption applies a status |
| `CastedSpell` | `(character, spell)` | Scrolls cast spells on use |
