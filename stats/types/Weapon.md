# Weapon

> **Type identifier**: `Weapon`
> **Source file**: `Stats/Generated/Data/Weapon.txt`
> **Modifier definition**: [Modifiers.md](../formats/Modifiers.md#weapon) (60 fields)

---

## Overview

Defines weapon stat blocks — damage, properties, proficiency requirements, enchantments, and granted abilities. Referenced by GameObjects templates via the `Stats` attribute. Supports inheritance via `using`.

## Entry Format

```
new entry "WPN_Longsword"
type "Weapon"
using "_BaseLongsword"
data "RootTemplate" "569b0f3d-abcd-4b01-aaf0-979091288163"
data "Damage" "1d8"
data "VersatileDamage" "1d10"
data "Damage Type" "Slashing"
data "WeaponRange" "150"
data "Weapon Group" "MartialMeleeWeapon"
data "Weapon Properties" "Versatile;Melee;Dippable"
data "Proficiency Group" "Longswords;MartialWeapons"
data "Slot" "Melee Main Weapon"
data "Weight" "1.35"
data "ValueUUID" "91696f37-5a03-4f10-b636-2e5e2096a594"
data "BoostsOnEquipMainHand" "UnlockSpell(Zone_Cleave);UnlockSpell(Target_Slash_New)"
```

## Pack Distribution

| Pack | Size | Notes |
|------|------|-------|
| Shared | 61 KB | Core weapon definitions, base templates |
| GustavDev | 63 KB | Module-specific unique/named weapons |
| Gustav | 23 KB | Campaign-specific weapons |
| SharedDev | 15 KB | Development weapons |
| Honour | 6 KB | Honour-mode overrides |
| GustavX | 1 KB | DLC weapons |

---

## Form Reference — All Fields

> Complete field table for form/editor construction. 60 fields defined in [Modifiers.md](../formats/Modifiers.md#weapon). ✓ = observed in vanilla data.

| Field | Type | Observed |
|-------|------|:--------:|
| `Boosts` | FixedString | ✓ |
| `BoostsOnEquipMainHand` | FixedString | ✓ |
| `BoostsOnEquipOffHand` | FixedString | |
| `Charges` | ConstantInt | |
| `ColorPresetResource` | FixedString | |
| `ComboCategory` | FixedString | |
| `Damage` | FixedString | ✓ |
| `Damage Range` | ConstantInt | ✓ |
| `Damage Type` | Damage Type | ✓ |
| `DefaultBoosts` | FixedString | ✓ |
| `Durability` | ConstantInt | |
| `DurabilityDegradeSpeed` | Qualifier | |
| `ExtraProperties` | FixedString | |
| `FallingHitEffect` | FixedString | |
| `FallingLandEffect` | FixedString | |
| `Flags` | AttributeFlags | ✓ |
| `GameSize` | FixedString | ✓ |
| `IgnoreVisionBlock` | YesNo | |
| `InventoryTab` | InventoryTabs | ✓ |
| `ItemColor` | FixedString | ✓ |
| `ItemGroup` | FixedString | ✓ |
| `Level` | ConstantInt | ✓ |
| `MaxAmount` | ConstantInt | ✓ |
| `MaxCharges` | ConstantInt | |
| `MaxLevel` | ConstantInt | |
| `MinAmount` | ConstantInt | ✓ |
| `MinLevel` | ConstantInt | |
| `NeedsIdentification` | YesNo | |
| `ObjectCategory` | FixedString | ✓ |
| `PassivesMainHand` | FixedString | ✓ |
| `PassivesOffHand` | FixedString | |
| `PassivesOnEquip` | FixedString | ✓ |
| `PersonalStatusImmunities` | StatusIDs | ✓ |
| `Priority` | ConstantInt | ✓ |
| `Proficiency Group` | ProficiencyGroupFlags | ✓ |
| `Projectile` | FixedString | ✓ |
| `Rarity` | Rarity | ✓ |
| `Requirements` | Requirements | |
| `RootTemplate` | FixedString | ✓ |
| `Slot` | Itemslot | ✓ |
| `SoundSize` | FixedString | |
| `Spells` | FixedString | |
| `StatusInInventory` | FixedString | |
| `StatusOnEquip` | FixedString | ✓ |
| `SupplyValue` | ConstantInt | ✓ |
| `Tags` | FixedString | |
| `Unique` | ConstantInt | ✓ |
| `UniqueWeaponSoundSwitch` | FixedString | |
| `UseConditions` | Conditions | ✓ |
| `UseCosts` | FixedString | ✓ |
| `ValueLevel` | ConstantInt | ✓ |
| `ValueOverride` | ConstantInt | ✓ |
| `ValueRounding` | ConstantInt | ✓ |
| `ValueScale` | ConstantFloat | ✓ |
| `ValueUUID` | Guid | ✓ |
| `VersatileDamage` | FixedString | ✓ |
| `Weapon Group` | Weapon Group | ✓ |
| `Weapon Properties` | WeaponFlags | ✓ |
| `WeaponFunctors` | StatsFunctors | ✓ |
| `WeaponRange` | ConstantInt | ✓ |
| `Weight` | ConstantFloat | ✓ |

### Boost Fields & Observed Boosts

| Boost Field | Purpose |
|-------------|---------|
| `Boosts` | General boosts (always active) |
| `BoostsOnEquipMainHand` | Boosts when equipped in main hand |
| `DefaultBoosts` | Default boosts applied automatically |

**Boosts used in vanilla (10):** `CannotBeDisarmed` · `HiddenDuringCinematic` · `IgnoreResistance` · `Proficiency` · `Resistance` · `Skill` · `UnlockSpell` · `WeaponDamage` · `WeaponEnchantment` · `WeaponProperty`

### Functor Fields & Observed Functors

| Functor Field | Purpose |
|---------------|---------|
| `WeaponFunctors` | Functors executed on weapon hit |

**Functors used in vanilla (2):** `ApplyStatus` · `SurfaceChange`

---

## Complete Field Reference

### Damage & Combat

#### `Damage`
- **Type**: FixedString
- **Values**: Dice notation — `"1d4"`, `"1d6"`, `"1d8"`, `"1d10"`, `"1d12"`, `"2d6"`, `"4d6"`, `"5d6"`
- **Notes**: Base damage roll expression. Always uses `NdM` dice notation. Magical variants may have higher dice (e.g., `"4d6"` on legendary weapons). Inherited from base entries and commonly overridden.

#### `Damage Type`
- **Type**: Damage Type (enum from [ValueLists](../formats/ValueLists.md))
- **Values**: `"Slashing"`, `"Piercing"`, `"Bludgeoning"`, `"Necrotic"`, `"Fire"`, `"Radiant"`, `"Lightning"`, `"Psychic"`, `"Thunder"`, `"Force"`, `"Acid"`, `"Cold"`, `"Poison"`
- **Notes**: Physical weapons use Slashing/Piercing/Bludgeoning. Magical weapons may use any damage type.

#### `Damage Range`
- **Type**: ConstantInt
- **Values**: `"1500"`, `"1800"`, `"3000"`
- **Notes**: Maximum range for projectile damage falloff (game units, centimeters). Only relevant for ranged weapons.

#### `VersatileDamage`
- **Type**: FixedString
- **Values**: `"1d10"`, `"1d8"`
- **Notes**: Two-handed damage dice for Versatile weapons. Always higher than base `Damage`. Only set on weapons with `Versatile` in `Weapon Properties`.

#### `WeaponRange`
- **Type**: ConstantInt
- **Values**: `"150"` (melee), `"220"` (reach/whip), `"250"` (extended reach), `"500"` (hand crossbow), `"1500"` (shortbow), `"1800"` (longbow/heavy crossbow)
- **Notes**: Attack range in game units (centimeters). Standard melee = 150, Reach weapons = 220-250, Ranged = 500-1800.

### Weapon Classification

#### `Weapon Group`
- **Type**: Weapon Group (enum from [ValueLists](../formats/ValueLists.md))
- **Values**: `"SimpleMeleeWeapon"`, `"SimpleRangedWeapon"`, `"MartialMeleeWeapon"`, `"MartialRangedWeapon"`
- **Notes**: Determines weapon category for proficiency checks and class features.

#### `Weapon Properties`
- **Type**: WeaponFlags (flags enum from [ValueLists](../formats/ValueLists.md))
- **Values**: Semicolon-separated flags — `"Light;Melee;Dippable"`, `"Versatile;Melee;Dippable;Magical"`, `"Heavy;Reach;Twohanded;Melee;Dippable"`, `"Ammunition;Loading;Twohanded;Heavy"`, `"Thrown;Light;Melee;Dippable;Finesse"`
- **Valid flags**: `Light`, `Heavy`, `Reach`, `Twohanded`, `Finesse`, `Thrown`, `Ammunition`, `Loading`, `Melee`, `Dippable`, `Versatile`, `Unstowable`, `Magical`, `NoDualWield`, `NotSheathable`
- **Notes**: Multiple flags separated by `;`. `Melee` and `Dippable` are on all melee weapons. `Magical` added to enchanted weapons (prevents resistance to non-magical damage). `Ammunition` and `Loading` on crossbows.

#### `Proficiency Group`
- **Type**: ProficiencyGroupFlags (flags enum from [ValueLists](../formats/ValueLists.md))
- **Values**: `"Daggers;SimpleWeapons"`, `"Battleaxes;MartialWeapons"`, `"Longswords;MartialWeapons"`, `"Longbows;MartialWeapons"`, `"HandCrossbows;MartialWeapons"`, `"Maces;SimpleWeapons"`
- **Notes**: Semicolon-separated. First entry is weapon-specific proficiency, second is the general category. Weapon-specific examples: `Daggers`, `Longswords`, `Battleaxes`, `Handaxes`, `Longbows`, `Shortbows`, `HeavyCrossbows`, `LightCrossbows`, `HandCrossbows`, `Maces`, `Scimitars`, `Rapiers`, `Greatswords`, etc.

#### `Slot`
- **Type**: Itemslot (enum from [ValueLists](../formats/ValueLists.md))
- **Values**: `"Melee Main Weapon"`, `"Ranged Main Weapon"`, `"Melee Offhand Weapon"`, `"Ranged Offhand Weapon"`
- **Notes**: Determines which equipment slot the weapon occupies. Most weapons use main weapon slot.

### Equipment & Inventory

#### `InventoryTab`
- **Type**: InventoryTabs (enum from [ValueLists](../formats/ValueLists.md))
- **Values**: `"Equipment"`, `"Hidden"`
- **Notes**: Tab assignment in character inventory. `Hidden` used for unarmed/internal weapons that shouldn't show in UI.

#### `ItemGroup`
- **Type**: FixedString
- **Values**: `"Dummy"`, `"MeatCleaver"`, `"Pitchfork"`, `"Torch"`, `""` (empty)
- **Notes**: Groups items for stacking/sorting. References name groups in `ItemProgressionVisuals.txt`. Empty string for most weapons.

#### `Rarity`
- **Type**: Rarity (enum from [ValueLists](../formats/ValueLists.md))
- **Values**: `"Common"`, `"Uncommon"`, `"Rare"`, `"VeryRare"`, `"Legendary"`
- **Notes**: Absent or empty = Common. Affects item border color, value calculation, and loot table weighting.

#### `Unique`
- **Type**: ConstantInt
- **Values**: `"0"`, `"1"`
- **Notes**: Boolean (0/1). Marks the weapon as a named unique item. Unique weapons have hand-crafted stats and cannot be randomly generated by loot tables.

#### `Weight`
- **Type**: ConstantFloat
- **Values**: `"0.225"` (dart), `"0.45"` (dagger), `"0.9"` (shortsword), `"1.35"` (longsword), `"1.8"` (greatsword), `"2.7"` (greataxe), `"4.5"` (heavy crossbow), `"8.1"` (ballista)
- **Notes**: Weight in game units. Affects carry capacity and throw distance. Consistent across same weapon type.

#### `Level`
- **Type**: ConstantInt
- **Values**: `"1"`, `"2"`, `"3"`, `"4"`
- **Notes**: Base weapon power level. Gates availability in loot tables and progression. Level 1 = mundane, higher = more powerful.

#### `MinLevel`
- **Type**: ConstantInt
- **Notes**: Minimum character level required to use/find this weapon. Rarely set on weapons.

#### `MaxLevel`
- **Type**: ConstantInt
- **Notes**: Maximum character level for scaling. Rarely set on weapons.

#### `MinAmount`
- **Type**: ConstantInt
- **Notes**: Minimum drop amount. Inherited from Modifiers. Not observed in vanilla weapon data.

#### `MaxAmount`
- **Type**: ConstantInt
- **Notes**: Maximum stack amount. Not observed in vanilla weapon data (weapons don't stack).

### Value & Pricing

#### `ValueUUID`
- **Type**: Guid
- **Values**: `"91696f37-5a03-4f10-b636-2e5e2096a594"`, `"4cd41c74-9c86-4233-922e-4db5bc750df5"`, `"71191c11-966f-4c19-b4ee-eb36d31c4944"`
- **Notes**: UUID referencing a value/pricing table. Different UUIDs correspond to different base value tiers. Combined with `ValueLevel` and `ValueScale` to calculate final gold value.

#### `ValueLevel`
- **Type**: ConstantInt
- **Values**: `"1"`, `"2"`, `"3"`, `"4"`
- **Notes**: Enchantment tier for value calculation. 1 = +1 weapon, 2 = +2, etc. Used by the pricing formula when `ValueOverride` is not set.

#### `ValueScale`
- **Type**: ConstantFloat
- **Values**: `"0.2"`, `"0.3"`, `"0.5"`, `"1"`
- **Notes**: Multiplier applied to base value. 0.2 = 20% of standard price, 1 = full price.

#### `ValueOverride`
- **Type**: ConstantInt
- **Values**: `"60"`, `"80"`, `"150"`, `"200"`, `"330"`, `"600"`
- **Notes**: Absolute gold value — bypasses `ValueUUID` + `ValueLevel` + `ValueScale` calculation entirely. Used for quest weapons with fixed values.

#### `ValueRounding`
- **Type**: ConstantInt
- **Values**: `"1"`
- **Notes**: Controls value rounding behavior. Only seen as `"1"` in vanilla.

### Template & Identity

#### `RootTemplate`
- **Type**: FixedString
- **Values**: `"a086b825-8f17-4f0e-855b-178f8cdc515a"`, `"569b0f3d-abcd-4b01-aaf0-979091288163"`
- **Notes**: UUID linking to a GameObjects template in `RootTemplates/_merged.lsx`. Defines the weapon's visual model, physics, and icon. Every weapon should have one.

#### `Tags`
- **Type**: FixedString
- **Values**: Semicolon-separated UUIDs — `"d30c1f61-bbda-4656-9077-7fa3c735744e;..."`, `"0ccdc54f-...;1a1a5f4e-..."`
- **Notes**: Tag UUIDs for classification, scripting, and conditional checks. Tags are defined in the Tags region. Not commonly set directly on weapons (usually inherited from templates).

#### `ObjectCategory`
- **Type**: FixedString
- **Values**: `"MagicWeapons"`, `"BookHistoryFactions"`
- **Notes**: Category for loot table assignment via `TreasureTable.txt`. Links weapon to `object category` entries in treasure tables.

#### `ComboCategory`
- **Type**: FixedString
- **Notes**: Crafting combination category for `ItemCombos.txt`. Not commonly used on weapons.

#### `Priority`
- **Type**: ConstantInt
- **Notes**: Resolution priority when multiple entries conflict. Higher = preferred. Not commonly set on weapons.

### Boosts & Enchantments

#### `DefaultBoosts`
- **Type**: FixedString
- **Values**: `"WeaponEnchantment(1);WeaponProperty(Magical)"`, `"WeaponEnchantment(2);WeaponProperty(Magical)"`, `"WeaponProperty(Magical)"`, `"WeaponDamage(1d6, Necrotic)"`
- **Notes**: Semicolon-separated boost expressions always active on the weapon. Most enchanted weapons have `WeaponEnchantment(N)` for +N to attack/damage and `WeaponProperty(Magical)` to bypass non-magical resistance. See [functors-boosts.md](../reference/functors-boosts.md) for full boost syntax.

#### `Boosts`
- **Type**: FixedString
- **Values**: `"UnlockSpell(Target_DEN_Apprentice_DaggerOfShar_Spell)"`, `"Proficiency(Sickles);"`, `"IF(Tagged('APOSTLE_OF_MYRKUL',context.Source)):UnlockSpell(...)"`
- **Notes**: Conditional or static boost expressions. Supports `IF(condition):Boost(...)` syntax for tag-gated or context-conditional boosts. Semicolon-separated. See [functors-boosts.md](../reference/functors-boosts.md).

#### `BoostsOnEquipMainHand`
- **Type**: FixedString
- **Values**: `"UnlockSpell(Zone_Cleave);UnlockSpell(Target_Slash_New);UnlockSpell(Target_CripplingStrike);"`, `"UnlockSpell(Target_ConcussiveSmash)"`, `"UnlockSpell(Projectile_PiercingShot);UnlockSpell(Projectile_MobileShooting)"`
- **Notes**: Boosts applied only when equipped in main hand. Primarily used to grant weapon-specific actions (`UnlockSpell`). Most melee weapons grant Cleave/Slash/etc. based on weapon type. Semicolon-separated. Empty string `""` in overrides to suppress inherited boosts.

#### `BoostsOnEquipOffHand`
- **Type**: FixedString
- **Values**: `""` (most weapons), `"UnlockSpell(...)"`
- **Notes**: Boosts applied only when equipped in off-hand. Rarely used — most off-hand behavior is handled by dual-wield system.

### Passives & Status

#### `PassivesOnEquip`
- **Type**: FixedString
- **Values**: `"CHA_CompassSpear_Passive"`, `"DEN_Apprentice_DaggerOfShar_Passive;MAG_Shadow_BlindImmunity_Ring_Passive"`, `"UNI_Bow_SpellslotRecharge_Passive"`
- **Notes**: Semicolon-separated passive IDs granted while weapon is equipped. References entries in `Passive.txt`. Common on named/unique weapons to grant special abilities.

#### `PassivesMainHand`
- **Type**: FixedString
- **Values**: `"Overwhelm"`, `"MAG_Legendary_Chromatic_Spellslot_Passive"`
- **Notes**: Passive abilities active only when weapon is in main hand. Used for main-hand-specific weapon features.

#### `PassivesOffHand`
- **Type**: FixedString
- **Notes**: Passive abilities active only when weapon is in off-hand. Rarely used in vanilla.

#### `StatusOnEquip`
- **Type**: FixedString
- **Values**: `"MAG_SHA_SHAR_BLESSING_SAVING_THROW_ADVANTAGE_TECHNICAL"`, `"HANDLE_CANNON_OH_RANGED_MH"`
- **Notes**: Status effect applied when weapon is equipped. References a StatusData entry name. Removed when unequipped.

#### `StatusInInventory`
- **Type**: FixedString
- **Notes**: Status effect applied while weapon is in inventory (not equipped). Not observed in vanilla weapon data.

#### `PersonalStatusImmunities`
- **Type**: StatusIDs (semicolon-separated)
- **Values**: `"SILENCED;SG_Condition;BLEEDING"`, `"WEAPON_COATED_WITH_POISON;POISON_BASIC;POISON_SERPENT_VENOM;POISON_WYVERN;DIPPED_FIRE;DIPPED_POISON;DIPPED_WATER"`
- **Notes**: Status effects the wielder becomes immune to. Semicolon-separated StatusData entry names and/or StatusGroup IDs (prefixed `SG_`).

### Functors & Conditions

#### `WeaponFunctors`
- **Type**: StatsFunctors
- **Values**: `"IF(not SavingThrow(Ability.Dexterity, 11)):ApplyStatus(BLINDED, 100, 2)"`, `"GROUND:IF(HasStatus('BURNING',context.Source)):SurfaceChange(Ignite)"`, `"ApplyStatus(THUNDER_GAUNTLETS_DEBUFF,100,1);ApplyStatus(SELF,NO_DISADVANTAGE_FROM_THUNDER_GAUNTLETS,100,1)"`
- **Notes**: Functors triggered on weapon hit. Supports conditional syntax: `IF(condition):Functor(...)`. Context prefixes: `GROUND:` for surface effects. Multiple functors semicolon-separated. See [functors-boosts.md](../reference/functors-boosts.md) for full functor syntax and [functor-contexts.md](../reference/functor-contexts.md) for context prefixes.

#### `UseConditions`
- **Type**: Conditions
- **Values**: `"Tagged('BREWER_CREATURE', context.Source)"`, `"IsNotHumanoid(context.Source)"`, `"Tagged('APOSTLE_OF_MYRKUL', context.Source)"`, `"Tagged('CELESTIAL', context.Source)"`
- **Notes**: Boolean condition expression restricting who can use the weapon. Uses `context.Source` for the wielder. Common functions: `Tagged()`, `IsNotHumanoid()`, `HasStatus()`. If condition evaluates false, weapon cannot be equipped.

#### `UseCosts`
- **Type**: FixedString
- **Values**: `"ActionPoint:1"`
- **Notes**: Resource cost expression for using the weapon's granted ability. Format: `ResourceType:Amount`. Rarely set on weapons directly.

#### `ExtraProperties`
- **Type**: FixedString
- **Notes**: Additional property expressions. Available in Modifiers but not observed in vanilla weapon data.

### Projectile

#### `Projectile`
- **Type**: FixedString
- **Values**: `"ff93ba9c-124c-454e-ac8c-436c136bcef2"`
- **Notes**: UUID referencing a projectile template for ranged weapons. Defines the visual projectile fired (arrow, bolt). Used on bows and crossbows.

### Physical Properties

#### `GameSize`
- **Type**: FixedString
- **Values**: `"Large"`, `"Huge"`
- **Notes**: Overrides the weapon's object size for physics/interaction. Rarely used — only on oversized weapons (e.g., legendary/monster weapons). Engine values: `Tiny`, `Small`, `Medium`, `Large`, `Huge`, `Gargantuan`.

#### `SoundSize`
- **Type**: FixedString
- **Notes**: Sound category for weapon impact/swing sounds. Not observed in vanilla weapon data.

#### `ItemColor`
- **Type**: FixedString
- **Values**: `"DefaultGray"`
- **Notes**: Color preset name referencing entries in `ItemColor.txt`. Controls weapon tint. Rarely set — most weapons use their template's default color.

#### `ColorPresetResource`
- **Type**: FixedString
- **Notes**: UUID for a color preset resource. Not observed in vanilla weapon data.

#### `UniqueWeaponSoundSwitch`
- **Type**: FixedString
- **Notes**: Unique weapon sound identifier for Wwise audio. Used on named weapons with distinctive sound design.

### Durability

#### `Charges`
- **Type**: ConstantInt
- **Notes**: Current charge count. Not observed in vanilla weapon data.

#### `MaxCharges`
- **Type**: ConstantInt
- **Notes**: Maximum charge capacity. Not observed in vanilla weapon data.

#### `Durability`
- **Type**: ConstantInt
- **Notes**: Durability hit points. Not observed in vanilla weapon data.

#### `DurabilityDegradeSpeed`
- **Type**: Qualifier (enum from [ValueLists](../formats/ValueLists.md))
- **Notes**: Speed of durability degradation. Not observed in vanilla weapon data.

### Display

#### `NeedsIdentification`
- **Type**: YesNo
- **Values**: `"Yes"`, `"No"`
- **Notes**: Whether the weapon requires the Identify spell to reveal its properties. Not observed in vanilla weapon data.

#### `IgnoreVisionBlock`
- **Type**: YesNo
- **Values**: `"Yes"`, `"No"`
- **Notes**: Whether the weapon ignores vision-blocking obstacles. Rarely used.

### Flags & Requirements

#### `Flags`
- **Type**: AttributeFlags (flags enum from [ValueLists](../formats/ValueLists.md))
- **Values**: `"Torch;InvulnerableAndInteractive"`
- **Notes**: Semicolon-separated attribute flags. Only observed on WPN_Torch in vanilla. Available flags include `Torch`, `InvulnerableAndInteractive`, `PickedUp`, `Floating`, and others from the AttributeFlags valuelist.

#### `Requirements`
- **Type**: Requirements
- **Notes**: Equipment requirements expression. Not observed in vanilla weapon data (proficiency is handled via `Proficiency Group` instead).

#### `FallingHitEffect`
- **Type**: FixedString
- **Notes**: VFX played when the weapon hits something after falling. Not observed in vanilla weapon data.

#### `FallingLandEffect`
- **Type**: FixedString
- **Notes**: VFX played when the weapon lands after being thrown/dropped. Not observed in vanilla weapon data.

### Supply & Miscellaneous

#### `Spells`
- **Type**: FixedString
- **Notes**: Spells granted while weapon is equipped. Not observed in vanilla weapon data — spell grants use `BoostsOnEquipMainHand` with `UnlockSpell()` instead.

#### `SupplyValue`
- **Type**: ConstantInt
- **Notes**: Camp supply value if the weapon can be used as camp supplies. Not observed in vanilla weapon data.

#### `Shield`
- **Type**: YesNo
- **Notes**: Defined in Modifiers for shared item fields. Not applicable to weapons (shields are Armor type).

---

## Value Syntax Reference

### Boost Expressions

Used in `DefaultBoosts`, `Boosts`, `BoostsOnEquipMainHand`, `BoostsOnEquipOffHand`:

```
WeaponEnchantment(N)           -- +N to attack and damage rolls
WeaponProperty(Magical)        -- Bypasses non-magical damage resistance
WeaponDamage(1d6, Necrotic)    -- Extra damage dice of a type
UnlockSpell(SpellEntryName)    -- Grants a spell while equipped
Proficiency(WeaponType)        -- Grants proficiency
IF(Tagged('TAG',context.Source)):Boost(...)  -- Conditional boost
```

### Functor Expressions

Used in `WeaponFunctors`:

```
ApplyStatus(STATUS_NAME, chance, duration)
IF(not SavingThrow(Ability.Dexterity, DC)):ApplyStatus(...)
GROUND:IF(HasStatus('STATUS',context.Source)):SurfaceChange(Ignite)
DealDamage(1d6, DamageType)
```

### Proficiency Group Values

Weapon-specific: `Battleaxes`, `Daggers`, `Flails`, `Glaives`, `Greataxes`, `Greatswords`, `Halberds`, `Handaxes`, `HandCrossbows`, `HeavyCrossbows`, `Javelins`, `LightCrossbows`, `LightHammers`, `Longbows`, `Longswords`, `Maces`, `Mauls`, `Morningstars`, `Pikes`, `Quarterstaffs`, `Rapiers`, `Scimitars`, `Shortbows`, `Shortswords`, `Sickles`, `Spears`, `Tridents`, `WarPicks`, `Warhammers`, `Whips`

General: `SimpleWeapons`, `MartialWeapons`

---

## Cross-References

| From | To | Via |
|------|----|----|
| Weapon.RootTemplate | GameObjects | UUID → `MapKey` in RootTemplates |
| Weapon.ValueUUID | Value tables | Pricing lookup |
| Weapon.PassivesOnEquip | PassiveData | Entry name reference |
| Weapon.StatusOnEquip | StatusData | Entry name reference |
| Weapon.PersonalStatusImmunities | StatusData | Status/group IDs |
| Weapon.ObjectCategory | TreasureTable | Loot table categories |
| Weapon.Tags | Tags region | UUID references |
| Weapon.Projectile | Projectile templates | UUID reference |
| Weapon.WeaponFunctors | Functors reference | [functors-boosts.md](../reference/functors-boosts.md) |
| Weapon.DefaultBoosts | Boosts reference | [functors-boosts.md](../reference/functors-boosts.md) |

## Caveats & Gotchas

- **Empty string overrides**: Setting a field to `""` in a `using` child suppresses the inherited value. Common for `BoostsOnEquipMainHand` when a unique weapon replaces standard weapon actions.
- **WeaponEnchantment vs WeaponDamage**: `WeaponEnchantment(N)` adds +N to attack AND damage rolls. `WeaponDamage(NdM, Type)` adds only extra damage dice. Both go in `DefaultBoosts`.
- **Proficiency Group order**: Weapon-specific proficiency should come first, general second (e.g., `"Longswords;MartialWeapons"` not `"MartialWeapons;Longswords"`).
- **Weapon Properties vs DefaultBoosts**: `Magical` in `Weapon Properties` and `WeaponProperty(Magical)` in `DefaultBoosts` are both needed — the flag affects game rules while the boost affects the damage type tag.
- **Shield field**: Present in Modifiers.txt but meaningless on Weapon entries — shields use the Armor type.
- **Unobserved fields**: Many fields from Modifiers.txt (`Charges`, `Durability`, `FallingHitEffect`, `FallingLandEffect`, `SoundSize`, `Requirements`, `StatusInInventory`, `NeedsIdentification`, `Spells`) are not used in vanilla weapon data but are available for mods.
- **Conditional boost scope**: `IF(Condition):Boost1(args);Boost2(args)` — the condition only applies to `Boost1`. Repeat the `IF()` for each boost: `IF(Condition):Boost1(args);IF(Condition):Boost2(args)`.
- **DealDamage CoinMultiplier**: In `WeaponFunctors`, if you use `DealDamage` with 5+ args, arg 5 (CoinMultiplier) must be `0` — not empty. `DealDamage(1d6,Fire,,,)` silently fails; use `DealDamage(1d6,Fire,,0)` instead.
- **OnDamage loop risk**: `WeaponFunctors` with `DealDamage` that trigger `OnDamage` passives can loop infinitely. Use `IgnoreOnDamage=true` (arg 8): `DealDamage(1d6,Fire,,0,,true)`.
- **Cross-format name matching**: All name-based references (e.g., `PassivesOnEquip`, `StatusOnEquip`) are **case-sensitive**. `"mypassive"` ≠ `"MyPassive"` — mismatches fail silently.
- **Inheritance load order**: `using "ParentWeapon"` requires the parent to be defined in the same file or an earlier-loaded file. Forward references cause silent inheritance failure.

---

## Scripting & Runtime Notes

### Script Extender (SE) Lua

```lua
-- Read weapon stats
local stat = Ext.Stats.Get("WPN_Longsword_1")
local damage = stat.Damage
local weaponType = stat.WeaponType

-- Modify at runtime (MUST sync after)
stat.DefaultBoosts = "WeaponEnchantment(3);WeaponProperty(Magical)"
Ext.Stats.Sync("WPN_Longsword_1")

-- Access via entity
local entity = Ext.Entity.Get(itemGuid)
local statsName = entity.Stats.Name  -- e.g., "WPN_Longsword_1"
```

> **CRITICAL:** `Ext.Stats.Sync()` is mandatory after any runtime change — without it modifications are invisible.

### Osiris Events

| Event | Signature | Relevance |
|-------|-----------|----------|
| `StatusApplied` | `(obj, status, causee, storyId)` | Fires when `StatusOnEquip` triggers |
| `Died` | `(entity, cause)` | Track kills for weapon-triggered effects |
| `EnteredCombat` | `(character, combatId)` | Combat-only weapon behaviours |


