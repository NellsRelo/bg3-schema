# Armor

> **Type identifier**: `Armor`
> **Source file**: `Stats/Generated/Data/Armor.txt`
> **Modifier definition**: [Modifiers.md](../formats/Modifiers.md#armor) (52 fields)

---

## Overview

Defines armor, shields, clothing, helmets, gloves, boots, amulets, rings, cloaks, and instruments. Despite the name, this type covers all non-weapon equippable items. Referenced by GameObjects templates via the `Stats` attribute. Supports inheritance via `using`.

## Entry Format

```
new entry "ARM_ChainMail"
type "Armor"
using "ARM_ChainMail_Body"
data "RootTemplate" "63cc7723-245d-4b62-b9e6-5a47283cf777"
data "ArmorClass" "16"
data "ArmorType" "ChainMail"
data "Armor Class Ability" "None"
data "Slot" "Breast"
data "Proficiency Group" "HeavyArmor"
data "Boosts" "Disadvantage(Skill,Stealth)"
data "Weight" "25"
data "ValueUUID" "9495e96a-7e7c-4e3a-8d81-51611908908c"
```

## Pack Distribution

| Pack | Notes |
|------|-------|
| Shared | Core armor definitions, base templates |
| SharedDev | Development entries |
| GustavDev | Module-specific unique/named armor |
| Gustav | Campaign-specific armor |
| Honour | Honour-mode overrides |
| GustavX | DLC armor |

---

## Form Reference — All Fields

> Complete field table for form/editor construction. 52 fields defined in [Modifiers.md](../formats/Modifiers.md#armor). ✓ = observed in vanilla data.

| Field | Type | Observed |
|-------|------|:--------:|
| `Ability Modifier Cap` | ConstantInt | ✓ |
| `Armor Class Ability` | Ability | ✓ |
| `ArmorClass` | ConstantInt | ✓ |
| `ArmorType` | ArmorType | ✓ |
| `Boosts` | FixedString | ✓ |
| `Charges` | ConstantInt | ✓ |
| `ColorPresetResource` | FixedString | ✓ |
| `ComboCategory` | FixedString | ✓ |
| `DefaultBoosts` | FixedString | |
| `Durability` | ConstantInt | |
| `DurabilityDegradeSpeed` | Qualifier | |
| `ExtraProperties` | FixedString | |
| `FallingHitEffect` | FixedString | |
| `FallingLandEffect` | FixedString | |
| `Flags` | AttributeFlags | ✓ |
| `GameSize` | FixedString | |
| `InstrumentType` | InstrumentType | ✓ |
| `InventoryTab` | InventoryTabs | ✓ |
| `ItemColor` | FixedString | ✓ |
| `ItemGroup` | FixedString | ✓ |
| `Level` | ConstantInt | ✓ |
| `MaxAmount` | ConstantInt | ✓ |
| `MaxCharges` | ConstantInt | ✓ |
| `MaxLevel` | ConstantInt | |
| `MinAmount` | ConstantInt | ✓ |
| `MinLevel` | ConstantInt | ✓ |
| `NeedsIdentification` | YesNo | |
| `ObjectCategory` | FixedString | ✓ |
| `PassivesOnEquip` | FixedString | ✓ |
| `PersonalStatusImmunities` | StatusIDs | ✓ |
| `Priority` | ConstantInt | ✓ |
| `Proficiency Group` | ProficiencyGroupFlags | ✓ |
| `Rarity` | Rarity | ✓ |
| `Requirements` | Requirements | |
| `RootTemplate` | FixedString | ✓ |
| `Shield` | YesNo | ✓ |
| `Slot` | Itemslot | ✓ |
| `SoundSize` | FixedString | |
| `Spells` | FixedString | |
| `StatusInInventory` | FixedString | |
| `StatusOnEquip` | FixedString | ✓ |
| `Tags` | FixedString | |
| `Unique` | ConstantInt | ✓ |
| `UseConditions` | Conditions | |
| `UseCosts` | FixedString | ✓ |
| `ValueLevel` | ConstantInt | ✓ |
| `ValueOverride` | ConstantInt | ✓ |
| `ValueRounding` | ConstantInt | ✓ |
| `ValueScale` | ConstantFloat | ✓ |
| `ValueUUID` | Guid | ✓ |
| `Weight` | ConstantFloat | ✓ |

### Boost Fields & Observed Boosts

| Boost Field | Purpose |
|-------------|--------|
| `Boosts` | General boosts (always active while equipped) |

**Boosts used in vanilla (13):** `Ability` · `AbilityOverrideMinimum` · `AC` · `ActionResource` · `Advantage` · `CriticalHit` · `Disadvantage` · `ProficiencyBonus` · `Resistance` · `RollBonus` · `Skill` · `Tag` · `UnlockSpell`

### Functor Fields & Observed Functors

None — Armor does not have functor-accepting fields.

---

## Complete Field Reference

### Armor Class & Type

#### `ArmorClass`
- **Type**: ConstantInt
- **Values**: `"10"` (clothing), `"11"` (leather/padded), `"12"` (studded leather), `"13"` (chain shirt/hide), `"14"` (scale mail/breastplate), `"15"` (half plate), `"16"` (ring mail/chain mail), `"17"` (splint), `"18"` (plate)
- **Notes**: Base Armor Class value. Combined with `Armor Class Ability` modifier (capped by `Ability Modifier Cap`). Shields add ArmorClass as a bonus rather than setting it.

#### `ArmorType`
- **Type**: ArmorType (enum from [ValueLists](../formats/ValueLists.md))
- **Values**: `"None"` (clothing/accessories), `"Leather"`, `"Padded"`, `"StuddedLeather"`, `"Hide"`, `"ChainShirt"`, `"ScaleMail"`, `"BreastPlate"`, `"HalfPlate"`, `"RingMail"`, `"ChainMail"`, `"Splint"`, `"Plate"`
- **Notes**: Determines AC calculation rules and which proficiency is required. `None` for non-armor equippables (gloves, boots, amulets, rings, cloaks).

#### `Armor Class Ability`
- **Type**: Ability (enum from [ValueLists](../formats/ValueLists.md))
- **Values**: `"Dexterity"` (light/medium armor), `"None"` (heavy armor), `"Constitution"` (Barbarian Unarmored Defense)
- **Notes**: Which ability modifier adds to AC. `None` = no ability modifier (heavy armor, or items that don't add to AC).

#### `Ability Modifier Cap`
- **Type**: ConstantInt
- **Values**: `"2"` (medium armor), absent (light armor = uncapped), `"0"` (heavy armor = effectively `None`)
- **Notes**: Maximum ability modifier that can be added to AC. Standard D&D 5e: light armor = no cap, medium armor = 2, heavy armor = None (use `Armor Class Ability "None"` instead).

#### `Shield`
- **Type**: YesNo
- **Values**: `"Yes"`, `"No"`
- **Notes**: Whether this item is a shield. Shields add their `ArmorClass` as a bonus to the character's total AC rather than setting it.

### Equipment Slot & Proficiency

#### `Slot`
- **Type**: Itemslot (enum from [ValueLists](../formats/ValueLists.md))
- **Values**: `"Breast"` (body armor), `"Boots"`, `"Gloves"`, `"Helmet"`, `"Amulet"`, `"Ring"`, `"Cloak"`, `"Melee Offhand Weapon"` (shields), `"MusicalInstrument"`, `"Underwear"`, `"VanityBody"`, `"VanityBoots"`, `"Overhead"`
- **Notes**: Equipment slot assignment. Shields use `Melee Offhand Weapon` slot. `VanityBody`/`VanityBoots` for camp cosmetics. `Overhead` for headwear.

#### `Proficiency Group`
- **Type**: ProficiencyGroupFlags (flags enum from [ValueLists](../formats/ValueLists.md))
- **Values**: `"LightArmor"`, `"MediumArmor"`, `"HeavyArmor"`, `"Shields"`
- **Notes**: Required proficiency to equip without penalties. Only set on body armor and shields. Accessories (rings, amulets, cloaks, etc.) have no proficiency requirement.

#### `InventoryTab`
- **Type**: InventoryTabs (enum from [ValueLists](../formats/ValueLists.md))
- **Values**: `"Equipment"`
- **Notes**: Inventory tab assignment. Usually `"Equipment"` for all wearable items.

### Identity & Value

#### `RootTemplate`
- **Type**: FixedString
- **Values**: `"63cc7723-245d-4b62-b9e6-5a47283cf777"`, `"19451420-13f6-444c-a15b-7abb6dde3f91"`
- **Notes**: UUID linking to a GameObjects template in `RootTemplates/_merged.lsx`. Defines the item's visual model, physics, and icon.

#### `Rarity`
- **Type**: Rarity (enum from [ValueLists](../formats/ValueLists.md))
- **Values**: `"Common"`, `"Uncommon"`, `"Rare"`, `"VeryRare"`, `"Legendary"`
- **Notes**: Absent or empty = Common. Affects item border color, value calculation, and loot table weighting.

#### `Unique`
- **Type**: ConstantInt
- **Values**: `"0"`, `"1"`
- **Notes**: Boolean (0/1). Marks item as named/unique. Unique items have hand-crafted stats and cannot be randomly generated.

#### `ObjectCategory`
- **Type**: FixedString
- **Values**: `"ClothingCommon"`, `"ShoesRich"`, `"MagicCleric"`, `"BookScholar"`, `"MagicWeapons"`
- **Notes**: Category for treasure table lookup in `TreasureTable.txt`. Determines which loot pools this armor appears in.

#### `ComboCategory`
- **Type**: FixedString
- **Values**: `"DyableArmor"`
- **Notes**: Crafting combination category for `ItemCombos.txt`. `DyableArmor` marks armor that can be dyed.

#### `Tags`
- **Type**: FixedString
- **Notes**: Semicolon-separated tag UUIDs for classification and scripting. Not observed in vanilla Armor.txt data.

#### `Priority`
- **Type**: ConstantInt
- **Values**: `"1"`
- **Notes**: Resolution priority when multiple entries conflict. Rarely set.

### Value & Pricing

#### `ValueUUID`
- **Type**: Guid
- **Values**: `"9495e96a-7e7c-4e3a-8d81-51611908908c"`, `"4024ce6c-f02d-4d7c-8033-869ada06ef82"`
- **Notes**: UUID referencing a value/pricing table. Combined with `ValueLevel` and `ValueScale` to calculate gold value.

#### `ValueLevel`
- **Type**: ConstantInt
- **Values**: `"1"`, `"5"`, `"10"`
- **Notes**: Value scaling tier. Higher = more expensive. Used in pricing formula when `ValueOverride` is not set.

#### `ValueScale`
- **Type**: ConstantFloat
- **Values**: `"0.8"`, `"1"`, `"1.2"`
- **Notes**: Multiplier on base value. 0.8 = 80% of standard, 1.2 = 120%.

#### `ValueOverride`
- **Type**: ConstantInt
- **Values**: `"0"`, `"5"`, `"25"`
- **Notes**: Absolute gold value — bypasses ValueUUID calculation. `"0"` = worthless.

#### `ValueRounding`
- **Type**: ConstantInt
- **Values**: `"1"`
- **Notes**: Value rounding method. Only `"1"` observed.

### Weight & Level

#### `Weight`
- **Type**: ConstantFloat
- **Values**: `"0.55"` (light gloves), `"5"` (leather armor), `"9"` (chain mail), `"20"` (half plate), `"25"` (plate)
- **Notes**: Item weight in game units. Affects carrying capacity.

#### `Level`
- **Type**: ConstantInt
- **Values**: `"1"`, `"5"`, `"7"`
- **Notes**: Base item power level. Gates availability in loot tables and progression.

#### `MinLevel`
- **Type**: ConstantInt
- **Values**: `"1"`, `"5"`, `"7"`
- **Notes**: Minimum level for scaling/availability.

#### `MaxLevel`
- **Type**: ConstantInt
- **Notes**: Maximum level for scaling. Not observed in vanilla armor data.

#### `MinAmount` / `MaxAmount`
- **Type**: ConstantInt
- **Values**: `"1"`
- **Notes**: Stack limits. Set to `"1"` for equipment (armor doesn't stack).

### Boosts & Effects

#### `Boosts`
- **Type**: FixedString
- **Values**: `"AC(1)"`, `"Disadvantage(Skill,Stealth)"`, `"UnlockSpell(Target_TWN_FeignDeath)"`, `"IF(not HasPassive('MediumArmorMaster', context.Source)):Disadvantage(Skill,Stealth)"`, `"RollBonus(SavingThrow,1)"`, `"Ability(Strength, 2)"`
- **Notes**: Boost expressions applied while equipped. Semicolon-separated. Supports conditional syntax with `IF()`. The stealth disadvantage on medium/heavy armor is implemented as a conditional boost: `IF(not HasPassive('MediumArmorMaster', ...)):Disadvantage(Skill,Stealth)`. See [functors-boosts.md](../reference/functors-boosts.md).

#### `DefaultBoosts`
- **Type**: FixedString
- **Values**: `"ItemReturnToOwner()"`
- **Notes**: Default boosts always active. `ItemReturnToOwner()` causes the item to return to the owner when thrown. Rarely used on armor.

#### `PassivesOnEquip`
- **Type**: FixedString
- **Values**: `"ARM_MartialArtsLethality_1_Passive"`, `"ARM_Stealthy_1_Passive;ARM_Balance_1_Passive"`, `"MAG_TWN_Surgeon_ParalyzingCritical_Passive"`
- **Notes**: Semicolon-separated passive IDs granted while equipped. References entries in `Passive.txt`. Very common on magical armor.

#### `PersonalStatusImmunities`
- **Type**: StatusIDs
- **Values**: `"DIPPED_FIRE;DIPPED_POISON"`
- **Notes**: Semicolon-separated status IDs the wearer becomes immune to.

### Status

#### `StatusOnEquip`
- **Type**: FixedString
- **Values**: `"UNI_MERREGONMASK_EFFECT_TECHNICAL"`, `"MAG_KHALIDS_GIFT_TECHNICAL"`, `"MAG_EXOTIC_MATERIAL_ARMOR_TECHNICAL;MAG_CHARISMA_CASTER_TEMP_HP_TECHNICAL"`
- **Notes**: Status(es) applied when item is equipped. Semicolon-separated for multiple. Often named with `_TECHNICAL` suffix for hidden/non-display statuses. References StatusData entries.

#### `StatusInInventory`
- **Type**: FixedString
- **Values**: `"FLAG_SOUL_OF_ARTIFICE"`, `"ACTIVATE_STEEL_DEFENDER_MODEL"`
- **Notes**: Status applied while item is in inventory (not equipped). Used for items that have effects just by being carried.

### Charges

#### `Charges`
- **Type**: ConstantInt
- **Values**: `"8"`
- **Notes**: Current charge count for items with limited-use abilities.

#### `MaxCharges`
- **Type**: ConstantInt
- **Values**: `"8"`
- **Notes**: Maximum charge capacity. Charges regenerate on long rest.

### Conditions & Costs

#### `UseConditions`
- **Type**: Conditions
- **Notes**: Boolean condition expression restricting who can use the item. Not observed in vanilla armor data.

#### `UseCosts`
- **Type**: FixedString
- **Values**: `"ActionPoint:1"`
- **Notes**: Resource cost for using the item's active ability. Format: `ResourceType:Amount`.

#### `Requirements`
- **Type**: Requirements
- **Values**: `""` (empty)
- **Notes**: Equipment requirements. Observed as empty string. Proficiency is handled by `Proficiency Group` instead.

### Instrument

#### `InstrumentType`
- **Type**: InstrumentType (enum from [ValueLists](../formats/ValueLists.md))
- **Values**: `"Horn"`, `"Flute"`, `"Lute"`, `"Drum"`, `"None"`
- **Notes**: Musical instrument type. Only set on instrument items (Slot = `MusicalInstrument`). Determines which instrument animation/sound to use.

### Visual

#### `ItemColor`
- **Type**: FixedString
- **Values**: `"DefaultGray"`, `""` (empty)
- **Notes**: Color preset name referencing entries in `ItemColor.txt`. Controls item tint.

#### `ColorPresetResource`
- **Type**: FixedString
- **Values**: `"fa030c66-f9be-5dff-f479-bfbbe70cc41a"`
- **Notes**: UUID for a color preset resource. Used for dyed armor variants.

#### `ItemGroup`
- **Type**: FixedString
- **Values**: `"Gloves"`, `""` (empty)
- **Notes**: Item grouping for stacking/sorting.

### Flags

#### `Flags`
- **Type**: AttributeFlags (flags enum from [ValueLists](../formats/ValueLists.md))
- **Values**: `"InvulnerableAndInteractive"`, `"IgnoreClouds"`
- **Notes**: Semicolon-separated attribute flags. Rarely used on armor.

### Spells

#### `Spells`
- **Type**: FixedString
- **Notes**: Spells granted while item is equipped. Not observed in vanilla armor data — spell grants use `Boosts` with `UnlockSpell()` instead.

### Unobserved Fields

These fields are defined in Modifiers.txt for Armor but not observed in vanilla data:

- **`Durability`** / **`DurabilityDegradeSpeed`** — Durability system (not used)
- **`ExtraProperties`** — Additional properties
- **`FallingHitEffect`** / **`FallingLandEffect`** — Falling VFX
- **`GameSize`** — Size override
- **`NeedsIdentification`** — Identify requirement
- **`SoundSize`** — Sound category

---

## Value Syntax Reference

### Boost Expressions

Used in `Boosts` and `DefaultBoosts`:

```
AC(N)                          -- Flat AC bonus
Disadvantage(Skill,Stealth)    -- Disadvantage on a skill
Advantage(Skill,Perception)    -- Advantage on a skill
RollBonus(SavingThrow,N)       -- Bonus to saving throws
Ability(Strength, N)           -- Ability score bonus
UnlockSpell(SpellEntryName)    -- Grant a spell
Proficiency(HeavyArmor)        -- Grant a proficiency
IF(condition):Boost(...)       -- Conditional boost
```

### Slot Values

| Slot Value | Equipment |
|-----------|-----------|
| `Breast` | Body armor |
| `Boots` | Footwear |
| `Gloves` | Handwear |
| `Helmet` | Headwear |
| `Amulet` | Neckwear |
| `Ring` | Rings |
| `Cloak` | Cloaks |
| `Melee Offhand Weapon` | Shields |
| `MusicalInstrument` | Instruments |
| `Underwear` | Base clothing |
| `VanityBody` / `VanityBoots` | Camp cosmetics |
| `Overhead` | Headwear overlay |

---

## Cross-References

| From | To | Via |
|------|----|----|
| Armor.RootTemplate | GameObjects | UUID → `MapKey` in RootTemplates |
| Armor.ValueUUID | Value tables | Pricing lookup |
| Armor.PassivesOnEquip | PassiveData | Entry name reference |
| Armor.StatusOnEquip | StatusData | Entry name reference |
| Armor.StatusInInventory | StatusData | Entry name reference |
| Armor.PersonalStatusImmunities | StatusData | Status/group IDs |
| Armor.ObjectCategory | TreasureTable | Loot table categories |
| Armor.ComboCategory | ItemCombos | Crafting category |
| Armor.ItemColor | ItemColor.txt | Color preset name |
| Armor.ColorPresetResource | Color presets | UUID reference |
| Armor.Boosts | Boosts reference | [functors-boosts.md](../reference/functors-boosts.md) |

## Caveats & Gotchas

- **ArmorType "None"**: All non-body-armor equippables (gloves, boots, rings, amulets, cloaks, instruments) have `ArmorType "None"` and omit `ArmorClass`.
- **Shield slot**: Shields use Armor type (not Weapon), but their slot is `"Melee Offhand Weapon"`.
- **Stealth disadvantage**: Medium/heavy armor stealth disadvantage is a conditional boost, not inherent to the ArmorType. It uses `IF(not HasPassive('MediumArmorMaster',...)):Disadvantage(Skill,Stealth)`.
- **Spells vs Boosts**: To grant spells from armor, use `Boosts "UnlockSpell(...)"` — the `Spells` field is not used in vanilla armor.
- **StatusOnEquip semicolons**: Multiple statuses can be chained: `"STATUS1;STATUS2"`.
- **DyableArmor**: Items that can be dyed have `ComboCategory "DyableArmor"`, linking them to dye recipes in `ItemCombos.txt`.
- **Conditional boost scope**: `IF(Condition):Boost1(args);Boost2(args)` — the condition only applies to `Boost1`. For multiple conditional boosts, repeat the `IF()`: `IF(Condition):Boost1(args);IF(Condition):Boost2(args)`.
- **Cross-format name matching**: All name-based references (`PassivesOnEquip`, `StatusOnEquip`, `StatusInInventory`) are **case-sensitive** and whitespace-sensitive. Trailing spaces or wrong casing fail silently.
- **Inheritance load order**: `using "ParentArmor"` requires the parent to be defined in the same file or an earlier-loaded file. Forward references cause silent inheritance failure.
- **AC stacking**: `ArmorClassAbility "Dexterity"` with `0` max means no Dex cap (like light armor). With a positive max value it caps Dex bonus (like medium armor). Heavy armor sets this to `"None"` to exclude Dex entirely.
- **MusicalInstrument slot**: Instruments use the Armor type with `Slot "MusicalInstrument"` and `ArmorType "None"`. They follow the same boost/passive framework as other equipment.
- **OnEquip context**: `StatsFunctorContext.OnEquip` sets `context.Target = Item`, `context.Source = Self`. Not ideal for applying statuses — prefer `StatusOnEquip` or Osiris `Equipped` events instead.

---

## Scripting & Runtime Notes

### Script Extender (SE) Lua

```lua
-- Read armor stats
local stat = Ext.Stats.Get("ARM_ChainMail")
local ac = stat.ArmorClass
local slot = stat.Slot

-- Modify at runtime (MUST sync after)
stat.Boosts = "AC(2);Resistance(Fire,Resistant)"
Ext.Stats.Sync("ARM_ChainMail")

-- Access via entity
local entity = Ext.Entity.Get(itemGuid)
local statsName = entity.Stats.Name  -- e.g., "ARM_ChainMail"
```

> **CRITICAL:** `Ext.Stats.Sync()` is mandatory after any runtime change — without it modifications are invisible.

### Osiris Events

| Event | Signature | Relevance |
|-------|-----------|----------|
| `StatusApplied` | `(obj, status, causee, storyId)` | Fires when `StatusOnEquip` triggers |
| `CharacterJoinedParty` | `(character, partyGuid)` | May need to reapply equipment effects |
