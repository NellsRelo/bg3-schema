# Modifiers.txt — Stats Type Field Definitions

> **Source**: `Shared/Public/Shared/Stats/Generated/Structure/Modifiers.txt`
> **Size**: 25,917 bytes (646 lines)
> **Pack**: Shared only — definitive schema for all stat types

## Purpose

Defines **every valid field** (and its value type) for each stat data type. When a `.txt` data file has:

```
new entry "Longsword"
type "Weapon"
data "Damage" "1d8"
data "Damage Type" "Slashing"
```

This file declares that `Weapon` has fields `Damage` (type `FixedString`) and `Damage Type` (type `Damage Type`). The types reference valuelists from [ValueLists.txt](ValueLists.md).

## Format

```
modifier type "TypeName"
modifier "FieldName","ValueType"
modifier "FieldName","ValueType"
...
```

## Types Defined (9 total)

| Type | Field Count | Data Files | Description |
|------|------------|------------|-------------|
| [Armor](#armor) | 52 | Armor.txt | Armor, shields, clothing |
| [Character](#character) | 58 | Character.txt | NPC/creature stat blocks |
| [CriticalHitTypeData](#criticalhittypedata) | 13 | CriticalHitTypes.txt | Critical hit VFX per damage type |
| [InterruptData](#interruptdata) | 30 | Interrupt.txt | Interrupt/reaction definitions |
| [Object](#object) | 47 | Object.txt | Consumables, scrolls, misc items |
| [PassiveData](#passivedata) | 29 | Passive.txt | Passive features & abilities |
| [SpellData](#spelldata) | 185 | Spell_*.txt | All spell types (Projectile, Target, Shout, etc.) |
| [StatusData](#statusdata) | 110 | Status_*.txt | All status types (BOOST, EFFECT, etc.) |
| [Weapon](#weapon) | 60 | Weapon.txt | Weapons |

---

## Armor

52 fields. Used by `Data/Armor.txt`.

| Field | Type | Notes |
|-------|------|-------|
| `Ability Modifier Cap` | ConstantInt | Max ability modifier for AC |
| `Armor Class Ability` | Ability | Ability used for AC (usually Dexterity) |
| `ArmorClass` | ConstantInt | Base AC |
| `ArmorType` | ArmorType | None, Cloth..Plate |
| `Boosts` | FixedString | Boost expressions |
| `Charges` | ConstantInt | Charge count |
| `ColorPresetResource` | FixedString | Color preset UUID |
| `ComboCategory` | FixedString | Crafting combo category |
| `DefaultBoosts` | FixedString | Default boost expressions |
| `Durability` | ConstantInt | Durability HP |
| `DurabilityDegradeSpeed` | Qualifier | Degradation rate |
| `ExtraProperties` | FixedString | Additional properties |
| `FallingHitEffect` | FixedString | VFX on falling hit |
| `FallingLandEffect` | FixedString | VFX on landing |
| `Flags` | AttributeFlags | Item attribute flags |
| `GameSize` | FixedString | Object size override |
| `InstrumentType` | InstrumentType | Musical instrument type |
| `InventoryTab` | InventoryTabs | Inventory tab assignment |
| `ItemColor` | FixedString | Item color preset name |
| `ItemGroup` | FixedString | Item group for stacking |
| `Level` | ConstantInt | Item level |
| `MaxAmount` | ConstantInt | Max stack amount |
| `MaxCharges` | ConstantInt | Max charge capacity |
| `MaxLevel` | ConstantInt | Max level for scaling |
| `MinAmount` | ConstantInt | Min drop amount |
| `MinLevel` | ConstantInt | Min level for scaling |
| `NeedsIdentification` | YesNo | Requires Identify spell |
| `ObjectCategory` | FixedString | Object category for loot tables |
| `PassivesOnEquip` | FixedString | Semicolon-separated passive IDs |
| `PersonalStatusImmunities` | StatusIDs | Status immunities |
| `Priority` | ConstantInt | Resolution priority |
| `Proficiency Group` | ProficiencyGroupFlags | Required proficiency |
| `Rarity` | Rarity | Common..Legendary |
| `Requirements` | Requirements | Equip requirements |
| `RootTemplate` | FixedString | Template UUID |
| `Shield` | YesNo | Is shield |
| `Slot` | Itemslot | Equipment slot |
| `SoundSize` | FixedString | Sound category |
| `Spells` | FixedString | Granted spells |
| `StatusInInventory` | FixedString | Status while in inventory |
| `StatusOnEquip` | FixedString | Status applied on equip |
| `Tags` | FixedString | Semicolon-separated tag UUIDs |
| `Unique` | ConstantInt | Unique item flag (0/1) |
| `UseConditions` | Conditions | Use condition expression |
| `UseCosts` | FixedString | Use cost expression |
| `ValueOverride` | ConstantInt | Override gold value |
| `ValueLevel` | ConstantInt | Value scaling level |
| `ValueRounding` | ConstantInt | Value rounding |
| `ValueScale` | ConstantFloat | Value multiplier |
| `ValueUUID` | Guid | Value table UUID |
| `Weight` | ConstantFloat | Item weight |

---

## Character

58 fields. Used by `Data/Character.txt`.

| Field | Type | Notes |
|-------|------|-------|
| `AcidResistance` | ResistanceFlags | Acid damage resistance |
| `ActionResources` | FixedString | Action resource grants |
| `Armor` | ConstantInt | Natural armor |
| `ArmorType` | ArmorType | Armor type |
| `BludgeoningResistance` | ResistanceFlags | Bludgeoning resistance |
| `Charisma` | ConstantInt | CHA score |
| `Class` | FixedString | Class identifier |
| `ColdResistance` | ResistanceFlags | Cold resistance |
| `Constitution` | ConstantInt | CON score |
| `DarkvisionRange` | FixedString | Darkvision distance |
| `DefaultBoosts` | FixedString | Default boosts |
| `Dexterity` | ConstantInt | DEX score |
| `DifficultyStatuses` | FixedString | Difficulty-conditional statuses |
| `DynamicAnimationTag` | Guid | Animation tag UUID |
| `ExtraProperties` | FixedString | Extra properties |
| `FallingHitEffect` | FixedString | Falling hit VFX |
| `FallingLandEffect` | FixedString | Falling land VFX |
| `FireResistance` | ResistanceFlags | Fire resistance |
| `Flags` | AttributeFlags | Character flags |
| `ForceResistance` | ResistanceFlags | Force resistance |
| `FOV` | ConstantInt | Field of view |
| `GameSize` | FixedString | Size override |
| `Hearing` | ConstantInt | Hearing range |
| `Initiative` | ConstantInt | Initiative modifier |
| `Intelligence` | ConstantInt | INT score |
| `Level` | ConstantInt | Character level |
| `LightningResistance` | ResistanceFlags | Lightning resistance |
| `MinimumDetectionRange` | FixedString | Min detection range |
| `NecroticResistance` | ResistanceFlags | Necrotic resistance |
| `Passives` | FixedString | Semicolon-separated passive IDs |
| `PathInfluence` | FixedString | Pathfinding influence |
| `PersonalStatusImmunities` | StatusIDs | Status immunities |
| `PiercingResistance` | ResistanceFlags | Piercing resistance |
| `PoisonResistance` | ResistanceFlags | Poison resistance |
| `ProficiencyBonusScaling` | Guid | Proficiency bonus table UUID |
| `Proficiency Group` | ProficiencyGroupFlags | Proficiency groups |
| `ProficiencyBonus` | ConstantInt | Proficiency bonus value |
| `Progression Type` | Progression Type | Level vs ChallengeRating |
| `Progressions` | FixedString | Progression UUIDs |
| `PsychicResistance` | ResistanceFlags | Psychic resistance |
| `RadiantResistance` | ResistanceFlags | Radiant resistance |
| `Sight` | ConstantInt | Sight range |
| `SlashingResistance` | ResistanceFlags | Slashing resistance |
| `SoundSize` | FixedString | Sound category |
| `SpellCastingAbility` | Ability | Spellcasting ability |
| `StepsType` | StepsType | Footstep sound type |
| `Strength` | ConstantInt | STR score |
| `ThunderResistance` | ResistanceFlags | Thunder resistance |
| `UnarmedAttackAbility` | Ability | Unarmed melee ability |
| `UnarmedRangedAttackAbility` | Ability | Unarmed ranged ability |
| `VerticalFOV` | ConstantInt | Vertical field of view |
| `Vitality` | ConstantInt | Hit points |
| `Weight` | ConstantFloat | Character weight |
| `Wisdom` | ConstantInt | WIS score |
| `XPReward` | Guid | XP reward table UUID |

---

## CriticalHitTypeData

13 fields. Used by `Data/CriticalHitTypes.txt`.

| Field | Type | Notes |
|-------|------|-------|
| `AcidFX` | Guid | Acid crit VFX UUID |
| `BludgeoningFX` | Guid | Bludgeoning crit VFX UUID |
| `ColdFX` | Guid | Cold crit VFX UUID |
| `FireFX` | Guid | Fire crit VFX UUID |
| `ForceFX` | Guid | Force crit VFX UUID |
| `LightningFX` | Guid | Lightning crit VFX UUID |
| `NecroticFX` | Guid | Necrotic crit VFX UUID |
| `PiercingFX` | Guid | Piercing crit VFX UUID |
| `PoisonFX` | Guid | Poison crit VFX UUID |
| `PsychicFX` | Guid | Psychic crit VFX UUID |
| `RadiantFX` | Guid | Radiant crit VFX UUID |
| `SlashingFX` | Guid | Slashing crit VFX UUID |
| `ThunderFX` | Guid | Thunder crit VFX UUID |

---

## InterruptData

30 fields. Used by `Data/Interrupt.txt`.

| Field | Type | Notes |
|-------|------|-------|
| `Conditions` | Conditions | Trigger conditions |
| `Container` | FixedString | Container spell ID |
| `Cooldown` | CooldownType | Cooldown type |
| `Cost` | FixedString | Resource cost |
| `Description` | TranslatedString | Description handle |
| `DescriptionRef` | TranslatedString | Description reference |
| `DescriptionParams` | FixedString | Description parameters |
| `DisplayName` | TranslatedString | Display name handle |
| `DisplayNameRef` | TranslatedString | Display name reference |
| `EnableCondition` | Conditions | Enable condition |
| `EnableContext` | StatsFunctorContext | Enable context |
| `ExtraDescription` | TranslatedString | Extra description handle |
| `ExtraDescriptionRef` | TranslatedString | Extra description reference |
| `ExtraDescriptionParams` | FixedString | Extra description params |
| `Failure` | StatsFunctors | Functors on failure |
| `Icon` | FixedString | Icon resource name |
| `InterruptContext` | InterruptContext | When interrupt triggers |
| `InterruptContextScope` | InterruptContextScope | Range: Self, Nearby, Far |
| `InterruptDefaultValue` | InterruptDefaultValue | Default: None, Ask, Enabled |
| `InterruptFlags` | InterruptFlagsList | Interrupt flags |
| `LoreDescription` | TranslatedString | Lore description handle |
| `LoreDescriptionRef` | TranslatedString | Lore description reference |
| `Properties` | StatsFunctors | Property functors |
| `Roll` | Conditions | Roll condition expression |
| `ShortDescription` | TranslatedString | Short description handle |
| `ShortDescriptionRef` | TranslatedString | Short description reference |
| `ShortDescriptionParams` | FixedString | Short description params |
| `Stack` | FixedString | Stack ID |
| `Success` | StatsFunctors | Functors on success |
| `TooltipAttackSave` | FixedString | Tooltip attack/save info |
| `TooltipDamageList` | FixedString | Tooltip damage info |
| `TooltipOnMiss` | FixedString | Tooltip miss info |
| `TooltipOnSave` | FixedString | Tooltip save info |
| `TooltipPermanentWarnings` | FixedString | Tooltip warning info |
| `TooltipStatusApply` | FixedString | Tooltip status info |

---

## Object

47 fields. Used by `Data/Object.txt`. Covers consumables, scrolls, keys, quest items, misc objects.

| Field | Type | Notes |
|-------|------|-------|
| `AcidResistance` | ResistanceFlags | Acid resistance |
| `AddToBottomBar` | YesNo | Add to bottom hotbar |
| `Armor` | ConstantInt | Object AC |
| `BludgeoningResistance` | ResistanceFlags | Bludgeoning resistance |
| `ColdResistance` | ResistanceFlags | Cold resistance |
| `ComboCategory` | FixedString | Crafting combo category |
| `DarkvisionRange` | ConstantInt | Darkvision range |
| `DefaultBoosts` | FixedString | Default boosts |
| `FallingHitEffect` | FixedString | Falling hit VFX |
| `FallingLandEffect` | FixedString | Falling land VFX |
| `FireResistance` | ResistanceFlags | Fire resistance |
| `Flags` | AttributeFlags | Object flags |
| `ForceResistance` | ResistanceFlags | Force resistance |
| `FOV` | ConstantInt | Field of view |
| `GameSize` | FixedString | Size override |
| `IgnoredByAI` | YesNo | AI ignores this object |
| `InventoryTab` | InventoryTabs | Inventory tab |
| `ItemUseType` | ItemUseTypes | Use type classification |
| `Level` | ConstantInt | Object level |
| `LightningResistance` | ResistanceFlags | Lightning resistance |
| `MaxAmount` | ConstantInt | Max stack |
| `MaxLevel` | ConstantInt | Max level |
| `MinAmount` | ConstantInt | Min amount |
| `MinimumDetectionRange` | ConstantInt | Min detection range |
| `MinLevel` | ConstantInt | Min level |
| `NecroticResistance` | ResistanceFlags | Necrotic resistance |
| `ObjectCategory` | FixedString | Object category |
| `PassivesOnEquip` | FixedString | Passives on equip |
| `PersonalStatusImmunities` | StatusIDs | Status immunities |
| `PiercingResistance` | ResistanceFlags | Piercing resistance |
| `PoisonResistance` | ResistanceFlags | Poison resistance |
| `Priority` | ConstantInt | Priority |
| `PsychicResistance` | ResistanceFlags | Psychic resistance |
| `RadiantResistance` | ResistanceFlags | Radiant resistance |
| `Rarity` | Rarity | Rarity tier |
| `Requirements` | Requirements | Use requirements |
| `RootTemplate` | FixedString | Template UUID |
| `Sight` | ConstantInt | Sight range |
| `SlashingResistance` | ResistanceFlags | Slashing resistance |
| `SoundSize` | FixedString | Sound category |
| `StatusInInventory` | FixedString | Inventory status |
| `SupplyValue` | ConstantInt | Camp supply value |
| `ThunderResistance` | ResistanceFlags | Thunder resistance |
| `Unique` | ConstantInt | Unique flag |
| `UseConditions` | Conditions | Use conditions |
| `UseCosts` | FixedString | Use costs |
| `ValueOverride` | ConstantInt | Value override |
| `ValueLevel` | ConstantInt | Value level |
| `ValueRounding` | ConstantInt | Value rounding |
| `ValueScale` | ConstantFloat | Value scale |
| `ValueUUID` | Guid | Value UUID |
| `VerticalFOV` | ConstantInt | Vertical FOV |
| `Vitality` | ConstantInt | Hit points |
| `Weight` | ConstantFloat | Weight |

---

## PassiveData

29 fields. Used by `Data/Passive.txt`.

| Field | Type | Notes |
|-------|------|-------|
| `BoostConditions` | Conditions | Conditions for boosts to apply |
| `BoostContext` | StatsFunctorContext | Context for boost evaluation |
| `Boosts` | FixedString | Boost expressions |
| `Conditions` | Conditions | Passive trigger conditions |
| `Description` | TranslatedString | Description handle |
| `DescriptionRef` | TranslatedString | Description reference |
| `DescriptionParams` | FixedString | Description parameters |
| `DisplayName` | TranslatedString | Display name handle |
| `DisplayNameRef` | TranslatedString | Display name reference |
| `DynamicAnimationTag` | Guid | Animation tag UUID |
| `EnabledConditions` | Conditions | When passive is enabled |
| `EnabledContext` | StatsFunctorContext | Enable evaluation context |
| `ExtraDescription` | TranslatedString | Extra description handle |
| `ExtraDescriptionRef` | TranslatedString | Extra description reference |
| `ExtraDescriptionParams` | FixedString | Extra description params |
| `Icon` | FixedString | Icon resource name |
| `LoreDescription` | TranslatedString | Lore description handle |
| `LoreDescriptionRef` | TranslatedString | Lore description reference |
| `PriorityOrder` | ConstantInt | Priority ordering |
| `Properties` | PassiveFlags | Passive property flags |
| `StatsFunctorContext` | StatsFunctorContext | Functor execution context |
| `StatsFunctors` | StatsFunctors | Functor expressions |
| `ToggleGroup` | FixedString | Toggle group ID |
| `ToggleOffContext` | StatsFunctorContext | Toggle off context |
| `ToggleOffEffect` | FixedString | Toggle off VFX |
| `ToggleOffFunctors` | StatsFunctors | Toggle off functors |
| `ToggleOnEffect` | FixedString | Toggle on VFX |
| `ToggleOnFunctors` | StatsFunctors | Toggle on functors |
| `TooltipConditionalDamage` | FixedString | Tooltip conditional damage |
| `TooltipPermanentWarnings` | FixedString | Tooltip warnings |
| `TooltipSave` | FixedString | Tooltip save info |
| `TooltipUseCosts` | FixedString | Tooltip use costs |

---

## SpellData

185 fields. Used by `Data/Spell_*.txt` (Projectile, ProjectileStrike, Rush, Shout, Target, Teleportation, Throw, Wall, Zone).

All spell subtypes share this field set. The `SpellType` field distinguishes the actual subtype.

| Field | Type | Notes |
|-------|------|-------|
| `SpellType` | FixedString | Subtype: Projectile, ProjectileStrike, Rush, Shout, Target, Teleportation, Throw, Wall, Zone |
| `Acceleration` | ConstantInt | Projectile acceleration |
| `AddRangeFromAbility` | FixedString | Extra range from ability |
| `AiCalculationSpellOverride` | FixedString | AI spell override |
| `AIFlags` | AIFlags | AI behavior flags |
| `AlternativeCastTextEvents` | FixedString | Alt cast text events |
| `AmountOfTargets` | FixedString | Target count |
| `Angle` | ConstantInt | Cone/zone angle |
| `SpellAnimationIntentType` | SpellAnimationIntentType | Animation intent |
| `AoEConditions` | TargetConditions | AoE target conditions |
| `AreaRadius` | ConstantInt | Area radius |
| `Autocast` | YesNo | Auto-cast enabled |
| `Base` | ConstantInt | Base value |
| `BeamEffect` | FixedString | Beam VFX |
| `CastEffect` | FixedString | Cast VFX |
| `CastEffectTextEvent` | FixedString | Cast VFX text event |
| `CastSound` | FixedString | Cast sound |
| `CastTargetHitDelay` | ConstantInt | Hit delay |
| `CastTextEvent` | FixedString | Cast text event |
| `CinematicArenaFlags` | CinematicArenaFlags | Camera flags |
| `CinematicArenaTimelineOverride` | Guid | Timeline override UUID |
| `CombatAIOverrideSpell` | FixedString | Combat AI override |
| `ConcentrationSpellID` | FixedString | Concentration link |
| `ContainerSpells` | FixedString | Container spell list |
| `Cooldown` | CooldownType | Cooldown type |
| `CycleConditions` | TargetConditions | Cycle target conditions |
| `Damage` | FixedString | Damage roll expression |
| `Damage Range` | ConstantInt | Damage range modifier |
| `DamageType` | Damage Type | Damage type |
| `DeathType` | Death Type | Death type on kill |
| `DelayRollDie` | DieType | Delay roll die |
| `DelayRollTarget` | ConstantInt | Delay roll target |
| `DelayTurnsCount` | ConstantInt | Delay turns |
| `Description` | TranslatedString | Description handle |
| `DescriptionRef` | TranslatedString | Description reference |
| `DescriptionParams` | FixedString | Description params |
| `DisappearEffect` | FixedString | Disappear VFX |
| `DisplayName` | TranslatedString | Display name handle |
| `DisplayNameRef` | TranslatedString | Display name reference |
| `Distribution` | ProjectileDistribution | Projectile distribution |
| `DualWieldingSpellAnimation` | FixedString | Dual wield animation |
| `DualWieldingUseCosts` | FixedString | Dual wield costs |
| `EndPosRadius` | ConstantInt | End position radius |
| `ExplodeRadius` | ConstantInt | Explosion radius |
| `ExtraDescription` | TranslatedString | Extra description |
| `ExtraDescriptionRef` | TranslatedString | Extra description ref |
| `ExtraDescriptionParams` | FixedString | Extra description params |
| `ExtraProjectileTargetConditions` | TargetConditions | Extra projectile targeting |
| `FemaleImpactEffects` | FixedString | Female-specific VFX |
| `FollowUpOriginalSpell` | FixedString | Follow-up original spell |
| `ForceTarget` | ConstantInt | Force target |
| `ForkChance` | ConstantInt | Fork chance % |
| `ForkingConditions` | TargetConditions | Fork conditions |
| `ForkLevels` | ConstantInt | Fork levels |
| `FrontOffset` | ConstantInt | Front offset |
| `FXScale` | ConstantInt | VFX scale |
| `Height` | ConstantInt | Wall/zone height |
| `HighlightConditions` | TargetConditions | Highlight conditions |
| `HitAnimationType` | HitAnimationType | Hit animation |
| `HitCosts` | FixedString | Hit costs |
| `HitDelay` | ConstantInt | Hit delay ms |
| `HitEffect` | FixedString | Hit VFX |
| `HitExtension` | ConstantFloat | Hit extension |
| `HitRadius` | ConstantFloat | Hit radius |
| `Icon` | FixedString | Icon name |
| `IgnoreTeleport` | YesNo | Ignore teleport |
| `ImpactEffect` | FixedString | Impact VFX |
| `InstrumentComponentCastSound` | FixedString | Instrument cast sound |
| `InstrumentComponentImpactSound` | FixedString | Instrument impact sound |
| `InstrumentComponentLoopingSound` | FixedString | Instrument loop sound |
| `InstrumentComponentPrepareSound` | FixedString | Instrument prepare sound |
| `InterruptPrototype` | FixedString | Interrupt prototype ID |
| `ItemWall` | FixedString | Item wall template |
| `ItemWallStatus` | FixedString | Item wall status |
| `JumpDelay` | ConstantInt | Jump delay |
| `Level` | ConstantInt | Spell level |
| `Lifetime` | ConstantInt | Effect lifetime |
| `LineOfSightFlags` | LineOfSightFlags | LoS flags |
| `Magic Cost` | ConstantInt | Magic cost |
| `MaleImpactEffects` | FixedString | Male-specific VFX |
| `MaxAttacks` | ConstantInt | Max attacks |
| `MaxDistance` | ConstantInt | Max distance |
| `MaxForkCount` | ConstantInt | Max fork targets |
| `MaxHitsPerTurn` | ConstantInt | Max hits per turn |
| `MaximumTargets` | ConstantInt | Max targets |
| `MaximumTotalTargetHP` | ConstantInt | Max total HP targeted |
| `MemorizationRequirements` | MemorizationRequirements | Memorization reqs |
| `Memory Cost` | ConstantInt | Memory cost |
| `MemoryCost` | ConstantInt | Memory cost (alt field) |
| `MinHitsPerTurn` | ConstantInt | Min hits per turn |
| `MinJumpDistance` | ConstantFloat | Min jump distance |
| `MovementSpeed` | ConstantInt | Movement speed |
| `MovingObjectSummonTemplate` | FixedString | Moving object template |
| `NextAttackChance` | ConstantInt | Next attack chance % |
| `NextAttackChanceDivider` | ConstantInt | Chance divider |
| `OnlyHit1Target` | ConstantInt | Single target limit |
| `OriginSpellFail` | StatsFunctors | Origin fail functors |
| `OriginSpellProperties` | StatsFunctors | Origin properties |
| `OriginSpellRoll` | RollConditions | Origin roll conditions |
| `OriginSpellSuccess` | StatsFunctors | Origin success functors |
| `OriginTargetConditions` | TargetConditions | Origin target conditions |
| `OverrideSpellLevel` | YesNo | Override spell level |
| `PositionEffect` | FixedString | Position VFX |
| `PowerLevel` | ConstantInt | Power level |
| `PrepareEffect` | FixedString | Prepare VFX |
| `PrepareEffectBone` | FixedString | Prepare VFX bone |
| `PrepareLoopSound` | FixedString | Prepare loop sound |
| `PrepareSound` | FixedString | Prepare sound |
| `PreviewCursor` | CursorMode | Preview cursor |
| `PreviewEffect` | FixedString | Preview VFX |
| `PreviewStrikeHits` | YesNo | Preview strike hits |
| `ProjectileCount` | FixedString | Projectile count |
| `ProjectileDelay` | ConstantInt | Projectile delay |
| `ProjectileSpells` | FixedString | Projectile spell list |
| `ProjectileTerrainOffset` | YesNo | Terrain offset |
| `ProjectileType` | ProjectileType | Projectile type |
| `Range` | ConstantInt | Cast range |
| `ReappearEffect` | FixedString | Reappear VFX |
| `ReappearEffectTextEvent` | FixedString | Reappear text event |
| `RechargeValues` | FixedString | Recharge values |
| `Requirement` | SpellRequirement | Weapon requirement |
| `RequirementConditions` | TargetConditions | Requirement conditions |
| `RequirementEvents` | StatusEvent | Requirement events |
| `Requirements` | Requirements | General requirements |
| `RitualCosts` | FixedString | Ritual costs |
| `RootSpellID` | FixedString | Root spell link |
| `SelectedCharacterEffect` | FixedString | Selected char VFX |
| `SelectedObjectEffect` | FixedString | Selected object VFX |
| `SelectedPositionEffect` | FixedString | Selected pos VFX |
| `Shape` | FixedString | AoE shape |
| `Sheathing` | SpellSheathing | Weapon sheathing |
| `ShortDescription` | TranslatedString | Short description |
| `ShortDescriptionRef` | TranslatedString | Short description ref |
| `ShortDescriptionParams` | FixedString | Short description params |
| `Shuffle` | YesNo | Shuffle targets |
| `SingleSource` | YesNo | Single source |
| `SourceLimbIndex` | ConstantInt | Source limb index |
| `SpawnEffect` | FixedString | Spawn VFX |
| `SpellActionType` | SpellActionType | Action type |
| `SpellActionTypePriority` | ConstantInt | Action type priority |
| `SpellAnimation` | FixedString | Animation ID |
| `SpellAnimationType` | SpellAnimationType | Animation type |
| `Spellbook` | FixedString | Spellbook ID |
| `SpellCategory` | SpellCategoryFlags | Category flags |
| `SpellContainerID` | FixedString | Container ID |
| `SpellEffect` | FixedString | Spell VFX |
| `SpellFail` | StatsFunctors | Fail functors |
| `SpellFlags` | SpellFlagList | Spell flags |
| `SpellJumpType` | SpellJumpType | Jump type |
| `SpellProperties` | StatsFunctors | Property functors |
| `SpellRoll` | RollConditions | Roll conditions |
| `SpellSchool` | SpellSchool | Magic school |
| `SpellSoundAftermathTrajectory` | FixedString | Aftermath trajectory sound |
| `SpellSoundMagnitude` | SpellSoundMagnitude | Sound magnitude |
| `SpellStyleGroup` | SpellStyleGroup | Style group |
| `SpellSuccess` | StatsFunctors | Success functors |
| `Stealth` | YesNo | Stealth spell |
| `SteerSpeedMultipler` | ConstantFloat | Steer speed multiplier |
| `StopAtFirstContact` | ConstantInt | Stop at first hit |
| `StormEffect` | FixedString | Storm VFX |
| `StrikeCount` | ConstantInt | Strike count |
| `SurfaceGrowInterval` | ConstantInt | Surface grow interval |
| `SurfaceGrowStep` | ConstantInt | Surface grow step |
| `SurfaceLifetime` | ConstantInt | Surface lifetime |
| `SurfaceRadius` | ConstantInt | Surface radius |
| `SurfaceType` | Surface Type | Surface type |
| `TargetCeiling` | FixedString | Target ceiling |
| `TargetConditions` | TargetConditions | Target conditions |
| `TargetEffect` | FixedString | Target VFX |
| `TargetFloor` | FixedString | Target floor |
| `TargetGroundEffect` | FixedString | Target ground VFX |
| `TargetHitEffect` | FixedString | Target hit VFX |
| `TargetProjectiles` | YesNo | Target projectiles |
| `TargetRadius` | FixedString | Target radius |
| `TargetSound` | FixedString | Target sound |
| `TeleportDelay` | ConstantInt | Teleport delay |
| `TeleportSelf` | YesNo | Teleport self |
| `TeleportSurface` | YesNo | Teleport to surface |
| `Template` | FixedString | Template ID |
| `ThrowableSpellFail` | StatsFunctors | Throwable fail functors |
| `ThrowableSpellProperties` | StatsFunctors | Throwable properties |
| `ThrowableSpellRoll` | RollConditions | Throwable roll conditions |
| `ThrowableSpellSuccess` | StatsFunctors | Throwable success functors |
| `ThrowableTargetConditions` | TargetConditions | Throwable targeting |
| `ThrowOrigin` | ThrowOrigin | Throw origin |
| `TooltipAttackSave` | FixedString | Tooltip attack/save |
| `TooltipDamageList` | FixedString | Tooltip damage list |
| `TooltipOnMiss` | FixedString | Tooltip on miss |
| `TooltipOnSave` | FixedString | Tooltip on save |
| `TooltipPermanentWarnings` | FixedString | Tooltip warnings |
| `TooltipSpellDCAbilities` | AbilityFlags | Tooltip DC abilities |
| `TooltipStatusApply` | FixedString | Tooltip status apply |
| `TooltipUpcastDescription` | Guid | Upcast description UUID |
| `TooltipUpcastDescriptionParams` | FixedString | Upcast description params |
| `Trajectories` | FixedString | Trajectory data |
| `UseCosts` | FixedString | Use costs |
| `UseWeaponDamage` | YesNo | Use weapon damage |
| `UseWeaponProperties` | YesNo | Use weapon properties |
| `VerbalIntent` | VerbalIntent | Verbal intent |
| `VocalComponentSound` | FixedString | Vocal component sound |
| `WallEndEffect` | FixedString | Wall end VFX |
| `WallStartEffect` | FixedString | Wall start VFX |
| `WeaponBones` | FixedString | Weapon bones |
| `WeaponTypes` | WeaponFlags | Weapon type flags |

---

## StatusData

110 fields. Used by `Data/Status_*.txt` (BOOST, DEACTIVATED, DOWNED, EFFECT, FEAR, HEAL, INCAPACITATED, INVISIBLE, KNOCKED_DOWN, POLYMORPHED, SNEAKING).

All status subtypes share this field set. The `StatusType` field distinguishes the actual subtype.

| Field | Type | Notes |
|-------|------|-------|
| `StatusType` | FixedString | Subtype: BOOST, DEACTIVATED, DOWNED, EFFECT, FEAR, HEAL, INCAPACITATED, INVISIBLE, KNOCKED_DOWN, POLYMORPHED, SNEAKING |
| `AbsorbSurfaceRange` | ConstantInt | Surface absorption range |
| `AbsorbSurfaceType` | FixedString | Surface type to absorb |
| `AiCalculationSpellOverride` | FixedString | AI spell override |
| `AnimationEnd` | FixedString | End animation |
| `AnimationLoop` | FixedString | Loop animation |
| `AnimationStart` | FixedString | Start animation |
| `ApplyEffect` | FixedString | Apply VFX |
| `AuraFlags` | AuraFlags | Aura behavior flags |
| `AuraFX` | FixedString | Aura VFX |
| `AuraRadius` | ConstantInt | Aura radius |
| `AuraStatuses` | StatsFunctors | Aura status functors |
| `BeamEffect` | FixedString | Beam VFX |
| `BonusFromSkill` | Skill | Skill bonus source |
| `Boosts` | FixedString | Boost expressions |
| `Charges` | ConstantInt | Status charges |
| `DefendTargetPosition` | YesNo | Defend target pos |
| `Description` | TranslatedString | Description handle |
| `DescriptionRef` | TranslatedString | Description reference |
| `DescriptionParams` | FixedString | Description params |
| `DieAction` | FixedString | Action on death |
| `DisableInteractions` | YesNo | Disable interactions |
| `DisplayName` | TranslatedString | Display name |
| `DisplayNameRef` | TranslatedString | Display name ref |
| `DynamicAnimationTag` | Guid | Animation tag UUID |
| `EndEffect` | FixedString | End VFX |
| `ForceStackOverwrite` | YesNo | Force stack overwrite |
| `FormatColor` | FormatStringColor | Display color |
| `FreezeTime` | ConstantInt | Freeze time |
| `HealEffectId` | FixedString | Heal effect ID |
| `HealMultiplier` | ConstantInt | Heal multiplier |
| `HealStat` | StatusHealType | What to heal |
| `HealType` | HealValueType | How to calculate heal |
| `HealValue` | FixedString | Heal value expression |
| `HideOverheadUI` | ConstantInt | Hide overhead UI |
| `HitAnimationType` | HitAnimationType | Hit animation type |
| `Icon` | FixedString | Icon name |
| `ImmuneFlag` | AttributeFlags | Immunity flags |
| `Instant` | YesNo | Instant application |
| `IsUnique` | ConstantInt | Unique status flag |
| `Items` | FixedString | Item references |
| `LeaveAction` | FixedString | Leave action |
| `LEDEffect` | LEDEffectType | LED peripheral effect |
| `ManagedStatusEffectGroup` | FixedString | Effect group |
| `ManagedStatusEffectType` | ManagedStatusEffectType | Positive/Negative |
| `Material` | FixedString | Material override |
| `MaterialApplyArmor` | YesNo | Apply to armor |
| `MaterialApplyBody` | YesNo | Apply to body |
| `MaterialApplyNormalMap` | YesNo | Apply normal map |
| `MaterialApplyWeapon` | YesNo | Apply to weapon |
| `MaterialFadeAmount` | ConstantInt | Material fade |
| `MaterialOverlayOffset` | ConstantInt | Material offset |
| `MaterialParameters` | FixedString | Material params |
| `MaterialType` | MaterialType | Material type |
| `MeshEffect` | FixedString | Mesh effect |
| `Necromantic` | YesNo | Necromantic flag |
| `NumStableFailed` | ConstantInt | Failed death saves |
| `NumStableSuccess` | ConstantInt | Successful death saves |
| `OnApplyConditions` | Conditions | Apply conditions |
| `OnApplyFail` | StatsFunctors | Apply failure functors |
| `OnApplyFunctors` | StatsFunctors | Apply functors |
| `OnApplyRoll` | Conditions | Apply roll conditions |
| `OnApplySuccess` | StatsFunctors | Apply success functors |
| `OnRemoveFail` | StatsFunctors | Remove failure functors |
| `OnRemoveFunctors` | StatsFunctors | Remove functors |
| `OnRemoveRoll` | Conditions | Remove roll conditions |
| `OnRemoveSuccess` | StatsFunctors | Remove success functors |
| `OnRollsFailed` | StatsFunctors | All rolls failed |
| `OnSuccess` | StatsFunctors | General success |
| `OnTickFail` | StatsFunctors | Tick failure functors |
| `OnTickRoll` | Conditions | Tick roll conditions |
| `OnTickSuccess` | StatsFunctors | Tick success functors |
| `Passives` | FixedString | Granted passives |
| `PeaceOnly` | YesNo | Peace only |
| `PerformEventName` | FixedString | Performance event |
| `PlayerHasTag` | FixedString | Player tag check |
| `PlayerSameParty` | YesNo | Same party check |
| `PolymorphResult` | FixedString | Polymorph result |
| `Projectile` | FixedString | Projectile template |
| `Radius` | ConstantInt | Effect radius |
| `RemoveConditions` | Conditions | Remove conditions |
| `RemoveEvents` | StatusEvent | Remove event triggers |
| `ResetCooldowns` | FixedString | Cooldowns to reset |
| `RetainSpells` | FixedString | Retained spells |
| `Rules` | Guid | Rules UUID |
| `Sheathing` | StatusSheathing | Weapon sheathing |
| `SoundLoop` | FixedString | Loop sound |
| `SoundStart` | FixedString | Start sound |
| `SoundStop` | FixedString | Stop sound |
| `SoundVocalEnd` | SoundVocalType | Vocal end sound |
| `SoundVocalLoop` | SoundVocalType | Vocal loop sound |
| `SoundVocalStart` | SoundVocalType | Vocal start sound |
| `Spells` | FixedString | Granted spells |
| `SplatterBloodAmount` | ConstantFloat | Blood splatter amount |
| `SplatterDirtAmount` | ConstantFloat | Dirt splatter amount |
| `SplatterSweatAmount` | ConstantFloat | Sweat splatter amount |
| `StableRoll` | FixedString | Death save roll |
| `StableRollDC` | ConstantInt | Death save DC |
| `StackId` | FixedString | Stack identifier |
| `StackPriority` | ConstantInt | Stack priority |
| `StackType` | StatusStackType | Stacking behavior |
| `StatsId` | FixedString | Stats entry reference |
| `StatusEffect` | FixedString | Status VFX |
| `StatusEffectOnTurn` | FixedString | Per-turn VFX |
| `StatusEffectOverride` | FixedString | VFX override |
| `StatusEffectOverrideForItems` | FixedString | Item VFX override |
| `StatusGroups` | StatusGroupFlags | Status group membership |
| `StatusPropertyFlags` | StatusPropertyFlags | Status property flags |
| `StatusSoundState` | FixedString | Sound state |
| `StillAnimationPriority` | StillAnimPriority | Still animation priority |
| `StillAnimationType` | StatusAnimationType | Still animation type |
| `SurfaceChange` | FixedString | Surface change |
| `TargetConditions` | FixedString | Target conditions |
| `TargetEffect` | FixedString | Target VFX |
| `TemplateID` | FixedString | Template ID |
| `TickFunctors` | StatsFunctors | Per-tick functors |
| `TickType` | TickType | When to tick |
| `Toggle` | YesNo | Toggleable |
| `TooltipDamage` | FixedString | Tooltip damage |
| `TooltipPermanentWarnings` | FixedString | Tooltip warnings |
| `TooltipSave` | FixedString | Tooltip save info |
| `UseLyingPickingState` | YesNo | Use lying state |
| `WeaponOverride` | FixedString | Weapon override |

---

## Weapon

60 fields. Used by `Data/Weapon.txt`.

| Field | Type | Notes |
|-------|------|-------|
| `Boosts` | FixedString | Boost expressions |
| `BoostsOnEquipMainHand` | FixedString | Main hand equip boosts |
| `BoostsOnEquipOffHand` | FixedString | Off hand equip boosts |
| `Charges` | ConstantInt | Charge count |
| `ColorPresetResource` | FixedString | Color preset UUID |
| `ComboCategory` | FixedString | Combo category |
| `Damage` | FixedString | Damage roll expression |
| `Damage Range` | ConstantInt | Damage range modifier |
| `Damage Type` | Damage Type | Damage type |
| `DefaultBoosts` | FixedString | Default boosts |
| `Durability` | ConstantInt | Durability HP |
| `DurabilityDegradeSpeed` | Qualifier | Degradation speed |
| `ExtraProperties` | FixedString | Extra properties |
| `FallingHitEffect` | FixedString | Falling hit VFX |
| `FallingLandEffect` | FixedString | Falling land VFX |
| `Flags` | AttributeFlags | Attribute flags |
| `GameSize` | FixedString | Size override |
| `IgnoreVisionBlock` | YesNo | Ignore vision block |
| `InventoryTab` | InventoryTabs | Inventory tab |
| `ItemColor` | FixedString | Color preset name |
| `ItemGroup` | FixedString | Item group |
| `Level` | ConstantInt | Weapon level |
| `MaxAmount` | ConstantInt | Max stack |
| `MaxCharges` | ConstantInt | Max charges |
| `MaxLevel` | ConstantInt | Max level |
| `MinAmount` | ConstantInt | Min amount |
| `MinLevel` | ConstantInt | Min level |
| `NeedsIdentification` | YesNo | Needs Identify |
| `ObjectCategory` | FixedString | Object category |
| `PassivesMainHand` | FixedString | Main hand passives |
| `PassivesOffHand` | FixedString | Off hand passives |
| `PassivesOnEquip` | FixedString | Equip passives |
| `PersonalStatusImmunities` | StatusIDs | Status immunities |
| `Priority` | ConstantInt | Priority |
| `Proficiency Group` | ProficiencyGroupFlags | Proficiency group |
| `Projectile` | FixedString | Projectile template |
| `Rarity` | Rarity | Rarity tier |
| `Requirements` | Requirements | Requirements |
| `RootTemplate` | FixedString | Template UUID |
| `Slot` | Itemslot | Equipment slot |
| `SoundSize` | FixedString | Sound category |
| `Spells` | FixedString | Granted spells |
| `StatusInInventory` | FixedString | Inventory status |
| `StatusOnEquip` | FixedString | Equip status |
| `SupplyValue` | ConstantInt | Supply value |
| `Tags` | FixedString | Tag UUIDs |
| `Unique` | ConstantInt | Unique flag |
| `UniqueWeaponSoundSwitch` | FixedString | Unique weapon sound |
| `UseConditions` | Conditions | Use conditions |
| `UseCosts` | FixedString | Use costs |
| `ValueOverride` | ConstantInt | Value override |
| `ValueLevel` | ConstantInt | Value level |
| `ValueRounding` | ConstantInt | Value rounding |
| `ValueScale` | ConstantFloat | Value scale |
| `ValueUUID` | Guid | Value UUID |
| `VersatileDamage` | FixedString | Versatile damage roll |
| `Weapon Group` | Weapon Group | Weapon group |
| `Weapon Properties` | WeaponFlags | Weapon properties |
| `WeaponFunctors` | StatsFunctors | Weapon functors |
| `WeaponRange` | ConstantInt | Weapon range |
| `Weight` | ConstantFloat | Weight |

---

## Cross-References

| From | To | Via |
|------|----|----|
| Value types (e.g., `Damage Type`, `ArmorType`) | [ValueLists.txt](ValueLists.md) | Enum name match |
| Type-specific field docs | [Type files](../types/) | [Weapon](../types/Weapon.md), [Armor](../types/Armor.md), [SpellData](../types/SpellData.md), etc. |
| `StatsFunctors` typed fields | [functors-boosts.md](../reference/functors-boosts.md) | Functor/boost signatures |
| `StatsFunctorContext` typed fields | [functor-contexts.md](../reference/functor-contexts.md) | Context entity mapping |

## Caveats

- **Shared fields across types**: Many fields (e.g., `RootTemplate`, `Weight`, `Rarity`, `ValueUUID`) appear in multiple types with identical semantics. The type files document per-type observations.
- **Field name typos**: Some field names contain deliberate typos matching the game's source: `SteerSpeedMultipler` (missing 'i'), `Memory Cost` (space) vs `MemoryCost` (no space).
- **Value types are not enforcement**: `FixedString` is a catch-all for complex expressions (boosts, functors, conditions). The Modifiers.txt type only declares the parser — actual validation happens at runtime.
- **Unobserved fields**: Not all fields defined here are used in vanilla data. The type-specific docs flag which fields are unobserved but available for mods.
