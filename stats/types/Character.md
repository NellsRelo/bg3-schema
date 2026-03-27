# Character

> **Type identifier**: `Character`
> **Source file**: `Stats/Generated/Data/Character.txt`
> **Modifier definition**: [Modifiers.md](../formats/Modifiers.md#character) (58 fields)

---

## Overview

Defines NPC and creature stat blocks — ability scores, resistances, action resources, proficiencies, perception, and movement. The `_Base` entry is the root template all characters inherit from. Characters link to GameObjects templates via the `Stats` attribute.

## Entry Format

```
new entry "_Base"
type "Character"
data "Level" "1"
data "Strength" "10"
data "Dexterity" "10"
data "Constitution" "10"
data "Intelligence" "10"
data "Wisdom" "10"
data "Charisma" "10"
data "Armor" "10"
data "Vitality" "5"
data "XPReward" "810b5510-6748-4c8e-bef0-d990880ed1dd"
data "Sight" "1600"
data "Hearing" "1100"
data "FOV" "90"
data "Weight" "50"
data "StepsType" "Bare"
data "SpellCastingAbility" "Intelligence"
data "ProficiencyBonusScaling" "265d62c4-9b82-4ed6-9a86-da675b4ef8fe"
data "ActionResources" "ActionPoint:1;BonusActionPoint:1;Movement:9;ReactionActionPoint:1"
data "Passives" "AttackOfOpportunity;DarknessRules"
data "DefaultBoosts" "BlockRegainHP(Undead;Construct)"
data "PathInfluence" "BloodElectrified,100;BloodFrozen,30;Lava,700;Fire,40;..."
```

## Pack Distribution

| Pack | Size | Notes |
|------|------|-------|
| GustavDev | 184 KB | Named NPCs, boss characters |
| SharedDev | 147 KB | Development characters |
| Shared | 141 KB | Core base templates, generic creatures |
| Gustav | 67 KB | Campaign-specific NPCs |
| Honour | 13 KB | Honour-mode overrides |
| GustavX | 2 KB | DLC characters |

---

## Form Reference — All Fields

> Complete field table for form/editor construction. 58 fields defined in [Modifiers.md](../formats/Modifiers.md#character). ✓ = observed in vanilla data.

| Field | Type | Observed |
|-------|------|:--------:|
| `AcidResistance` | ResistanceFlags | ✓ |
| `ActionResources` | FixedString | ✓ |
| `Armor` | ConstantInt | ✓ |
| `ArmorType` | ArmorType | ✓ |
| `BludgeoningResistance` | ResistanceFlags | ✓ |
| `Charisma` | ConstantInt | ✓ |
| `Class` | FixedString | ✓ |
| `ColdResistance` | ResistanceFlags | ✓ |
| `Constitution` | ConstantInt | ✓ |
| `DarkvisionRange` | FixedString | ✓ |
| `DefaultBoosts` | FixedString | ✓ |
| `Dexterity` | ConstantInt | ✓ |
| `DifficultyStatuses` | FixedString | ✓ |
| `DynamicAnimationTag` | Guid | |
| `ExtraProperties` | FixedString | |
| `FallingHitEffect` | FixedString | ✓ |
| `FallingLandEffect` | FixedString | ✓ |
| `FireResistance` | ResistanceFlags | ✓ |
| `Flags` | AttributeFlags | ✓ |
| `ForceResistance` | ResistanceFlags | ✓ |
| `FOV` | ConstantInt | ✓ |
| `GameSize` | FixedString | ✓ |
| `Hearing` | ConstantInt | ✓ |
| `Initiative` | ConstantInt | ✓ |
| `Intelligence` | ConstantInt | ✓ |
| `Level` | ConstantInt | ✓ |
| `LightningResistance` | ResistanceFlags | ✓ |
| `MinimumDetectionRange` | FixedString | ✓ |
| `NecroticResistance` | ResistanceFlags | ✓ |
| `Passives` | FixedString | ✓ |
| `PathInfluence` | FixedString | ✓ |
| `PersonalStatusImmunities` | StatusIDs | ✓ |
| `PiercingResistance` | ResistanceFlags | ✓ |
| `PoisonResistance` | ResistanceFlags | ✓ |
| `Proficiency Group` | ProficiencyGroupFlags | ✓ |
| `ProficiencyBonus` | ConstantInt | ✓ |
| `ProficiencyBonusScaling` | Guid | ✓ |
| `Progression Type` | Progression Type | |
| `Progressions` | FixedString | ✓ |
| `PsychicResistance` | ResistanceFlags | ✓ |
| `RadiantResistance` | ResistanceFlags | ✓ |
| `Sight` | ConstantInt | ✓ |
| `SlashingResistance` | ResistanceFlags | ✓ |
| `SoundSize` | FixedString | ✓ |
| `SpellCastingAbility` | Ability | ✓ |
| `StepsType` | StepsType | ✓ |
| `Strength` | ConstantInt | ✓ |
| `ThunderResistance` | ResistanceFlags | ✓ |
| `UnarmedAttackAbility` | Ability | ✓ |
| `UnarmedRangedAttackAbility` | Ability | ✓ |
| `VerticalFOV` | ConstantInt | |
| `Vitality` | ConstantInt | ✓ |
| `Weight` | ConstantFloat | ✓ |
| `Wisdom` | ConstantInt | ✓ |
| `XPReward` | Guid | ✓ |

### Boost Fields & Observed Boosts

| Boost Field | Purpose |
|-------------|--------|
| `DefaultBoosts` | Default boosts for the character |

**Boosts used in vanilla (9):** `ActionResource` · `ActionResourceBlock` · `Attribute` · `BlockRegainHP` · `CriticalHit` · `DialogueBlock` · `Invulnerable` · `ProficiencyBonus` · `Skill`

### Functor Fields & Observed Functors

None — Character does not have functor-accepting fields.

---

## Complete Field Reference

### Ability Scores

#### `Strength`
- **Type**: ConstantInt
- **Values**: `"10"` (base), `"18"` (strong fighter), `"25"` (ancient dragon)
- **Notes**: STR score. Affects melee attack/damage, carry capacity, Athletics, Strength saves. Range 1-30.

#### `Dexterity`
- **Type**: ConstantInt
- **Values**: `"10"` (base), `"13"` (nimble), `"22"` (extremely agile)
- **Notes**: DEX score. Affects AC (with armor), ranged attacks, Dexterity saves, Stealth, Acrobatics. Range 1-30.

#### `Constitution`
- **Type**: ConstantInt
- **Values**: `"10"` (base), `"14"` (tough), `"17"` (very hardy)
- **Notes**: CON score. Affects HP per level and Constitution saves. Range 1-30.

#### `Intelligence`
- **Type**: ConstantInt
- **Values**: `"10"` (base), `"15"` (clever), `"20"` (brilliant)
- **Notes**: INT score. Affects Wizard spell DCs, Investigation, Arcana. Range 1-30.

#### `Wisdom`
- **Type**: ConstantInt
- **Values**: `"10"` (base), `"16"` (perceptive), `"20"` (sagacious)
- **Notes**: WIS score. Affects Cleric/Druid/Ranger spell DCs, Perception, Insight. Range 1-30.

#### `Charisma`
- **Type**: ConstantInt
- **Values**: `"10"` (base), `"15"` (personable), `"22"` (supernaturally charming)
- **Notes**: CHA score. Affects Warlock/Sorcerer/Bard/Paladin spell DCs, Persuasion, Deception. Range 1-30.

### Combat Stats

#### `Armor`
- **Type**: ConstantInt
- **Values**: `"0"` (no natural armor), `"10"` (standard), `"12"` (natural armor), `"15"` (heavy natural armor)
- **Notes**: Natural armor class base. This is the creature's unarmored AC, commonly 10 for humanoids. Monsters may have higher natural AC.

#### `Vitality`
- **Type**: ConstantInt
- **Values**: `"5"` (weak creature), `"8"`, `"24"`, `"145"` (boss)
- **Notes**: Base hit points. For leveled characters this is a starting value; class progressions add HP per level.

#### `Initiative`
- **Type**: ConstantInt
- **Values**: `"-20"` (very slow), `"-1"`, `"2"`, `"4"`, `"6"` (fast)
- **Notes**: Initiative modifier. Added to initiative rolls to determine combat turn order. Can be negative for slow creatures.

#### `Level`
- **Type**: ConstantInt
- **Values**: `"1"` (standard)
- **Notes**: Base character level. Almost always `"1"` — actual level comes from Progression system. Affects proficiency bonus when `ProficiencyBonusScaling` is set.

### Resistances

All resistance fields use the **ResistanceFlags** enum from [ValueLists](../formats/ValueLists.md).

Valid values: `"Resistant"`, `"Immune"`, `"Vulnerable"`, `"ResistantToNonMagical"`, `"ImmuneToNonMagical"`

| Field | Damage Type | Example |
|-------|-------------|---------|
| `AcidResistance` | Acid | `"Resistant"`, `"Immune"` |
| `BludgeoningResistance` | Bludgeoning | `"ResistantToNonMagical"`, `"Immune"` |
| `ColdResistance` | Cold | `"Resistant"`, `"Immune"` |
| `FireResistance` | Fire | `"Resistant"`, `"Immune"` |
| `ForceResistance` | Force | `"Vulnerable"` |
| `LightningResistance` | Lightning | `"Resistant"`, `"Immune"` |
| `NecroticResistance` | Necrotic | `"Immune"` |
| `PiercingResistance` | Piercing | `"ResistantToNonMagical"` |
| `PoisonResistance` | Poison | `"Immune"` |
| `PsychicResistance` | Psychic | `"Immune"` |
| `RadiantResistance` | Radiant | `"Vulnerable"` |
| `SlashingResistance` | Slashing | `"ResistantToNonMagical"` |
| `ThunderResistance` | Thunder | `"Immune"` |

**Notes**: `ResistantToNonMagical` is unique to physical damage types (Bludgeoning, Piercing, Slashing) — creature takes half damage from non-magical sources but full from magical. Only set on creatures that specifically have this resistance (e.g., fiends, lycanthropes).

### Action Resources

#### `ActionResources`
- **Type**: FixedString
- **Values**: `"ActionPoint:1;BonusActionPoint:1;Movement:9;ReactionActionPoint:1"`, `"ActionPoint:1;BonusActionPoint:1;Movement:10.5;ReactionActionPoint:1"`, `"ActionPoint:0;BonusActionPoint:2;ReactionActionPoint:0"`
- **Notes**: Semicolon-separated `ResourceType:Amount` pairs. Defines per-turn action economy. Standard humanoid: 1 Action, 1 Bonus Action, 1 Reaction, 9m Movement. Movement values are in meters. Some creatures have 0 actions and multiple bonus actions for special behavior.

### Casting & Abilities

#### `SpellCastingAbility`
- **Type**: Ability (enum from [ValueLists](../formats/ValueLists.md))
- **Values**: `"Intelligence"` (Wizards), `"Wisdom"` (Clerics/Druids/Rangers), `"Charisma"` (Warlocks/Sorcerers/Bards/Paladins), `"None"`
- **Notes**: Primary ability for spell save DCs and spell attack modifiers. `"None"` for non-caster creatures.

#### `UnarmedAttackAbility`
- **Type**: Ability (enum from [ValueLists](../formats/ValueLists.md))
- **Values**: `"Strength"`, `"None"`
- **Notes**: Ability modifier used for unarmed melee attacks. Usually `"Strength"`.

#### `UnarmedRangedAttackAbility`
- **Type**: Ability (enum from [ValueLists](../formats/ValueLists.md))
- **Values**: `"Strength"`, `"None"`
- **Notes**: Ability modifier used for unarmed ranged attacks (thrown objects).

### Proficiency

#### `ProficiencyBonusScaling`
- **Type**: Guid
- **Values**: `"265d62c4-9b82-4ed6-9a86-da675b4ef8fe"`
- **Notes**: UUID referencing a proficiency bonus scaling table. Determines how proficiency bonus grows with level. The same UUID is shared across most characters.

#### `ProficiencyBonus`
- **Type**: ConstantInt
- **Values**: `"3"`, `"4"`, `""` (empty)
- **Notes**: Fixed proficiency bonus override. When set, bypasses the `ProficiencyBonusScaling` table. Used for high-CR creatures with custom proficiency.

#### `Proficiency Group`
- **Type**: ProficiencyGroupFlags (flags enum from [ValueLists](../formats/ValueLists.md))
- **Values**: `"SimpleWeapons;MartialWeapons;MediumArmor;HeavyArmor;LightArmor;Shields"` (Fighter), `"LightArmor;HandCrossbows;Longswords;Rapiers;Shortswords;SimpleWeapons"` (Rogue)
- **Notes**: Semicolon-separated proficiency flags. Defines all weapon and armor proficiencies the character has. Combines weapon-specific and armor-category proficiencies.

### Progression & Class

#### `Class`
- **Type**: FixedString
- **Values**: `"Cleric"`, `"Fighter"`, `"Wizard"`, `"Rogue"`
- **Notes**: Primary class identifier. Determines which progression table to use.

#### `Progression Type`
- **Type**: Progression Type (enum from [ValueLists](../formats/ValueLists.md))
- **Values**: `"Level"`, `""` (empty)
- **Notes**: How the character progresses — `"Level"` for standard leveling, empty/absent for non-leveling creatures.

#### `Progressions`
- **Type**: FixedString
- **Values**: `"f59fb377-24c5-444a-861b-8a0260ff0e20"`, `"224dd8a5-da1a-427c-beae-879c8524fec1"`
- **Notes**: UUID referencing a Progression entry in the Progressions region. Defines class features, spell slots, and ability unlocks per level.

### Perception & Sensing

#### `Sight`
- **Type**: ConstantInt
- **Values**: `"1600"` (standard), `"1850"`, `"2400"` (eagle-eyed)
- **Notes**: Sight range in game units (centimeters). Determines how far the creature can see. 1600 = standard, higher values for creatures with keen sight.

#### `Hearing`
- **Type**: ConstantInt
- **Values**: `"1100"` (standard), `"1800"` (keen hearing)
- **Notes**: Hearing range in game units. Affects detection of sneaking characters.

#### `FOV`
- **Type**: ConstantInt
- **Values**: `"90"`
- **Notes**: Horizontal field of view in degrees. Standard is 90°.

#### `VerticalFOV`
- **Type**: ConstantInt
- **Values**: `"0"`, `""` (empty)
- **Notes**: Vertical field of view. Usually 0 or unset.

#### `DarkvisionRange`
- **Type**: FixedString
- **Values**: `"0"` (no darkvision), `"9"` (60ft = 9 cells), `"16"` (extended darkvision)
- **Notes**: Darkvision distance in cells (1 cell ≈ 6.6ft). 0 = no darkvision. Elves/dwarves typically have 9.

#### `MinimumDetectionRange`
- **Type**: FixedString
- **Values**: `"2"`
- **Notes**: Minimum range at which the creature can detect others, regardless of stealth.

### Passives & Boosts

#### `Passives`
- **Type**: FixedString
- **Values**: `"AttackOfOpportunity;DarknessRules"` (minimal base), `"ShortResting;NonLethal;WeaponThrow;Perform;AttackOfOpportunity;DarknessRules"` (full PC-like), `"FeyAncestry;Darkvision;DarknessRules"` (racial)
- **Notes**: Semicolon-separated passive ability IDs from `Passive.txt`. Defines default passive features. `AttackOfOpportunity` and `DarknessRules` are near-universal. PC-like creatures add `ShortResting`, `NonLethal`, `WeaponThrow`, `Perform`.

#### `DefaultBoosts`
- **Type**: FixedString
- **Values**: `"BlockRegainHP(Undead;Construct)"` (universal base), `"Skill(Stealth, 6); BlockRegainHP(Undead;Construct)"` (with skill bonus), `"ProficiencyBonus(SavingThrow, Wisdom); BlockRegainHP(Undead;Construct)"` (with save bonus)
- **Notes**: Semicolon-separated boost expressions always active. `BlockRegainHP(Undead;Construct)` is on almost every character — prevents Undead and Constructs from being healed normally. Additional boosts for specific creatures: `Skill()`, `ProficiencyBonus()`, `Advantage()`. See [functors-boosts.md](../reference/functors-boosts.md).

#### `PersonalStatusImmunities`
- **Type**: StatusIDs
- **Values**: `"SG_Poisoned;EXHAUSTED;PARALYZED;HOLD_PERSON;PETRIFIED..."` (15+ items)
- **Notes**: Semicolon-separated status IDs and status group IDs (prefixed `SG_`). Defines complete status immunity list. Common on undead, constructs, and boss creatures.

#### `DifficultyStatuses`
- **Type**: FixedString
- **Values**: `"STATUS_EASY: HEALTHREDUCTION_EASYMODE; STATUS_HARD: HEALTHBOOST_HARDCORE"`, `"STATUS_HARD: ORIN_HARDCORE"`
- **Notes**: Difficulty-conditional status application. Format: `DIFFICULTY_TAG: STATUS_NAME; DIFFICULTY_TAG: STATUS_NAME`. Applies different statuses based on game difficulty setting.

### Movement & Sound

#### `Weight`
- **Type**: ConstantFloat
- **Values**: `"10"` (small), `"25"` (child-sized), `"35"` (light humanoid), `"50"` (standard), `"75"` (heavy/large)
- **Notes**: Character weight in game units. Affects throw distance and push calculations.

#### `StepsType`
- **Type**: StepsType (enum from [ValueLists](../formats/ValueLists.md))
- **Values**: `"Bare"`, `"Leather"`, `"Metal"`, `"Bone"`
- **Notes**: Footstep sound type. Determines which sound set plays when walking. `Bare` = barefoot, `Metal` = armored, etc.

#### `PathInfluence`
- **Type**: FixedString
- **Values**: `"BloodElectrified,100;BloodFrozen,30;Lava,700;Fire,40;HolyFire,40;..."` (38-item comma+semicolon list)
- **Notes**: Surface avoidance weights for pathfinding AI. Format: `SurfaceType,Weight;` pairs. Higher weight = stronger avoidance. Standard list includes all hazardous surface types (Lava=700, Fire=40, Poison=200, etc.). Characters will path around surfaces proportional to these weights.

#### `SoundSize`
- **Type**: FixedString
- **Values**: `"Medium"`, `"Large"`, `"Huge"`
- **Notes**: Sound size category for audio system. Determines footstep volume and NPC detection sounds.

#### `GameSize`
- **Type**: FixedString
- **Values**: `"Small"`, `"Medium"`, `"Large"`, `"Huge"`
- **Notes**: Creature size category. Affects combat mechanics (grapple, shove), space occupied, and model scale.

### Progression References

#### `XPReward`
- **Type**: Guid
- **Values**: `"810b5510-6748-4c8e-bef0-d990880ed1dd"`, `"c83d6caa-c5c3-4356-b55c-8d634535976c"`, `""` (empty)
- **Notes**: UUID referencing an XP reward table. Determines experience awarded on defeat. Empty = no XP.

#### `DynamicAnimationTag`
- **Type**: Guid
- **Values**: `"d559367e-4d27-402a-8898-a72fd5f20c8b"`
- **Notes**: UUID for a dynamic animation tag. Controls animation behaviour variations.

### Armor

#### `ArmorType`
- **Type**: ArmorType (enum from [ValueLists](../formats/ValueLists.md))
- **Values**: `"None"`, `"Cloth"`, `"Leather"`, `"ScaleMail"`
- **Notes**: Natural armor type for the creature. Affects AC calculation and stealth penalties. Most characters use `"None"` (unarmored) since armor comes from equipment.

### Properties

#### `ExtraProperties`
- **Type**: FixedString
- **Values**: `"ApplyStatus(HIDE_IN_PLAIN_SIGHT,100,-1)"`, `""` (empty)
- **Notes**: Extra property functors applied to the character. Uses the same functor syntax as spell properties. Rarely used — only on specialized creatures.

#### `Flags`
- **Type**: AttributeFlags (flags enum from [ValueLists](../formats/ValueLists.md))
- **Values**: `"ObscurityWithoutSneaking"`, `"EnableObscurityEvents"`, `"Floating;SlippingImmunity;Grounded;IgnoreClouds"`
- **Notes**: Semicolon-separated character attribute flags. Control special behaviors: `Floating` (levitation), `SlippingImmunity` (ice immunity), `Grounded` (can't be pushed), `IgnoreClouds` (ignores fog), `ObscurityWithoutSneaking` (naturally hidden).

#### `FallingHitEffect`
- **Type**: FixedString
- **Values**: `"VFX_Combat_Bludgeoning_Damage_Blood_01"`
- **Notes**: VFX played when the character is hit by a falling object.

#### `FallingLandEffect`
- **Type**: FixedString
- **Values**: `"VFX_Combat_Force_Land_01"`
- **Notes**: VFX played when the character lands after falling.

---

## Value Syntax Reference

### ActionResources Format

```
ResourceType:Amount;ResourceType:Amount;...
```

Common resource types:
- `ActionPoint` — Standard actions (usually 1)
- `BonusActionPoint` — Bonus actions (usually 1)
- `Movement` — Movement in meters (9 = 30ft, 10.5 = 35ft)
- `ReactionActionPoint` — Reactions (usually 1)
- `SpellSlot:N:Level` — Spell slot of level N (e.g., `SpellSlot:2:1` = 2 level-1 slots)

### DefaultBoosts Common Functions

```
BlockRegainHP(Type1;Type2)         -- Block healing for creature types
Skill(SkillName, Bonus)            -- Flat skill bonus
ProficiencyBonus(SavingThrow, Ability) -- Save proficiency
Advantage(Skill, SkillName)        -- Advantage on skill
Resistance(DamageType, Resistant)  -- Damage resistance
```

### Resistance Values

| Value | Meaning |
|-------|---------|
| `Resistant` | Half damage from all sources |
| `Immune` | No damage |
| `Vulnerable` | Double damage |
| `ResistantToNonMagical` | Half from non-magical, full from magical |
| `ImmuneToNonMagical` | No damage from non-magical, full from magical |

---

## Cross-References

| From | To | Via |
|------|----|----|
| Character.Progressions | Progressions region | UUID reference |
| Character.XPReward | XP reward tables | UUID reference |
| Character.ProficiencyBonusScaling | Proficiency tables | UUID reference |
| Character.DynamicAnimationTag | Animation system | UUID reference |
| Character.Passives | PassiveData | Entry name references |
| Character.PersonalStatusImmunities | StatusData | Status/group IDs |
| Character.DefaultBoosts | Boosts reference | [functors-boosts.md](../reference/functors-boosts.md) |
| Character.Class | Classes region | Class identifier |
| Character (Stats attribute) | GameObjects | GameObjects.Stats references entry name |

## Caveats & Gotchas

- **BlockRegainHP**: `BlockRegainHP(Undead;Construct)` is on nearly every character. It prevents healing from working on Undead and Constructs. Do not remove it unless intentional.
- **PathInfluence length**: The default `PathInfluence` string is very long (~38 surface types). It's inherited from `_Base` — only override if the creature should path through specific surfaces (e.g., fire elementals ignoring Fire surfaces).
- **Vitality vs HP**: `Vitality` is the base HP value. Actual HP at higher levels = Vitality + (CON modifier × level) + class hit die rolls. For non-leveling creatures, Vitality IS the final HP.
- **DarkvisionRange units**: Uses cells (1 cell ≈ 1.5m ≈ 5ft), unlike Sight/Hearing which use cm. 9 cells = 60ft darkvision.
- **Resistance stacking**: Resistances from Character stats stack with equipment/status resistances according to D&D 5e rules (resistance doesn't stack, immunity overrides resistance).
- **DifficultyStatuses format**: The `STATUS_EASY:` and `STATUS_HARD:` prefixes are difficulty tags, not status names. The part after the colon is the actual status applied.
- **`_Base` inheritance chain**: Nearly all Character entries use `using "_Base"`. This parent defines ~38-item `PathInfluence`, standard `Sight`/`Hearing`/`FOV`, `BlockRegainHP(Undead;Construct)`, and default action resources. Only override fields you need to change.
- **Cross-format name matching**: `GameObjects.Stats` references Character entry names and is **case-sensitive**. A mismatch between the LSX `Stats` attribute and the `.txt` entry name fails silently.
- **Conditional boost scope**: In `DefaultBoosts`, `IF(Condition):Boost1(args);Boost2(args)` — the condition only applies to `Boost1`. Repeat `IF()` for each: `IF(Condition):Boost1(args);IF(Condition):Boost2(args)`.
- **Passives field**: Semicolon-delimited list of PassiveData entry names. These are **name-based cross-format references** — case-sensitive, no whitespace tolerance.
- **ActionResources format**: `ActionPoint:N` grants N action points. `SpellSlot:N:L` grants N spell slots of level L. Multiple resources are semicolon-delimited.

---

## Scripting & Runtime Notes

### Script Extender (SE) Lua

```lua
-- Read character stats
local stat = Ext.Stats.Get("Goblin_Warrior")
local hp = stat.Vitality
local passives = stat.Passives

-- Modify at runtime (MUST sync after)
stat.DefaultBoosts = "Resistance(Fire,Resistant)"
Ext.Stats.Sync("Goblin_Warrior")

-- Create new stat entry inheriting from existing
local custom = Ext.Stats.Create("MyCreature", "Character", "_Base")
custom.Vitality = 50
Ext.Stats.Sync("MyCreature")
```

> **CRITICAL:** `Ext.Stats.Sync()` is mandatory after any runtime change — without it modifications are invisible.

### Osiris Events

| Event | Signature | Relevance |
|-------|-----------|----------|
| `EnteredCombat` | `(character, combatId)` | Combat start; `OnCombatStarted` context triggers |
| `TurnStarted` | `(character, combatId)` | `OnTurn` context fires here |
| `Died` | `(entity, cause)` | Character death tracking |
| `LeveledUp` | `(character, level)` | Recalculates Vitality/HP scaling |
| `LongRestFinished` | `(character, resting)` | `OnLongRest` context fires here |
| `ShortRested` | `(character, resting)` | `OnShortRest` context fires here |
