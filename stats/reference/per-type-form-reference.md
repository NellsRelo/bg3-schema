# Per-Type Form Reference

> **Purpose**: Maps every stat data type to its complete field set, observed boosts, and observed functors.
> Use this when building forms/editors for individual stat types — it tells you exactly what fields, boost names, and functor names to support per type.
>
> **Source data**: Extracted from vanilla BG3 data files across Shared, Gustav, and GustavX packs.
> Field definitions from [Modifiers.md](../formats/Modifiers.md). Boost/functor definitions from [functors-boosts.md](functors-boosts.md).

## Summary

| Type | Fields | Boost Fields | Unique Boosts | Functor Fields | Unique Functors |
|------|--------|-------------|---------------|----------------|-----------------|
| [Weapon](#weapon) | 60 | 3 | 10 | 1 | 2 |
| [Armor](#armor) | 52 | 1 | 13 | 0 | 0 |
| [Character](#character) | 58 | 1 | 9 | 0 | 0 |
| [Object](#object) | 47 | 1 | 5 | 0 | 0 |
| [SpellData](#spelldata) | 185 | 0 | 0 | 5 | 26 |
| [StatusData](#statusdata) | 110 | 1 | 88 | 10 | 22 |
| [PassiveData](#passivedata) | 29 | 1 | 53 | 4 | 12 |
| [InterruptData](#interruptdata) | 30 | 0 | 0 | 3 | 11 |
| [CriticalHitTypeData](#criticalhittypedata) | 13 | 0 | 0 | 0 | 0 |

---

## Weapon

> 60 fields defined in Modifiers. 40 observed in vanilla data.
> **Data file**: `Weapon.txt`

### Fields

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

### Boost Fields

| Field | Purpose |
|-------|---------|
| `Boosts` | General boosts (always active) |
| `BoostsOnEquipMainHand` | Boosts when equipped in main hand |
| `DefaultBoosts` | Default boosts applied automatically |

### Boosts Used in Vanilla (10)

`CannotBeDisarmed` · `HiddenDuringCinematic` · `IgnoreResistance` · `Proficiency` · `Resistance` · `Skill` · `UnlockSpell` · `WeaponDamage` · `WeaponEnchantment` · `WeaponProperty`

### Functor Fields

| Field | Purpose |
|-------|---------|
| `WeaponFunctors` | Functors executed on weapon hit |

### Functors Used in Vanilla (2)

`ApplyStatus` · `SurfaceChange`

---

## Armor

> 52 fields defined in Modifiers. 36 observed in vanilla data.
> **Data file**: `Armor.txt`

### Fields

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

### Boost Fields

| Field | Purpose |
|-------|---------|
| `Boosts` | General boosts (always active while equipped) |

### Boosts Used in Vanilla (13)

`Ability` · `AbilityOverrideMinimum` · `AC` · `ActionResource` · `Advantage` · `CriticalHit` · `Disadvantage` · `ProficiencyBonus` · `Resistance` · `RollBonus` · `Skill` · `Tag` · `UnlockSpell`

### Functor Fields

None — Armor does not have functor-accepting fields.

---

## Character

> 58 fields defined in Modifiers. 51 observed in vanilla data.
> **Data file**: `Character.txt`

### Fields

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

### Boost Fields

| Field | Purpose |
|-------|---------|
| `DefaultBoosts` | Default boosts for the character |

### Boosts Used in Vanilla (9)

`ActionResource` · `ActionResourceBlock` · `Attribute` · `BlockRegainHP` · `CriticalHit` · `DialogueBlock` · `Invulnerable` · `ProficiencyBonus` · `Skill`

### Functor Fields

None — Character does not have functor-accepting fields.

---

## Object

> 47 fields defined in Modifiers. 50 observed in vanilla data.
> **Data file**: `Object.txt`

### Fields

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

### Boost Fields

| Field | Purpose |
|-------|---------|
| `DefaultBoosts` | Default boosts for the object |

### Boosts Used in Vanilla (5)

`CriticalHit` · `DamageReduction` · `IgnoreFallDamage` · `Invulnerable` · `Tag`

### Functor Fields

None — Object does not have functor-accepting fields.

---

## SpellData

> 185 fields defined in Modifiers. 140 observed in vanilla data.
> **Data files**: `Spell_Projectile.txt`, `Spell_ProjectileStrike.txt`, `Spell_Rush.txt`, `Spell_Shout.txt`, `Spell_Target.txt`, `Spell_Teleportation.txt`, `Spell_Throw.txt`, `Spell_Wall.txt`, `Spell_Zone.txt`

### Fields

| Field | Type | Observed |
|-------|------|:--------:|
| `Acceleration` | ConstantInt | ✓ |
| `AddRangeFromAbility` | FixedString | ✓ |
| `AiCalculationSpellOverride` | FixedString | ✓ |
| `AIFlags` | AIFlags | ✓ |
| `AlternativeCastTextEvents` | FixedString | ✓ |
| `AmountOfTargets` | FixedString | ✓ |
| `Angle` | ConstantInt | ✓ |
| `AoEConditions` | TargetConditions | ✓ |
| `AreaRadius` | ConstantInt | ✓ |
| `Autocast` | YesNo | ✓ |
| `Base` | ConstantInt | ✓ |
| `BeamEffect` | FixedString | ✓ |
| `CastEffect` | FixedString | ✓ |
| `CastEffectTextEvent` | FixedString | |
| `CastSound` | FixedString | ✓ |
| `CastTargetHitDelay` | ConstantInt | ✓ |
| `CastTextEvent` | FixedString | ✓ |
| `CinematicArenaFlags` | CinematicArenaFlags | ✓ |
| `CinematicArenaTimelineOverride` | Guid | |
| `CombatAIOverrideSpell` | FixedString | ✓ |
| `ConcentrationSpellID` | FixedString | ✓ |
| `ContainerSpells` | FixedString | ✓ |
| `Cooldown` | CooldownType | ✓ |
| `CycleConditions` | TargetConditions | ✓ |
| `Damage` | FixedString | ✓ |
| `Damage Range` | ConstantInt | ✓ |
| `DamageType` | Damage Type | ✓ |
| `DeathType` | Death Type | ✓ |
| `DelayRollDie` | DieType | |
| `DelayRollTarget` | ConstantInt | |
| `DelayTurnsCount` | ConstantInt | |
| `Description` | TranslatedString | ✓ |
| `DescriptionParams` | FixedString | ✓ |
| `DescriptionRef` | TranslatedString | |
| `DisappearEffect` | FixedString | ✓ |
| `DisplayName` | TranslatedString | ✓ |
| `DisplayNameRef` | TranslatedString | |
| `Distribution` | ProjectileDistribution | ✓ |
| `DualWieldingSpellAnimation` | FixedString | ✓ |
| `DualWieldingUseCosts` | FixedString | ✓ |
| `EndPosRadius` | ConstantInt | |
| `ExplodeRadius` | ConstantInt | ✓ |
| `ExtraDescription` | TranslatedString | ✓ |
| `ExtraDescriptionParams` | FixedString | ✓ |
| `ExtraDescriptionRef` | TranslatedString | |
| `ExtraProjectileTargetConditions` | TargetConditions | ✓ |
| `FemaleImpactEffects` | FixedString | |
| `FollowUpOriginalSpell` | FixedString | ✓ |
| `ForceTarget` | ConstantInt | |
| `ForkChance` | ConstantInt | ✓ |
| `ForkingConditions` | TargetConditions | ✓ |
| `ForkLevels` | ConstantInt | ✓ |
| `FrontOffset` | ConstantInt | ✓ |
| `FXScale` | ConstantInt | |
| `Height` | ConstantInt | ✓ |
| `HighlightConditions` | TargetConditions | ✓ |
| `HitAnimationType` | HitAnimationType | ✓ |
| `HitCosts` | FixedString | ✓ |
| `HitDelay` | ConstantInt | |
| `HitEffect` | FixedString | ✓ |
| `HitExtension` | ConstantFloat | ✓ |
| `HitRadius` | ConstantFloat | ✓ |
| `Icon` | FixedString | ✓ |
| `IgnoreTeleport` | YesNo | |
| `ImpactEffect` | FixedString | ✓ |
| `InstrumentComponentCastSound` | FixedString | ✓ |
| `InstrumentComponentImpactSound` | FixedString | ✓ |
| `InstrumentComponentLoopingSound` | FixedString | ✓ |
| `InstrumentComponentPrepareSound` | FixedString | ✓ |
| `InterruptPrototype` | FixedString | ✓ |
| `ItemWall` | FixedString | |
| `ItemWallStatus` | FixedString | |
| `JumpDelay` | ConstantInt | |
| `Level` | ConstantInt | ✓ |
| `Lifetime` | ConstantInt | |
| `LineOfSightFlags` | LineOfSightFlags | ✓ |
| `Magic Cost` | ConstantInt | |
| `MaleImpactEffects` | FixedString | |
| `MaxAttacks` | ConstantInt | |
| `MaxDistance` | ConstantInt | |
| `MaxForkCount` | ConstantInt | ✓ |
| `MaxHitsPerTurn` | ConstantInt | |
| `MaximumTargets` | ConstantInt | ✓ |
| `MaximumTotalTargetHP` | ConstantInt | ✓ |
| `MemorizationRequirements` | MemorizationRequirements | |
| `Memory Cost` | ConstantInt | |
| `MemoryCost` | ConstantInt | ✓ |
| `MinHitsPerTurn` | ConstantInt | |
| `MinJumpDistance` | ConstantFloat | ✓ |
| `MovementSpeed` | ConstantInt | ✓ |
| `MovingObjectSummonTemplate` | FixedString | |
| `NextAttackChance` | ConstantInt | |
| `NextAttackChanceDivider` | ConstantInt | |
| `OnlyHit1Target` | ConstantInt | ✓ |
| `OriginSpellFail` | StatsFunctors | |
| `OriginSpellProperties` | StatsFunctors | ✓ |
| `OriginSpellRoll` | RollConditions | |
| `OriginSpellSuccess` | StatsFunctors | |
| `OriginTargetConditions` | TargetConditions | ✓ |
| `OverrideSpellLevel` | YesNo | |
| `PositionEffect` | FixedString | ✓ |
| `PowerLevel` | ConstantInt | ✓ |
| `PrepareEffect` | FixedString | ✓ |
| `PrepareEffectBone` | FixedString | |
| `PrepareLoopSound` | FixedString | ✓ |
| `PrepareSound` | FixedString | ✓ |
| `PreviewCursor` | CursorMode | ✓ |
| `PreviewEffect` | FixedString | ✓ |
| `PreviewStrikeHits` | YesNo | |
| `ProjectileCount` | FixedString | ✓ |
| `ProjectileDelay` | ConstantInt | ✓ |
| `ProjectileSpells` | FixedString | |
| `ProjectileTerrainOffset` | YesNo | ✓ |
| `ProjectileType` | ProjectileType | ✓ |
| `Range` | ConstantInt | ✓ |
| `ReappearEffect` | FixedString | |
| `ReappearEffectTextEvent` | FixedString | |
| `RechargeValues` | FixedString | ✓ |
| `Requirement` | SpellRequirement | |
| `RequirementConditions` | TargetConditions | ✓ |
| `RequirementEvents` | StatusEvent | ✓ |
| `Requirements` | Requirements | ✓ |
| `RitualCosts` | FixedString | ✓ |
| `RootSpellID` | FixedString | ✓ |
| `SelectedCharacterEffect` | FixedString | |
| `SelectedObjectEffect` | FixedString | |
| `SelectedPositionEffect` | FixedString | |
| `Shape` | FixedString | ✓ |
| `Sheathing` | SpellSheathing | ✓ |
| `ShortDescription` | TranslatedString | |
| `ShortDescriptionParams` | FixedString | |
| `ShortDescriptionRef` | TranslatedString | |
| `Shuffle` | YesNo | |
| `SingleSource` | YesNo | |
| `SourceLimbIndex` | ConstantInt | ✓ |
| `SpawnEffect` | FixedString | |
| `SpellActionType` | SpellActionType | ✓ |
| `SpellActionTypePriority` | ConstantInt | |
| `SpellAnimation` | FixedString | ✓ |
| `SpellAnimationIntentType` | SpellAnimationIntentType | |
| `SpellAnimationType` | SpellAnimationType | |
| `Spellbook` | FixedString | |
| `SpellCategory` | SpellCategoryFlags | ✓ |
| `SpellContainerID` | FixedString | ✓ |
| `SpellEffect` | FixedString | ✓ |
| `SpellFail` | StatsFunctors | ✓ |
| `SpellFlags` | SpellFlagList | ✓ |
| `SpellJumpType` | SpellJumpType | ✓ |
| `SpellProperties` | StatsFunctors | ✓ |
| `SpellRoll` | RollConditions | ✓ |
| `SpellSchool` | SpellSchool | ✓ |
| `SpellSoundAftermathTrajectory` | FixedString | |
| `SpellSoundMagnitude` | SpellSoundMagnitude | ✓ |
| `SpellStyleGroup` | SpellStyleGroup | ✓ |
| `SpellSuccess` | StatsFunctors | ✓ |
| `SpellType` | FixedString | |
| `Stealth` | YesNo | |
| `SteerSpeedMultipler` | ConstantFloat | ✓ |
| `StopAtFirstContact` | ConstantInt | ✓ |
| `StormEffect` | FixedString | |
| `StrikeCount` | ConstantInt | |
| `SurfaceGrowInterval` | ConstantInt | ✓ |
| `SurfaceGrowStep` | ConstantInt | ✓ |
| `SurfaceLifetime` | ConstantInt | ✓ |
| `SurfaceRadius` | ConstantInt | |
| `SurfaceType` | Surface Type | ✓ |
| `TargetCeiling` | FixedString | ✓ |
| `TargetConditions` | TargetConditions | ✓ |
| `TargetEffect` | FixedString | ✓ |
| `TargetFloor` | FixedString | ✓ |
| `TargetGroundEffect` | FixedString | ✓ |
| `TargetHitEffect` | FixedString | ✓ |
| `TargetProjectiles` | YesNo | ✓ |
| `TargetRadius` | FixedString | ✓ |
| `TargetSound` | FixedString | ✓ |
| `TeleportDelay` | ConstantInt | |
| `TeleportSelf` | YesNo | ✓ |
| `TeleportSurface` | YesNo | ✓ |
| `Template` | FixedString | ✓ |
| `ThrowableSpellFail` | StatsFunctors | |
| `ThrowableSpellProperties` | StatsFunctors | |
| `ThrowableSpellRoll` | RollConditions | |
| `ThrowableSpellSuccess` | StatsFunctors | ✓ |
| `ThrowableTargetConditions` | TargetConditions | |
| `ThrowOrigin` | ThrowOrigin | |
| `TooltipAttackSave` | FixedString | ✓ |
| `TooltipDamageList` | FixedString | ✓ |
| `TooltipOnMiss` | FixedString | ✓ |
| `TooltipOnSave` | FixedString | ✓ |
| `TooltipPermanentWarnings` | FixedString | ✓ |
| `TooltipSpellDCAbilities` | AbilityFlags | ✓ |
| `TooltipStatusApply` | FixedString | ✓ |
| `TooltipUpcastDescription` | Guid | ✓ |
| `TooltipUpcastDescriptionParams` | FixedString | ✓ |
| `Trajectories` | FixedString | ✓ |
| `UseCosts` | FixedString | ✓ |
| `UseWeaponDamage` | YesNo | |
| `UseWeaponProperties` | YesNo | |
| `VerbalIntent` | VerbalIntent | ✓ |
| `VocalComponentSound` | FixedString | ✓ |
| `WallEndEffect` | FixedString | |
| `WallStartEffect` | FixedString | |
| `WeaponBones` | FixedString | |
| `WeaponTypes` | WeaponFlags | ✓ |

### Boost Fields

None — SpellData does not have boost-accepting fields.

### Functor Fields

| Field | Purpose |
|-------|---------|
| `SpellProperties` | Main spell property functors |
| `SpellSuccess` | Functors on successful hit/save |
| `SpellFail` | Functors on miss/failed save |
| `OriginSpellProperties` | Origin-specific property functors |
| `ThrowableSpellSuccess` | Throwable success functors |

### Functors Used in Vanilla (26)

`ApplyEquipmentStatus` · `ApplyStatus` · `BreakConcentration` · `CreateExplosion` · `CreateSurface` · `DealDamage` · `ExecuteWeaponFunctors` · `Force` · `RegainHitPoints` · `RemoveStatus` · `RestoreResource` · `Resurrect` · `SetStatusDuration` · `ShortRest` · `Spawn` · `SpawnExtraProjectiles` · `Stabilize` · `Summon` · `SummonInInventory` · `SurfaceChange` · `SurfaceClearLayer` · `SwitchDeathType` · `TeleportSource` · `Unlock` · `Unsummon` · `UseActionResource`

---

## StatusData

> 110 fields defined in Modifiers. 88 observed in vanilla data.
> **Data files**: `Status_BOOST.txt`, `Status_DEACTIVATED.txt`, `Status_DOWNED.txt`, `Status_EFFECT.txt`, `Status_FEAR.txt`, `Status_HEAL.txt`, `Status_INCAPACITATED.txt`, `Status_INVISIBLE.txt`, `Status_KNOCKED_DOWN.txt`, `Status_POLYMORPHED.txt`, `Status_SNEAKING.txt`

### Fields

| Field | Type | Observed |
|-------|------|:--------:|
| `AbsorbSurfaceRange` | ConstantInt | |
| `AbsorbSurfaceType` | FixedString | |
| `AiCalculationSpellOverride` | FixedString | |
| `AnimationEnd` | FixedString | ✓ |
| `AnimationLoop` | FixedString | ✓ |
| `AnimationStart` | FixedString | ✓ |
| `ApplyEffect` | FixedString | ✓ |
| `AuraFlags` | AuraFlags | ✓ |
| `AuraFX` | FixedString | |
| `AuraRadius` | ConstantInt | ✓ |
| `AuraStatuses` | StatsFunctors | ✓ |
| `BeamEffect` | FixedString | ✓ |
| `BonusFromSkill` | Skill | |
| `Boosts` | FixedString | ✓ |
| `Charges` | ConstantInt | |
| `DefendTargetPosition` | YesNo | |
| `Description` | TranslatedString | ✓ |
| `DescriptionParams` | FixedString | ✓ |
| `DescriptionRef` | TranslatedString | |
| `DieAction` | FixedString | |
| `DisableInteractions` | YesNo | ✓ |
| `DisplayName` | TranslatedString | ✓ |
| `DisplayNameRef` | TranslatedString | |
| `DynamicAnimationTag` | Guid | ✓ |
| `EndEffect` | FixedString | |
| `ForceStackOverwrite` | YesNo | |
| `FormatColor` | FormatStringColor | ✓ |
| `FreezeTime` | ConstantInt | ✓ |
| `HealEffectId` | FixedString | |
| `HealMultiplier` | ConstantInt | |
| `HealStat` | StatusHealType | ✓ |
| `HealType` | HealValueType | |
| `HealValue` | FixedString | ✓ |
| `HideOverheadUI` | ConstantInt | ✓ |
| `HitAnimationType` | HitAnimationType | ✓ |
| `Icon` | FixedString | ✓ |
| `ImmuneFlag` | AttributeFlags | |
| `Instant` | YesNo | ✓ |
| `IsUnique` | ConstantInt | ✓ |
| `Items` | FixedString | |
| `LeaveAction` | FixedString | |
| `LEDEffect` | LEDEffectType | |
| `ManagedStatusEffectGroup` | FixedString | ✓ |
| `ManagedStatusEffectType` | ManagedStatusEffectType | ✓ |
| `Material` | FixedString | ✓ |
| `MaterialApplyArmor` | YesNo | ✓ |
| `MaterialApplyBody` | YesNo | ✓ |
| `MaterialApplyNormalMap` | YesNo | ✓ |
| `MaterialApplyWeapon` | YesNo | ✓ |
| `MaterialFadeAmount` | ConstantInt | ✓ |
| `MaterialOverlayOffset` | ConstantInt | |
| `MaterialParameters` | FixedString | ✓ |
| `MaterialType` | MaterialType | ✓ |
| `MeshEffect` | FixedString | ✓ |
| `Necromantic` | YesNo | |
| `NumStableFailed` | ConstantInt | ✓ |
| `NumStableSuccess` | ConstantInt | ✓ |
| `OnApplyConditions` | Conditions | ✓ |
| `OnApplyFail` | StatsFunctors | ✓ |
| `OnApplyFunctors` | StatsFunctors | ✓ |
| `OnApplyRoll` | Conditions | ✓ |
| `OnApplySuccess` | StatsFunctors | ✓ |
| `OnRemoveFail` | StatsFunctors | |
| `OnRemoveFunctors` | StatsFunctors | ✓ |
| `OnRemoveRoll` | Conditions | |
| `OnRemoveSuccess` | StatsFunctors | |
| `OnRollsFailed` | StatsFunctors | ✓ |
| `OnSuccess` | StatsFunctors | ✓ |
| `OnTickFail` | StatsFunctors | ✓ |
| `OnTickRoll` | Conditions | ✓ |
| `OnTickSuccess` | StatsFunctors | ✓ |
| `Passives` | FixedString | ✓ |
| `PeaceOnly` | YesNo | ✓ |
| `PerformEventName` | FixedString | ✓ |
| `PlayerHasTag` | FixedString | ✓ |
| `PlayerSameParty` | YesNo | |
| `PolymorphResult` | FixedString | |
| `Projectile` | FixedString | |
| `Radius` | ConstantInt | |
| `RemoveConditions` | Conditions | ✓ |
| `RemoveEvents` | StatusEvent | ✓ |
| `ResetCooldowns` | FixedString | |
| `RetainSpells` | FixedString | |
| `Rules` | Guid | ✓ |
| `Sheathing` | StatusSheathing | ✓ |
| `SoundLoop` | FixedString | ✓ |
| `SoundStart` | FixedString | ✓ |
| `SoundStop` | FixedString | ✓ |
| `SoundVocalEnd` | SoundVocalType | ✓ |
| `SoundVocalLoop` | SoundVocalType | ✓ |
| `SoundVocalStart` | SoundVocalType | ✓ |
| `Spells` | FixedString | |
| `SplatterBloodAmount` | ConstantFloat | ✓ |
| `SplatterDirtAmount` | ConstantFloat | ✓ |
| `SplatterSweatAmount` | ConstantFloat | ✓ |
| `StableRoll` | FixedString | ✓ |
| `StableRollDC` | ConstantInt | ✓ |
| `StackId` | FixedString | ✓ |
| `StackPriority` | ConstantInt | ✓ |
| `StackType` | StatusStackType | ✓ |
| `StatsId` | FixedString | |
| `StatusEffect` | FixedString | ✓ |
| `StatusEffectOnTurn` | FixedString | ✓ |
| `StatusEffectOverride` | FixedString | ✓ |
| `StatusEffectOverrideForItems` | FixedString | ✓ |
| `StatusGroups` | StatusGroupFlags | ✓ |
| `StatusPropertyFlags` | StatusPropertyFlags | ✓ |
| `StatusSoundState` | FixedString | ✓ |
| `StatusType` | FixedString | |
| `StillAnimationPriority` | StillAnimPriority | ✓ |
| `StillAnimationType` | StatusAnimationType | ✓ |
| `SurfaceChange` | FixedString | ✓ |
| `TargetConditions` | FixedString | |
| `TargetEffect` | FixedString | |
| `TemplateID` | FixedString | ✓ |
| `TickFunctors` | StatsFunctors | ✓ |
| `TickType` | TickType | ✓ |
| `Toggle` | YesNo | ✓ |
| `TooltipDamage` | FixedString | ✓ |
| `TooltipPermanentWarnings` | FixedString | ✓ |
| `TooltipSave` | FixedString | ✓ |
| `UseLyingPickingState` | YesNo | ✓ |
| `WeaponOverride` | FixedString | |

### Boost Fields

| Field | Purpose |
|-------|---------|
| `Boosts` | Boost expressions (primarily for BOOST status subtype) |

### Boosts Used in Vanilla (88)

`Ability` · `AbilityFailedSavingThrow` · `AbilityOverrideMinimum` · `AC` · `ACOverrideFormula` · `ActionResource` · `ActionResourceBlock` · `ActionResourceConsumeMultiplier` · `ActionResourceMultiplier` · `ActionResourceOverride` · `ActiveCharacterLight` · `Advantage` · `AiArchetypeOverride` · `AttackSpellOverride` · `Attribute` · `BlockAbilityModifierDamageBonus` · `BlockAbilityModifierFromAC` · `BlockRegainHP` · `BlockSpellCast` · `BlockVerbalComponent` · `CannotHarmCauseEntity` · `CanShootThrough` · `CanWalkThrough` · `CarryCapacityMultiplier` · `CharacterUnarmedDamage` · `CharacterWeaponDamage` · `CriticalHit` · `DamageBonus` · `DamageReduction` · `DarkvisionRangeMin` · `DetectDisturbancesBlock` · `DialogueBlock` · `Disadvantage` · `DownedStatus` · `EnableBasicItemInteractions` · `EntityThrowDamage` · `FactionOverride` · `FallDamageMultiplier` · `GameplayLight` · `GameplayObscurity` · `HalveWeaponDamage` · `HorizontalFOVOverride` · `IgnoreDamageThreshold` · `IgnoreFallDamage` · `IgnoreLeaveAttackRange` · `IgnoreSurfaceCover` · `IncreaseMaxHP` · `Invisibility` · `Invulnerable` · `ItemReturnToOwner` · `JumpMaxDistanceMultiplier` · `Lock` · `Lootable` · `MaximizeHealing` · `MovementSpeedLimit` · `ObjectSize` · `Proficiency` · `ProficiencyBonus` · `ProjectileDeflect` · `Reroll` · `Resistance` · `RollBonus` · `ScaleMultiplier` · `SightRangeMaximum` · `SightRangeMinimum` · `SightRangeOverride` · `Skill` · `SoundsBlocked` · `SourceAdvantageOnAttack` · `SourceAllyAdvantageOnAttack` · `SpellSaveDC` · `StatusImmunity` · `Tag` · `TemporaryHP` · `UnlockInterrupt` · `UnlockSpell` · `UnlockSpellVariant` · `UseBoosts` · `VoicebarkBlock` · `WeaponAttackRollAbilityOverride` · `WeaponAttackRollBonus` · `WeaponAttackTypeOverride` · `WeaponDamage` · `WeaponDamageDieOverride` · `WeaponDamageResistance` · `WeaponEnchantment` · `WeaponProperty` · `WeightCategory`

### Functor Fields

| Field | Purpose |
|-------|---------|
| `AuraStatuses` | Aura-applied functors |
| `OnApplyFunctors` | Functors on status application |
| `OnApplySuccess` | Functors on successful apply roll |
| `OnApplyFail` | Functors on failed apply roll |
| `OnTickSuccess` | Functors on successful tick roll |
| `OnTickFail` | Functors on failed tick roll |
| `TickFunctors` | Per-tick functors |
| `OnRemoveFunctors` | Functors on status removal |
| `OnRollsFailed` | Functors when all rolls fail |
| `OnSuccess` | General success functors |

### Functors Used in Vanilla (22)

`ApplyEquipmentStatus` · `ApplyStatus` · `BreakConcentration` · `CreateExplosion` · `CreateSurface` · `DealDamage` · `DisarmAndStealWeapon` · `DisarmWeapon` · `Force` · `RegainHitPoints` · `RemoveStatus` · `ResetCombatTurn` · `ResetCooldowns` · `RestoreResource` · `Resurrect` · `SetStatusDuration` · `Stabilize` · `Summon` · `SwitchDeathType` · `TriggerRandomCast` · `UseActionResource` · `UseSpell`

---

## PassiveData

> 29 fields defined in Modifiers. 25 observed in vanilla data.
> **Data file**: `Passive.txt`

### Fields

| Field | Type | Observed |
|-------|------|:--------:|
| `BoostConditions` | Conditions | ✓ |
| `BoostContext` | StatsFunctorContext | ✓ |
| `Boosts` | FixedString | ✓ |
| `Conditions` | Conditions | ✓ |
| `Description` | TranslatedString | ✓ |
| `DescriptionParams` | FixedString | ✓ |
| `DescriptionRef` | TranslatedString | |
| `DisplayName` | TranslatedString | ✓ |
| `DisplayNameRef` | TranslatedString | |
| `DynamicAnimationTag` | Guid | |
| `EnabledConditions` | Conditions | ✓ |
| `EnabledContext` | StatsFunctorContext | ✓ |
| `ExtraDescription` | TranslatedString | ✓ |
| `ExtraDescriptionParams` | FixedString | ✓ |
| `ExtraDescriptionRef` | TranslatedString | |
| `Icon` | FixedString | ✓ |
| `LoreDescription` | TranslatedString | |
| `LoreDescriptionRef` | TranslatedString | |
| `PriorityOrder` | ConstantInt | ✓ |
| `Properties` | PassiveFlags | ✓ |
| `StatsFunctorContext` | StatsFunctorContext | ✓ |
| `StatsFunctors` | StatsFunctors | ✓ |
| `ToggleGroup` | FixedString | ✓ |
| `ToggleOffContext` | StatsFunctorContext | ✓ |
| `ToggleOffEffect` | FixedString | |
| `ToggleOffFunctors` | StatsFunctors | ✓ |
| `ToggleOnEffect` | FixedString | ✓ |
| `ToggleOnFunctors` | StatsFunctors | ✓ |
| `TooltipConditionalDamage` | FixedString | ✓ |
| `TooltipPermanentWarnings` | FixedString | ✓ |
| `TooltipSave` | FixedString | ✓ |
| `TooltipUseCosts` | FixedString | ✓ |

### Boost Fields

| Field | Purpose |
|-------|---------|
| `Boosts` | Passive boost expressions (conditional via BoostConditions/BoostContext) |

### Boosts Used in Vanilla (53)

`Ability` · `AbilityOverrideMinimum` · `AC` · `ACOverrideFormula` · `ActionResource` · `ActionResourceOverride` · `ActionResourceReplenishTypeOverride` · `ActiveCharacterLight` · `AddProficiencyToAC` · `AddProficiencyToDamage` · `Advantage` · `ArmorAbilityModifierCapOverride` · `Attribute` · `BlockVerbalComponent` · `CannotBeDisarmed` · `CarryCapacityMultiplier` · `CharacterUnarmedDamage` · `CharacterWeaponDamage` · `CriticalDamageOnHit` · `CriticalHit` · `DamageBonus` · `DamageReduction` · `DarkvisionRangeMin` · `Disadvantage` · `DownedStatus` · `DualWielding` · `EntityThrowDamage` · `ExpertiseBonus` · `FallDamageMultiplier` · `IgnoreLowGroundPenalty` · `IgnorePointBlankDisadvantage` · `IgnoreResistance` · `IgnoreSurfaceCover` · `IncreaseMaxHP` · `Initiative` · `JumpMaxDistanceMultiplier` · `MinimumRollResult` · `NonLethal` · `Proficiency` · `ProficiencyBonus` · `ReduceCriticalAttackThreshold` · `Reroll` · `Resistance` · `RollBonus` · `Skill` · `StatusImmunity` · `Tag` · `TwoWeaponFighting` · `UnlockInterrupt` · `UnlockSpell` · `UnlockSpellVariant` · `Weight` · `WeightCategory`

### Functor Fields

| Field | Purpose |
|-------|---------|
| `StatsFunctors` | Main passive functors (triggered by StatsFunctorContext) |
| `ToggleOnFunctors` | Functors when toggled on |
| `ToggleOffFunctors` | Functors when toggled off |
| `Properties` | Passive property flags (PassiveFlags type — not a functor field, but extracted for completeness) |

### Functors Used in Vanilla (12)

`ApplyStatus` · `CreateExplosion` · `DealDamage` · `Kill` · `RegainHitPoints` · `RemoveStatus` · `RestoreResource` · `SetStatusDuration` · `SwapPlaces` · `TriggerRandomCast` · `UseActionResource` · `UseSpell`

---

## InterruptData

> 30 fields defined in Modifiers. 21 observed in vanilla data.
> **Data file**: `Interrupt.txt`

### Fields

| Field | Type | Observed |
|-------|------|:--------:|
| `Conditions` | Conditions | ✓ |
| `Container` | FixedString | ✓ |
| `Cooldown` | CooldownType | ✓ |
| `Cost` | FixedString | ✓ |
| `Description` | TranslatedString | ✓ |
| `DescriptionParams` | FixedString | ✓ |
| `DescriptionRef` | TranslatedString | |
| `DisplayName` | TranslatedString | ✓ |
| `DisplayNameRef` | TranslatedString | |
| `EnableCondition` | Conditions | ✓ |
| `EnableContext` | StatsFunctorContext | ✓ |
| `ExtraDescription` | TranslatedString | ✓ |
| `ExtraDescriptionParams` | FixedString | |
| `ExtraDescriptionRef` | TranslatedString | |
| `Failure` | StatsFunctors | ✓ |
| `Icon` | FixedString | ✓ |
| `InterruptContext` | InterruptContext | ✓ |
| `InterruptContextScope` | InterruptContextScope | ✓ |
| `InterruptDefaultValue` | InterruptDefaultValue | ✓ |
| `InterruptFlags` | InterruptFlagsList | ✓ |
| `LoreDescription` | TranslatedString | |
| `LoreDescriptionRef` | TranslatedString | |
| `Properties` | StatsFunctors | ✓ |
| `Roll` | Conditions | ✓ |
| `ShortDescription` | TranslatedString | |
| `ShortDescriptionParams` | FixedString | |
| `ShortDescriptionRef` | TranslatedString | |
| `Stack` | FixedString | ✓ |
| `Success` | StatsFunctors | ✓ |
| `TooltipAttackSave` | FixedString | |
| `TooltipDamageList` | FixedString | ✓ |
| `TooltipOnMiss` | FixedString | |
| `TooltipOnSave` | FixedString | |
| `TooltipPermanentWarnings` | FixedString | |
| `TooltipStatusApply` | FixedString | |

### Boost Fields

None — InterruptData does not have boost-accepting fields.

### Functor Fields

| Field | Purpose |
|-------|---------|
| `Properties` | Main interrupt effect functors |
| `Success` | Functors on successful roll |
| `Failure` | Functors on failed roll |

### Functors Used in Vanilla (11)

`AdjustRoll` · `ApplyStatus` · `Counterspell` · `DealDamage` · `RemoveStatus` · `SetAdvantage` · `SetDisadvantage` · `SetRoll` · `TutorialEvent` · `UseAttack` · `UseSpell`

---

## CriticalHitTypeData

> 13 fields defined in Modifiers. 13 observed in vanilla data.
> **Data file**: `CriticalHitTypes.txt`

### Fields

| Field | Type | Observed |
|-------|------|:--------:|
| `AcidFX` | Guid | ✓ |
| `BludgeoningFX` | Guid | ✓ |
| `ColdFX` | Guid | ✓ |
| `FireFX` | Guid | ✓ |
| `ForceFX` | Guid | ✓ |
| `LightningFX` | Guid | ✓ |
| `NecroticFX` | Guid | ✓ |
| `PiercingFX` | Guid | ✓ |
| `PoisonFX` | Guid | ✓ |
| `PsychicFX` | Guid | ✓ |
| `RadiantFX` | Guid | ✓ |
| `SlashingFX` | Guid | ✓ |
| `ThunderFX` | Guid | ✓ |

### Boost Fields

None.

### Functor Fields

None.

---

## Cross-Type Boost Usage Matrix

Which boosts appear in which types? Useful for understanding boost scope.

| Boost | Weapon | Armor | Character | Object | Status | Passive |
|-------|:------:|:-----:|:---------:|:------:|:------:|:-------:|
| `Ability` | | ✓ | | | ✓ | ✓ |
| `AbilityFailedSavingThrow` | | | | | ✓ | |
| `AbilityOverrideMinimum` | | ✓ | | | ✓ | ✓ |
| `AC` | | ✓ | | | ✓ | ✓ |
| `ACOverrideFormula` | | | | | ✓ | ✓ |
| `ActionResource` | | ✓ | ✓ | | ✓ | ✓ |
| `ActionResourceBlock` | | | ✓ | | ✓ | |
| `ActionResourceConsumeMultiplier` | | | | | ✓ | |
| `ActionResourceMultiplier` | | | | | ✓ | |
| `ActionResourceOverride` | | | | | ✓ | ✓ |
| `ActionResourceReplenishTypeOverride` | | | | | | ✓ |
| `ActiveCharacterLight` | | | | | ✓ | ✓ |
| `AddProficiencyToAC` | | | | | | ✓ |
| `AddProficiencyToDamage` | | | | | | ✓ |
| `Advantage` | | ✓ | | | ✓ | ✓ |
| `AiArchetypeOverride` | | | | | ✓ | |
| `ArmorAbilityModifierCapOverride` | | | | | | ✓ |
| `AttackSpellOverride` | | | | | ✓ | |
| `Attribute` | | | ✓ | | ✓ | ✓ |
| `BlockAbilityModifierDamageBonus` | | | | | ✓ | |
| `BlockAbilityModifierFromAC` | | | | | ✓ | |
| `BlockRegainHP` | | | ✓ | | ✓ | |
| `BlockSpellCast` | | | | | ✓ | |
| `BlockVerbalComponent` | | | | | ✓ | ✓ |
| `CannotBeDisarmed` | ✓ | | | | | ✓ |
| `CannotHarmCauseEntity` | | | | | ✓ | |
| `CanShootThrough` | | | | | ✓ | |
| `CanWalkThrough` | | | | | ✓ | |
| `CarryCapacityMultiplier` | | | | | ✓ | ✓ |
| `CharacterUnarmedDamage` | | | | | ✓ | ✓ |
| `CharacterWeaponDamage` | | | | | ✓ | ✓ |
| `CriticalDamageOnHit` | | | | | | ✓ |
| `CriticalHit` | | ✓ | ✓ | ✓ | ✓ | ✓ |
| `DamageBonus` | | | | | ✓ | ✓ |
| `DamageReduction` | | | | ✓ | ✓ | ✓ |
| `DarkvisionRangeMin` | | | | | ✓ | ✓ |
| `DetectDisturbancesBlock` | | | | | ✓ | |
| `DialogueBlock` | | | ✓ | | ✓ | |
| `Disadvantage` | | ✓ | | | ✓ | ✓ |
| `DownedStatus` | | | | | ✓ | ✓ |
| `DualWielding` | | | | | | ✓ |
| `EnableBasicItemInteractions` | | | | | ✓ | |
| `EntityThrowDamage` | | | | | ✓ | ✓ |
| `ExpertiseBonus` | | | | | | ✓ |
| `FactionOverride` | | | | | ✓ | |
| `FallDamageMultiplier` | | | | | ✓ | ✓ |
| `GameplayLight` | | | | | ✓ | |
| `GameplayObscurity` | | | | | ✓ | |
| `HalveWeaponDamage` | | | | | ✓ | |
| `HiddenDuringCinematic` | ✓ | | | | | |
| `HorizontalFOVOverride` | | | | | ✓ | |
| `IgnoreDamageThreshold` | | | | | ✓ | |
| `IgnoreFallDamage` | | | | ✓ | ✓ | |
| `IgnoreLeaveAttackRange` | | | | | ✓ | |
| `IgnoreLowGroundPenalty` | | | | | | ✓ |
| `IgnorePointBlankDisadvantage` | | | | | | ✓ |
| `IgnoreResistance` | ✓ | | | | | ✓ |
| `IgnoreSurfaceCover` | | | | | ✓ | ✓ |
| `IncreaseMaxHP` | | | | | ✓ | ✓ |
| `Initiative` | | | | | | ✓ |
| `Invisibility` | | | | | ✓ | |
| `Invulnerable` | | | ✓ | ✓ | ✓ | |
| `ItemReturnToOwner` | | | | | ✓ | |
| `JumpMaxDistanceMultiplier` | | | | | ✓ | ✓ |
| `Lock` | | | | | ✓ | |
| `Lootable` | | | | | ✓ | |
| `MaximizeHealing` | | | | | ✓ | |
| `MinimumRollResult` | | | | | | ✓ |
| `MovementSpeedLimit` | | | | | ✓ | |
| `NonLethal` | | | | | | ✓ |
| `ObjectSize` | | | | | ✓ | |
| `Proficiency` | ✓ | | | | ✓ | ✓ |
| `ProficiencyBonus` | | ✓ | ✓ | | ✓ | ✓ |
| `ProjectileDeflect` | | | | | ✓ | |
| `ReduceCriticalAttackThreshold` | | | | | | ✓ |
| `Reroll` | | | | | ✓ | ✓ |
| `Resistance` | ✓ | ✓ | | | ✓ | ✓ |
| `RollBonus` | | ✓ | | | ✓ | ✓ |
| `Savant` | | | | | | |
| `ScaleMultiplier` | | | | | ✓ | |
| `SightRangeMaximum` | | | | | ✓ | |
| `SightRangeMinimum` | | | | | ✓ | |
| `SightRangeOverride` | | | | | ✓ | |
| `Skill` | ✓ | ✓ | ✓ | | ✓ | ✓ |
| `SoundsBlocked` | | | | | ✓ | |
| `SourceAdvantageOnAttack` | | | | | ✓ | |
| `SourceAllyAdvantageOnAttack` | | | | | ✓ | |
| `SpellSaveDC` | | | | | ✓ | |
| `StatusImmunity` | | | | | ✓ | ✓ |
| `Tag` | | ✓ | | ✓ | ✓ | ✓ |
| `TemporaryHP` | | | | | ✓ | |
| `TwoWeaponFighting` | | | | | | ✓ |
| `UnlockInterrupt` | | | | | ✓ | ✓ |
| `UnlockSpell` | ✓ | ✓ | | | ✓ | ✓ |
| `UnlockSpellVariant` | | | | | ✓ | ✓ |
| `UseBoosts` | | | | | ✓ | |
| `VoicebarkBlock` | | | | | ✓ | |
| `WeaponAttackRollAbilityOverride` | | | | | ✓ | |
| `WeaponAttackRollBonus` | | | | | ✓ | |
| `WeaponAttackTypeOverride` | | | | | ✓ | |
| `WeaponDamage` | ✓ | | | | ✓ | |
| `WeaponDamageDieOverride` | | | | | ✓ | |
| `WeaponDamageResistance` | | | | | ✓ | |
| `WeaponEnchantment` | ✓ | | | | ✓ | |
| `WeaponProperty` | ✓ | | | | ✓ | |
| `Weight` | | | | | | ✓ |
| `WeightCategory` | | | | | ✓ | ✓ |

## Cross-Type Functor Usage Matrix

Which functors appear in which types?

| Functor | Weapon | Spell | Status | Passive | Interrupt |
|---------|:------:|:-----:|:------:|:-------:|:---------:|
| `AdjustRoll` | | | | | ✓ |
| `ApplyEquipmentStatus` | | ✓ | ✓ | | |
| `ApplyStatus` | ✓ | ✓ | ✓ | ✓ | ✓ |
| `BreakConcentration` | | ✓ | ✓ | | |
| `Counterspell` | | | | | ✓ |
| `CreateExplosion` | | ✓ | ✓ | ✓ | |
| `CreateSurface` | | ✓ | ✓ | | |
| `DealDamage` | | ✓ | ✓ | ✓ | ✓ |
| `DisarmAndStealWeapon` | | | ✓ | | |
| `DisarmWeapon` | | | ✓ | | |
| `ExecuteWeaponFunctors` | | ✓ | | | |
| `Force` | | ✓ | ✓ | | |
| `Kill` | | | | ✓ | |
| `RegainHitPoints` | | ✓ | ✓ | ✓ | |
| `RemoveStatus` | | ✓ | ✓ | ✓ | ✓ |
| `ResetCombatTurn` | | | ✓ | | |
| `ResetCooldowns` | | | ✓ | | |
| `RestoreResource` | | ✓ | ✓ | ✓ | |
| `Resurrect` | | ✓ | ✓ | | |
| `SetAdvantage` | | | | | ✓ |
| `SetDisadvantage` | | | | | ✓ |
| `SetRoll` | | | | | ✓ |
| `SetStatusDuration` | | ✓ | ✓ | ✓ | |
| `ShortRest` | | ✓ | | | |
| `Spawn` | | ✓ | | | |
| `SpawnExtraProjectiles` | | ✓ | | | |
| `Stabilize` | | ✓ | ✓ | | |
| `Summon` | | ✓ | ✓ | | |
| `SummonInInventory` | | ✓ | | | |
| `SurfaceChange` | ✓ | ✓ | | | |
| `SurfaceClearLayer` | | ✓ | | | |
| `SwapPlaces` | | | | ✓ | |
| `SwitchDeathType` | | ✓ | ✓ | | |
| `TeleportSource` | | ✓ | | | |
| `TriggerRandomCast` | | | ✓ | ✓ | |
| `TutorialEvent` | | | | | ✓ |
| `Unlock` | | ✓ | | | |
| `Unsummon` | | ✓ | | | |
| `UseActionResource` | | ✓ | ✓ | ✓ | |
| `UseAttack` | | | | | ✓ |
| `UseSpell` | | | ✓ | ✓ | ✓ |
