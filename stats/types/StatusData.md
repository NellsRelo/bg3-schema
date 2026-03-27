# StatusData

> **Type identifier**: `StatusData`
> **Source files**: `Stats/Generated/Data/Status_*.txt`
> **Modifier definition**: [Modifiers.md](../formats/Modifiers.md#statusdata) (110 fields)

---

## Overview

Defines all status effects — buffs, debuffs, conditions, polymorph, healing, invisibility, stealth, and more. The second-largest type after SpellData by field count (110). Each entry specifies a `StatusType` discriminator that determines which fields are relevant. All subtypes share the same 110-field pool.

## Status Subtypes

| StatusType | Source File | Purpose |
|------------|-------------|---------|
| `BOOST` | Status_BOOST.txt | Positive/negative effects, ability bonuses, auras |
| `EFFECT` | Status_EFFECT.txt | General effects (DoTs, conditions, surfaces) |
| `DOWNED` | Status_DOWNED.txt | Downed/dying state (death saves) |
| `FEAR` | Status_FEAR.txt | Fear condition |
| `HEAL` | Status_HEAL.txt | Healing over time |
| `INCAPACITATED` | Status_INCAPACITATED.txt | Incapacitated (stunned, paralyzed, petrified) |
| `INVISIBLE` | Status_INVISIBLE.txt | Invisibility |
| `KNOCKED_DOWN` | Status_KNOCKED_DOWN.txt | Knocked prone |
| `POLYMORPHED` | Status_POLYMORPHED.txt | Polymorph/wild shape |
| `DEACTIVATED` | Status_DEACTIVATED.txt | Deactivated/inactive state |
| `SNEAKING` | Status_SNEAKING.txt | Stealth/sneaking mode |

## Entry Format

```
new entry "HASTENED"
type "StatusData"
data "StatusType" "BOOST"
data "DisplayName" "h3f8a..."
data "Description" "h4c9b..."
data "Icon" "Spell_Transmutation_Haste"
data "StackId" "HASTENED"
data "StackType" "Stack"
data "Boosts" "ActionResource(Movement,6,0);ActionResource(ActionPoint,1,0)"
data "RemoveEvents" "OnTurn"
data "StatusPropertyFlags" "DisableOverhead;DisableCombatlog;DisablePortraitIndicator"
data "StatusGroups" "SG_RemoveOnRespec"
```

## Pack Distribution

| Pack | Files | Notes |
|------|-------|-------|
| Shared | All 11 subtypes | Primary definitions |
| SharedDev | Most subtypes | Development entries |
| Gustav | BOOST, DOWNED, EFFECT, POLYMORPHED, INCAPACITATED | Module-specific |
| GustavDev | Most subtypes | Development entries |
| GustavX | Most subtypes | DLC statuses |
| Honour | BOOST, DOWNED, KNOCKED_DOWN | Honour-mode overrides |

---

## Form Reference — All Fields

> Complete field table for form/editor construction. 110 fields defined in [Modifiers.md](../formats/Modifiers.md#statusdata). ✓ = observed in vanilla data.

| Field | Type | Observed |
|-------|------|:--------:|
| `AiCalculationSpellOverride` | FixedString | ✓ |
| `Angle` | ConstantInt | |
| `ApplyEffect` | FixedString | ✓ |
| `AuraFlags` | StatusAuraFlags | ✓ |
| `AuraFX` | FixedString | ✓ |
| `AuraRadius` | ConstantFloat | ✓ |
| `AuraStatuses` | StatsFunctors | ✓ |
| `BeamEffect` | FixedString | |
| `BonusFromSkill` | SkillType | |
| `Boosts` | FixedString | ✓ |
| `CastTextEvent` | FixedString | |
| `Charges` | ConstantInt | ✓ |
| `DamageStats` | FixedString | |
| `DamageType` | Damage Type | |
| `DeathType` | Death Type | |
| `DefendTargetPosition` | YesNo | |
| `Description` | TranslatedString | ✓ |
| `DescriptionParams` | FixedString | ✓ |
| `DescriptionRef` | TranslatedString | |
| `DisableInteractions` | YesNo | |
| `DisplayName` | TranslatedString | ✓ |
| `DisplayNameRef` | TranslatedString | |
| `DynamicAnimationTag` | Guid | ✓ |
| `EndEffect` | FixedString | ✓ |
| `ExtraDescription` | TranslatedString | |
| `ExtraDescriptionParams` | FixedString | |
| `ExtraDescriptionRef` | TranslatedString | |
| `FreezeGravity` | YesNo | |
| `HealMultiplier` | ConstantInt | ✓ |
| `HealStat` | StatusHealType | ✓ |
| `HealType` | HealValueType | ✓ |
| `HealValue` | FixedString | ✓ |
| `HitAnimationType` | HitAnimationType | |
| `Icon` | FixedString | ✓ |
| `ImmuneFlag` | AttributeFlags | |
| `IsChanneled` | YesNo | ✓ |
| `Items` | FixedString | |
| `LEDEffect` | StatusLEDEffect | ✓ |
| `Malus` | FixedString | |
| `ManagedStatusEffectGroup` | FixedString | ✓ |
| `ManagedStatusEffectType` | ManagedStatusEffectType | ✓ |
| `Material` | FixedString | ✓ |
| `MaterialApplyArmor` | YesNo | ✓ |
| `MaterialApplyBody` | YesNo | ✓ |
| `MaterialApplyNormalMap` | YesNo | ✓ |
| `MaterialFadeAmount` | ConstantFloat | ✓ |
| `MaterialOverlayOffset` | ConstantFloat | ✓ |
| `MaterialParameters` | FixedString | ✓ |
| `MaterialType` | MaterialType | ✓ |
| `Necromancy` | YesNo | |
| `NumStableRolled` | ConstantInt | |
| `NumStableSuccess` | ConstantInt | |
| `NumStableFailed` | ConstantInt | |
| `OnApplyConditions` | TargetConditions | ✓ |
| `OnApplyFail` | StatsFunctors | ✓ |
| `OnApplyFunctors` | StatsFunctors | ✓ |
| `OnApplyRoll` | RollConditions | ✓ |
| `OnApplySuccess` | StatsFunctors | ✓ |
| `OnRemoveConditions` | TargetConditions | |
| `OnRemoveFail` | StatsFunctors | ✓ |
| `OnRemoveFunctors` | StatsFunctors | ✓ |
| `OnRemoveRoll` | RollConditions | ✓ |
| `OnRemoveSuccess` | StatsFunctors | ✓ |
| `OnRollsFailed` | StatsFunctors | ✓ |
| `OnSuccess` | StatsFunctors | ✓ |
| `OnTickConditions` | TargetConditions | ✓ |
| `OnTickFail` | StatsFunctors | ✓ |
| `OnTickRoll` | RollConditions | ✓ |
| `OnTickSuccess` | StatsFunctors | ✓ |
| `PeaceOnly` | YesNo | |
| `PerformEventName` | FixedString | ✓ |
| `PlayerHasTag` | Guid | ✓ |
| `PlayerSameParty` | YesNo | ✓ |
| `PolymorphResult` | FixedString | ✓ |
| `Projectile` | FixedString | |
| `Radius` | ConstantInt | |
| `RetainSpells` | FixedString | ✓ |
| `Rules` | StatusRules | ✓ |
| `SavingThrow` | SavingThrow | ✓ |
| `SoundLoop` | FixedString | ✓ |
| `SoundStart` | FixedString | ✓ |
| `SoundStop` | FixedString | ✓ |
| `SoundVocalEnd` | FixedString | |
| `SoundVocalLoop` | FixedString | |
| `SoundVocalStart` | FixedString | ✓ |
| `SpellId` | FixedString | ✓ |
| `Spells` | FixedString | ✓ |
| `StackId` | FixedString | ✓ |
| `StackPriority` | ConstantInt | ✓ |
| `StackType` | StatusStackType | ✓ |
| `StableRollDC` | ConstantInt | |
| `StartEffect` | FixedString | ✓ |
| `StatusEffect` | FixedString | ✓ |
| `StatusEffectOnTurn` | FixedString | ✓ |
| `StatusEffectOverride` | FixedString | ✓ |
| `StatusEffectOverrideForItems` | FixedString | ✓ |
| `StatusGroups` | StatusGroups | ✓ |
| `StatusPropertyFlags` | StatusPropertyFlags | ✓ |
| `StatusSoundState` | FixedString | ✓ |
| `StatusType` | FixedString | |
| `StillAnimPriority` | FixedString | ✓ |
| `StillAnimType` | StillAnimType | ✓ |
| `SurfaceChange` | SurfaceChange | |
| `TargetConditions` | TargetConditions | ✓ |
| `TargetEffect` | FixedString | ✓ |
| `TickFunctors` | StatsFunctors | ✓ |
| `TickType` | StatusAnimationType | ✓ |
| `Toggle` | YesNo | ✓ |
| `TooltipDamage` | FixedString | ✓ |
| `TooltipPermanentWarnings` | FixedString | ✓ |
| `TooltipSave` | FixedString | ✓ |
| `UseLyingPickingState` | YesNo | ✓ |
| `WeaponOverride` | FixedString | ✓ |

### Boost Fields & Observed Boosts

| Boost Field | Purpose |
|-------------|---------|
| `Boosts` | Generic boost list applied while status is active |

**Boosts used in vanilla (88):** `AC` · `ACOverrideFormula` · `ActionResource` · `ActionResourceBlock` · `ActionResourceMultiplier` · `ActionResourceOverride` · `ActionResourcePreventReduction` · `ActionResourceReplenishTypeOverride` · `AdvanceSpells` · `Advantage` · `AiArchetypeOverride` · `ArmorAbilityModifierCapOverride` · `AttackSpellOverride` · `Attribute` · `BlockAbilityModifierDamageBonus` · `BlockAbilityModifierFromAC` · `BlockGravity` · `BlockRegainHP` · `BlockTravel` · `CanSeeThrough` · `CanShootThrough` · `CanWalkThrough` · `CannotHarmCauseEntity` · `CarryCapacityMultiplier` · `ConcentrationIgnoreDamage` · `CriticalDamageOnHit` · `DamageBonus` · `DamageTakenBonus` · `DarkvisionRange` · `DarkvisionRangeMin` · `DarkvisionRangeOverride` · `DetectCrimesBlock` · `DisableWeaponAbilityCheck` · `DownedStatus` · `DualWielding` · `EnableBasicItemInteractions` · `FactionOverride` · `FallDamageMultiplier` · `GameplayLight` · `GameplayObscurity` · `GuaranteedChanceRollOutcome` · `HalveWeaponDamage` · `IgnoreEnterAttackRange` · `IgnoreFallDamage` · `IgnoreLeaveAttackRange` · `IgnorePointBlankDisadvantage` · `IgnoreResistance` · `IgnoreSurfaceCover` · `Invulnerable` · `InvisibilityFlag` · `JumpMaxDistanceBonus` · `JumpMaxDistanceMultiplier` · `LeaveTriggers` · `Lock` · `MaximizeHealing` · `MaximumRollResult` · `MinimumRollResult` · `MonkWeaponDamageDiceOverride` · `MovementSpeedLimit` · `NoAOEDamageOnLand` · `NoDodge` · `NonLethal` · `NullifyAbilityScore` · `ObjectSize` · `ObjectSizeOverride` · `ProficiencyBonus` · `ReduceCriticalAttackThreshold` · `Resistance` · `RollBonus` · `SavingThrowBonus` · `ScaleMultiplier` · `Sight` · `Skill` · `SpellResistance` · `SpellSaveDC` · `StatusImmunity` · `Tag` · `TemporaryHP` · `UnlockInterrupt` · `UnlockSpell` · `UnlockSpellVariant` · `UnsummonOnHit` · `VoicebarkBlock` · `WeaponAttackRollAbilityOverride` · `WeaponDamage` · `WeaponDamageDieOverride` · `WeaponDamageTypeOverride` · `WeaponEnchantment` · `Weight`

### Functor Fields & Observed Functors

| Functor Field | Purpose |
|---------------|--------|
| `AuraStatuses` | Aura effects applied to nearby targets |
| `OnApplyFunctors` | Main on-apply functors |
| `OnApplySuccess` | Functors on successful apply roll |
| `OnApplyFail` | Functors on failed apply roll |
| `OnTickSuccess` | Functors on successful tick roll |
| `OnTickFail` | Functors on failed tick roll |
| `TickFunctors` | Main per-tick functors |
| `OnRemoveFunctors` | Functors when status is removed |
| `OnRollsFailed` | Functors when rolls fail |
| `OnSuccess` | Generic success functors |

**Functors used in vanilla (22):** `ApplyEquipmentStatus` · `ApplyStatus` · `BreakConcentration` · `CreateSurface` · `DealDamage` · `Douse` · `ExecuteWeaponFunctors` · `FireProjectile` · `Force` · `Kill` · `RegainHitPoints` · `RemoveStatus` · `RemoveStatusByLevel` · `RestoreResource` · `Resurrect` · `SetRoll` · `Spawn` · `Stabilize` · `SummonInInventory` · `SurfaceChange` · `TeleportSource` · `UseActionResource`

---

## Complete Field Reference

### Core Identity

#### `StatusType`
- **Type**: FixedString
- **Values**: `"BOOST"`, `"EFFECT"`, `"DOWNED"`, `"FEAR"`, `"HEAL"`, `"INCAPACITATED"`, `"INVISIBLE"`, `"KNOCKED_DOWN"`, `"POLYMORPHED"`, `"DEACTIVATED"`, `"SNEAKING"`
- **Notes**: Discriminates subtype. Determines which `Status_*.txt` file the entry belongs to.

### Display

#### `DisplayName`
- **Type**: TranslatedString
- **Values**: `"h3f8a...;1"` (handle format)
- **Notes**: Localized display name.

#### `DisplayNameRef`
- **Type**: TranslatedString
- **Notes**: Alternate display name reference.

#### `Description`
- **Type**: TranslatedString
- **Values**: `"h4c9b...;5"`
- **Notes**: Full status description.

#### `DescriptionRef`
- **Type**: TranslatedString
- **Notes**: Alternate description reference.

#### `DescriptionParams`
- **Type**: FixedString
- **Values**: `"DealDamage(1d4,Fire)"`, `"DealDamage(2d10,Radiant,Magical)"`, `"RegainHitPoints(1d8+WisdomModifier)"`, `"Distance(6)"`, `"LevelMapValue(AuraOfProtection_AuraHP)"`, `"ApplyStatus(BURNING,100,2)"`
- **Notes**: Functor expressions providing values for description placeholders (`[1]`, `[2]`, etc.).

#### `Icon`
- **Type**: FixedString
- **Values**: `"Spell_Transmutation_Haste"`, `"Spell_Enchantment_HoldPerson"`, `"Status_Burning"`, `"Spell_Abjuration_Shield_of_Faith"`, `"GenericIcon_DamageType_Radiant"`
- **Notes**: Icon asset name for status display.

#### `FormatColor`
- **Type**: FormatStringColor (enum)
- **Values**: `"White"`, `"Green"`, `"Red"`, `"Yellow"`, `"Blue"`, `"Orange"`, `"Cyan"`, `"Magenta"`
- **Notes**: Display color for status text in combat log and UI.

### Stacking

#### `StackId`
- **Type**: FixedString
- **Values**: `"HASTENED"`, `"BURNING"`, `"BLEEDING"`, `"POISONED"`, `"CONCENTRATING"`, `"MAG_HEAT_METAL"`, `"PRONE"`, `"WILDSHAPE"`, `"YOURFEARS_FEAR"`
- **Notes**: Stack identifier. Statuses with the same StackId interact (stack, overwrite, or fail). Typically matches the entry name.

#### `StackType`
- **Type**: StatusStackType (enum from [ValueLists](../formats/ValueLists.md))
- **Values**: `"Stack"`, `"Overwrite"`, `"Ignore"`
- **Notes**: What happens when a status with the same StackId is applied again. `"Stack"` = resets duration, `"Overwrite"` = replaces, `"Ignore"` = fails silently.

#### `StackPriority`
- **Type**: ConstantInt
- **Values**: `"0"`, `"1"`, `"2"`, `"99"`
- **Notes**: Priority within stack group. Higher priority overwrites lower. Default `"0"`.

#### `ForceStackOverwrite`
- **Type**: YesNo
- **Values**: `"Yes"`
- **Notes**: Force overwrite even if normally would stack/ignore.

#### `IsUnique`
- **Type**: ConstantInt
- **Values**: `"0"`, `"1"`
- **Notes**: Boolean. If `"1"`, only one instance of this status can exist globally.

### Effects & Boosts (BOOST primary)

#### `Boosts`
- **Type**: FixedString
- **Values**: `"ActionResource(Movement,6,0)"`, `"ActionResource(ActionPoint,1,0)"`, `"AC(2)"`, `"Advantage(SavingThrow,Wisdom)"`, `"DamageReduction(Fire,Resistant)"`, `"IF(not Ally(context.Target)):DamageReduction(All,2,Flat)"`, `"SpellSaveDC(1)"`, `"RollBonus(SavingThrow,1d4)"`, `"Ability(Strength,4,20)"`, `"Tag(YOURFEARS_TARGET)"`, `"TemporaryHP(1d4+4)"`, `"CriticalHit(AttackTarget,Success,Always)"`, `"Proficiency(SavingThrow,Constitution)"`, `"StatusImmunity(FRIGHTENED)"`, `"IgnoreResistance(Slashing,Resistant)"`, `"ActionResource(SpellSlot,1,1)"`
- **Notes**: Semicolon-separated boost expressions. Core BOOST field. Uses same boost syntax as Weapon/Armor `DefaultBoosts`. ActionResource format: `ActionResource(Type,Amount,Level)`. Conditional: `IF(condition):Boost(...)`.

#### `Passives`
- **Type**: FixedString
- **Values**: `"FightingStyle_Defense"`, `"DangerSense"`, `"Rage_Damage"`, `"SteadfastHeart"`, `"YOURFEARS_PassivePerception"`
- **Notes**: Semicolon-separated passive ability names granted while status is active. References PassiveData entries.

#### `Spells`
- **Type**: FixedString
- **Values**: `"Target_CureWounds_Level2"`, `"Shout_EndRage"`, `"Target_Smite_Searing"`, `"Zone_LightningBreath_Dragonborn"`
- **Notes**: Semicolon-separated spell entry names granted while status is active. References SpellData entries.

#### `Charges`
- **Type**: ConstantInt
- **Values**: `"1"`, `"2"`, `"3"`, `"5"`
- **Notes**: Number of charges. Status expires when charges are consumed. Used for multi-use effects.

### Flags & Groups

#### `StatusPropertyFlags`
- **Type**: StatusPropertyFlags (flags enum)
- **Values**: Semicolon-separated. All observed flags:
  - **Display**: `DisableOverhead`, `DisableCombatlog`, `DisablePortraitIndicator`, `ForceOverhead`, `OverheadOnTurn`, `ExcludeFromPortraitRendering`, `HideInItemTooltip`
  - **Behavior**: `ForceNeutralInteractions`, `LoseControl`, `LoseControlFriendly`, `IgnoredByImmobilized`, `AllowLeaveCombat`, `BringIntoCombat`, `InitiateCombat`
  - **Lifecycle**: `IgnoreResting`, `ApplyToDead`, `TickingWithSource`
  - **Immunity**: `IsInvulnerable`, `IsInvulnerableVisible`
  - **Combat**: `PeaceOnly`, `GiveExp`, `UnavailableInActiveRoll`
  - **UI**: `DisableInteractions`
- **Notes**: `"DisableOverhead;DisableCombatlog;DisablePortraitIndicator"` is the most common combo for non-display statuses.

#### `StatusGroups`
- **Type**: StatusGroupFlags (flags enum)
- **Values**: Semicolon-separated. All observed groups:
  - **Conditions**: `SG_Condition`, `SG_Unconscious`, `SG_Incapacitated`, `SG_Stunned`, `SG_Paralyzed`, `SG_Petrified`, `SG_Sleeping`, `SG_Sleeping_Magical`, `SG_Prone`, `SG_Frightened`, `SG_Fleeing`, `SG_Taunted`, `SG_Poisoned`, `SG_Mad`
  - **Forms**: `SG_Polymorph`, `SG_Polymorph_BeastShape`, `SG_Polymorph_BeastShape_NPC`, `SG_Disguise`
  - **Mode**: `SG_Invisible`, `SG_Drunk`, `SG_Light`, `SG_Surface`, `SG_WeaponCoating`
  - **System**: `SG_RemoveOnRespec`, `SG_DropForNonMutingDialog`
- **Notes**: Group membership for bulk operations. `SG_RemoveOnRespec` removes status when player respecs. `SG_Condition` is the broadest group for general conditions. A status can belong to multiple groups.

#### `ImmuneFlag`
- **Type**: AttributeFlags (flags enum)
- **Notes**: Immunity flags granted by this status.

### Lifecycle Events

#### `RemoveEvents`
- **Type**: StatusEvent (flags enum)
- **Values**: `"OnTurn"`, `"OnDamage"`, `"OnSpellCast"`, `"OnAttack"`, `"OnMove"`, `"OnEntityPickUp"`, `"OnEntityDrop"`, `"OnEntityDrag"`, `"OnLockpickingFinished"`, `"OnDisarmingFinished"`, `"OnStatusApplied"`, `"OnObscurityChanged"`
- **Notes**: Semicolon-separated events that trigger removal. `"OnTurn"` = removed at start of next turn. `"OnDamage"` = removed when damaged (e.g., Sleeping). Multiple events can be combined: `"OnDamage;OnStatusApplied"`.

#### `RemoveConditions`
- **Type**: Conditions
- **Values**: `"not HasStatus('YOURFEARS_TARGET')"`, `"HasStatus('BURNING')"`
- **Notes**: Condition expressions for automatic removal.

#### `Instant`
- **Type**: YesNo
- **Values**: `"Yes"`
- **Notes**: Status applies instantly and doesn't persist (one-shot effect).

#### `Toggle`
- **Type**: YesNo
- **Values**: `"Yes"`
- **Notes**: Status is togglable on/off by the player. Example: `VAMPIRE_REGENERATION`.

#### `PeaceOnly`
- **Type**: YesNo
- **Values**: `"Yes"`
- **Notes**: Status only active outside combat.

#### `Necromantic`
- **Type**: YesNo
- **Values**: `"Yes"`
- **Notes**: Marks status as necromantic (affects undead differently).

### Tick System

#### `TickType`
- **Type**: TickType (enum from [ValueLists](../formats/ValueLists.md))
- **Values**: `"StartTurn"`, `"EndTurn"`, `"EndRound"`
- **Notes**: When tick functors fire. `"StartTurn"` = at the start of the affected creature's turn. `"EndTurn"` = at the end. `"EndRound"` = when the round ends.

#### `TickFunctors`
- **Type**: StatsFunctors
- **Values**: `"DealDamage(1d4,Fire)"`, `"DealDamage(2d6,Necrotic,Magical)"`, `"IF(HasStatus('YOURFEARS_HEXED')):DealDamage(1d6,Necrotic)"`, `"AI_ONLY:DealDamage(1,Slashing)"`, `"RegainHitPoints(1d6+SpellcastingAbilityModifier)"`, `"ApplyStatus(MAG_HEAT_METAL_TICK_VFX,100,1)"`
- **Notes**: Functors executed each tick. Same syntax as SpellData functors. Supports `IF(condition):`, `AI_ONLY:` prefix. DoT damage is implemented here.

#### `OnTickRoll`
- **Type**: Conditions
- **Values**: `"not SavingThrow(Ability.Constitution, 15, AdvantageOnPoisoned())"`, `"SavingThrow(Ability.Wisdom, SourceSpellDC())"`, `"not SavingThrow(Ability.Dexterity, CalculateSpellDC(Ability.Wisdom, GetSummoner(context.Source)))"`, `"SkillCheck(Skill.Performance, 15)"`
- **Notes**: Roll condition checked each tick.

#### `OnTickSuccess`
- **Type**: StatsFunctors
- **Values**: `"DealDamage(2d10,Radiant,Magical)"`, `"DealDamage(3d8,Necrotic,Magical)"`, `"RemoveStatus(SELF,ENTOMBED)"`, `"ApplyStatus(CURSE_SKIPPED_TURN,100,1)"`
- **Notes**: Executed when tick roll succeeds.

#### `OnTickFail`
- **Type**: StatsFunctors
- **Values**: `"DealDamage(2d6/2,Fire,Magical)"`, `"RemoveStatus(ENTOMBED)"`, `"ApplyStatus(FRIGHTENED,100,1)"`
- **Notes**: Executed when tick roll fails.

### Apply System

#### `OnApplyRoll`
- **Type**: Conditions
- **Values**: `"not SavingThrow(Ability.Constitution, 15)"`, `"SavingThrow(Ability.Wisdom, SourceSpellDC())"`
- **Notes**: Roll condition checked when status is first applied.

#### `OnApplyConditions`
- **Type**: Conditions
- **Values**: `"not HasStatus('YOURFEARS_IMMUNE')"`, `"not Dead()"`, `"Character() and not Self()"`
- **Notes**: Boolean conditions that must be true for apply to proceed.

#### `OnApplySuccess`
- **Type**: StatsFunctors
- **Values**: `"ApplyStatus(PRONE,100,1)"`, `"DealDamage(1d6,Psychic)"`, `"RemoveStatus(FRIGHTENED)"`
- **Notes**: Executed when apply roll succeeds.

#### `OnApplyFail`
- **Type**: StatsFunctors
- **Values**: `"RemoveStatus(SELF,CHARMED)"`, `"ApplyStatus(SELF,YOURFEARS_FEAR_IMMUNE,100,2)"`
- **Notes**: Executed when apply roll fails.

#### `OnApplyFunctors`
- **Type**: StatsFunctors
- **Values**: Functor expressions
- **Notes**: Always-execute functors when status is applied (regardless of roll).

### Remove System

#### `OnRemoveRoll`
- **Type**: Conditions
- **Notes**: Roll condition checked when status is removed.

#### `OnRemoveSuccess`
- **Type**: StatsFunctors
- **Values**: `"ApplyStatus(SELF,LETHARGY,100,1)"`, `"DealDamage(4d6,Thunder)"`
- **Notes**: Executed when status is removed (if roll succeeds or unconditionally).

#### `OnRemoveFail`
- **Type**: StatsFunctors
- **Notes**: Executed when remove roll fails.

#### `OnRemoveFunctors`
- **Type**: StatsFunctors
- **Notes**: Always-execute functors on removal.

### General Success/Fail

#### `OnSuccess`
- **Type**: StatsFunctors
- **Values**: `"RegainHitPoints(1)"` (DOWNED — stabilized)
- **Notes**: General success functor. Used in DOWNED for successful death save stabilization.

#### `OnRollsFailed`
- **Type**: StatsFunctors
- **Values**: `"ApplyStatus(DYING,100,-1,DoT)"` (DOWNED — failed death saves)
- **Notes**: Executed when all rolls have failed. Used in DOWNED when 3 death saves fail.

### Aura System (BOOST)

#### `AuraRadius`
- **Type**: ConstantInt
- **Values**: `"2"`, `"3"`, `"6"`, `"9"`, `"10"`, `"18"`, `"30"`
- **Notes**: Aura effect radius in meters. Used by BOOST statuses to create persistent area effects.

#### `AuraStatuses`
- **Type**: StatsFunctors
- **Values**: `"TARGET:IF(not Dead() and Ally()):ApplyStatus(AURA_OF_PROTECTION,100,1)"`, `"TARGET:IF(Enemy() and not Dead()):ApplyStatus(FRIGHTFUL_PRESENCE_FRIGHTENED,100,1)"`, `"TARGET:IF(not Self() and not Dead()):DealDamage(1d4+WisdomModifier,Radiant)"`
- **Notes**: Status functors applied to targets within the aura radius. Always uses `TARGET:` prefix. Complex `IF(condition):` filtering for ally/enemy/self. Fires each tick.

#### `AuraFlags`
- **Type**: AuraFlags (flags enum)
- **Values**: `"IgnoreItems"`
- **Notes**: Aura behavior modifiers. `"IgnoreItems"` = don't affect items in the aura.

#### `AuraFX`
- **Type**: FixedString
- **Values**: UUID
- **Notes**: Visual effect for the aura.

### Target Conditions

#### `TargetConditions`
- **Type**: FixedString
- **Values**: `"Character() and not Dead()"`, `"not Self() and Ally()"`, `"Enemy()"`
- **Notes**: Conditions for who can be affected by this status.

### DOWNED-Specific Fields

#### `StableRoll`
- **Type**: FixedString
- **Values**: `"1d20"`
- **Notes**: Die roll for death saves.

#### `StableRollDC`
- **Type**: ConstantInt
- **Values**: `"10"`, `"15"`
- **Notes**: DC for death saves. Standard D&D 5e = 10.

#### `NumStableSuccess`
- **Type**: ConstantInt
- **Values**: `"1"`, `"3"`
- **Notes**: Number of death save successes to stabilize. Standard = 3. `"1"` for instant-stabilize variants.

#### `NumStableFailed`
- **Type**: ConstantInt
- **Values**: `"1"`, `"3"`
- **Notes**: Number of death save failures to die. Standard = 3.

#### `UseLyingPickingState`
- **Type**: YesNo
- **Values**: `"Yes"`
- **Notes**: Use the lying-down animation/picking state.

### HEAL-Specific Fields

#### `HealValue`
- **Type**: FixedString
- **Values**: `"100"`, `"1d8+SpellcastingAbilityModifier"`, `"2d8+WisdomModifier"`
- **Notes**: Heal amount expression. Can be static (`"100"`) or dice + modifier.

#### `HealType`
- **Type**: HealValueType (enum)
- **Values**: `"Qualifier"`, `"Fixed"`, `"Percentage"`
- **Notes**: How the heal value is calculated.

#### `HealStat`
- **Type**: StatusHealType (enum)
- **Values**: `"Vitality"`
- **Notes**: What resource to heal.

#### `HealMultiplier`
- **Type**: ConstantInt
- **Values**: `"100"`, `"200"`, `"50"`
- **Notes**: Percentage multiplier for heal value.

#### `HealEffectId`
- **Type**: FixedString
- **Values**: VFX identifier
- **Notes**: Visual effect for healing.

### POLYMORPHED-Specific Fields

#### `PolymorphResult`
- **Type**: FixedString
- **Values**: Stat entry name
- **Notes**: Target form for polymorph (references a Character stat entry).

#### `RetainSpells`
- **Type**: FixedString
- **Values**: Semicolon-separated spell names
- **Notes**: Spells retained from the original form during polymorph.

#### `Projectile`
- **Type**: FixedString
- **Values**: UUID or template
- **Notes**: Projectile template for polymorphed form.

#### `DisableInteractions`
- **Type**: YesNo
- **Values**: `"Yes"`
- **Notes**: Disables normal interactions while polymorphed.

#### `TemplateID`
- **Type**: FixedString
- **Values**: UUID
- **Notes**: Template UUID for the polymorphed visual form.

#### `Rules`
- **Type**: Guid
- **Values**: UUID
- **Notes**: Rule set UUID governing polymorph behavior.

### Stats & Identity

#### `StatsId`
- **Type**: FixedString
- **Values**: Character entry name
- **Notes**: References a Character stat entry (for polymorphed forms, summoned creatures).

#### `WeaponOverride`
- **Type**: FixedString
- **Values**: Weapon entry name
- **Notes**: Overrides the wielded weapon while status is active.

#### `ResetCooldowns`
- **Type**: FixedString
- **Values**: Spell entry name
- **Notes**: Cooldowns to reset when status is applied/removed.

#### `BonusFromSkill`
- **Type**: Skill (enum)
- **Notes**: Derives a bonus from a skill score.

### Visual & Animation

#### `StatusEffect`
- **Type**: FixedString
- **Values**: UUID
- **Notes**: Primary VFX displayed while status is active.

#### `StatusEffectOnTurn`
- **Type**: FixedString
- **Values**: UUID
- **Notes**: VFX played each turn.

#### `StatusEffectOverride`
- **Type**: FixedString
- **Values**: Status entry name
- **Notes**: Overrides VFX with another status's VFX.

#### `StatusEffectOverrideForItems`
- **Type**: FixedString
- **Values**: UUID
- **Notes**: VFX override specifically for items.

#### `ApplyEffect`
- **Type**: FixedString
- **Values**: UUID
- **Notes**: VFX played when status is applied.

#### `EndEffect`
- **Type**: FixedString
- **Values**: UUID
- **Notes**: VFX played when status expires/is removed.

#### `TargetEffect`
- **Type**: FixedString
- **Values**: UUID
- **Notes**: VFX on the target.

#### `BeamEffect`
- **Type**: FixedString
- **Values**: UUID
- **Notes**: Beam VFX (tether/link effects).

#### `MeshEffect`
- **Type**: FixedString
- **Values**: UUID
- **Notes**: Mesh overlay effect.

#### `AnimationStart`
- **Type**: FixedString
- **Values**: Animation name
- **Notes**: Animation played when status starts.

#### `AnimationLoop`
- **Type**: FixedString
- **Values**: Animation name
- **Notes**: Looping animation while status is active.

#### `AnimationEnd`
- **Type**: FixedString
- **Values**: Animation name
- **Notes**: Animation played when status ends.

#### `StillAnimationType`
- **Type**: StatusAnimationType (enum)
- **Values**: Animation type
- **Notes**: Idle animation override while status is active.

#### `StillAnimationPriority`
- **Type**: StillAnimPriority (enum)
- **Values**: Priority level
- **Notes**: Priority for the idle animation override.

#### `DynamicAnimationTag`
- **Type**: Guid
- **Values**: UUID
- **Notes**: Animation tag UUID for dynamic animation selection.

#### `HitAnimationType`
- **Type**: HitAnimationType (enum)
- **Values**: `"Default"`, `"None"`
- **Notes**: Hit reaction animation override.

### Material System

#### `Material`
- **Type**: FixedString
- **Values**: Material asset path
- **Notes**: Material/shader override. Used for visual effects like ice encasement, stone petrification.

#### `MaterialType`
- **Type**: MaterialType (enum)
- **Values**: `"Replacement"`, `"FadingOverlay"`, `"Overlay"`
- **Notes**: How the material is applied. `"Replacement"` replaces the base material, `"Overlay"` layers on top, `"FadingOverlay"` fades in.

#### `MaterialApplyBody`
- **Type**: YesNo
- **Values**: `"Yes"`, `"No"`
- **Notes**: Apply material to the body mesh.

#### `MaterialApplyArmor`
- **Type**: YesNo
- **Values**: `"Yes"`, `"No"`
- **Notes**: Apply material to armor meshes.

#### `MaterialApplyWeapon`
- **Type**: YesNo
- **Values**: `"Yes"`, `"No"`
- **Notes**: Apply material to weapon meshes.

#### `MaterialApplyNormalMap`
- **Type**: YesNo
- **Values**: `"Yes"`, `"No"`
- **Notes**: Apply normal map from the material.

#### `MaterialFadeAmount`
- **Type**: ConstantInt
- **Values**: `"3000"`
- **Notes**: Material fade duration in milliseconds.

#### `MaterialOverlayOffset`
- **Type**: ConstantInt
- **Notes**: Material overlay Z-offset.

#### `MaterialParameters`
- **Type**: FixedString
- **Values**: `"freezeDirection:SourceDirection"`, `"CharacterHeight:Height"`
- **Notes**: Colon-separated key:value material parameters. `freezeDirection:SourceDirection` for directional freeze effects.

### Sound

#### `SoundStart`
- **Type**: FixedString
- **Values**: Sound event name
- **Notes**: Sound played when status starts.

#### `SoundLoop`
- **Type**: FixedString
- **Values**: Sound event name
- **Notes**: Looping sound while status is active.

#### `SoundStop`
- **Type**: FixedString
- **Values**: Sound event name
- **Notes**: Sound played when status ends.

#### `SoundVocalStart`
- **Type**: SoundVocalType (enum)
- **Values**: Vocal type ID
- **Notes**: Vocal sound on status start.

#### `SoundVocalLoop`
- **Type**: SoundVocalType (enum)
- **Values**: Vocal type ID
- **Notes**: Looping vocal sound.

#### `SoundVocalEnd`
- **Type**: SoundVocalType (enum)
- **Values**: Vocal type ID
- **Notes**: Vocal sound on status end.

#### `StatusSoundState`
- **Type**: FixedString
- **Values**: Sound state name
- **Notes**: Ambient sound state override while status is active.

### Miscellaneous

#### `DieAction`
- **Type**: FixedString
- **Values**: Action expression
- **Notes**: Action performed when the status-holder dies.

#### `LeaveAction`
- **Type**: FixedString
- **Values**: Action expression
- **Notes**: Action performed when the status-holder leaves the area.

#### `Radius`
- **Type**: ConstantInt
- **Values**: `"2"`, `"6"`, `"9"`, `"18"`
- **Notes**: General effect radius. Different from AuraRadius — used for non-aura area effects.

#### `SurfaceChange`
- **Type**: FixedString
- **Values**: Surface change expression
- **Notes**: Surface modification when status is active (e.g., freezing water).

#### `AbsorbSurfaceRange`
- **Type**: ConstantInt
- **Notes**: Range for surface absorption effects.

#### `AbsorbSurfaceType`
- **Type**: FixedString
- **Notes**: Surface type to absorb.

#### `Sheathing`
- **Type**: StatusSheathing (enum)
- **Values**: `"Somatic"`, `"DontChange"`, `"Sheathed"`
- **Notes**: Weapon sheathing behavior during status.

#### `DefendTargetPosition`
- **Type**: YesNo
- **Notes**: Whether the status-holder defends a position.

#### `Items`
- **Type**: FixedString
- **Notes**: Item references associated with the status.

#### `PlayerHasTag`
- **Type**: FixedString
- **Values**: Tag string
- **Notes**: Tag check on the player.

#### `PlayerSameParty`
- **Type**: YesNo
- **Notes**: Whether the player must be in the same party.

#### `PerformEventName`
- **Type**: FixedString
- **Notes**: Performance event name (for bard performances).

#### `FreezeTime`
- **Type**: ConstantInt
- **Notes**: Time freeze duration.

#### `HideOverheadUI`
- **Type**: ConstantInt
- **Values**: `"0"`, `"1"`
- **Notes**: Boolean. Hides overhead health/status UI.

#### `ManagedStatusEffectGroup`
- **Type**: FixedString
- **Notes**: Effect group for managed status systems.

#### `ManagedStatusEffectType`
- **Type**: ManagedStatusEffectType (enum)
- **Values**: `"Positive"`, `"Negative"`, `"Neutral"`
- **Notes**: Classification for UI display (buff/debuff/neutral).

#### `LEDEffect`
- **Type**: LEDEffectType (enum)
- **Notes**: LED peripheral effect for compatible hardware (keyboard/mouse RGB).

#### `SplatterBloodAmount`
- **Type**: ConstantFloat
- **Values**: `"0"` to `"1"` (normalized)
- **Notes**: Blood splatter intensity on the character model.

#### `SplatterDirtAmount`
- **Type**: ConstantFloat
- **Values**: `"0"` to `"1"`
- **Notes**: Dirt splatter intensity.

#### `SplatterSweatAmount`
- **Type**: ConstantFloat
- **Values**: `"0"` to `"1"`
- **Notes**: Sweat splatter intensity.

#### `AiCalculationSpellOverride`
- **Type**: FixedString
- **Notes**: AI uses a different spell's parameters for evaluation.

### Tooltips

#### `TooltipDamage`
- **Type**: FixedString
- **Values**: `"DealDamage(1d4,Fire)"`, `"DealDamage(2d6,Necrotic,Magical)"`
- **Notes**: Tooltip damage display.

#### `TooltipSave`
- **Type**: FixedString
- **Values**: `"ConstitutionSavingThrow"`, `"WisdomSavingThrow"`
- **Notes**: Tooltip save type display.

#### `TooltipPermanentWarnings`
- **Type**: FixedString
- **Notes**: Permanent tooltip warnings.

---

## Cross-References

| From | To | Via |
|------|----|----|
| StatusData.StackId | StatusData | Stacking interaction |
| StatusData.Boosts | Boosts reference | [functors-boosts.md](../reference/functors-boosts.md) |
| StatusData.Passives | PassiveData | Passive entry names |
| StatusData.Spells | SpellData | Spell entry names |
| StatusData.AuraStatuses | StatusData | `ApplyStatus(NAME,...)` references |
| StatusData.StatusGroups | ValueLists | StatusGroupFlags enum |
| StatusData.StatsId | Character | Character stat entry |
| StatusData.WeaponOverride | Weapon | Weapon stat entry |
| StatusData.PolymorphResult | Character | Character stat entry |
| SpellData.SpellSuccess | StatusData | `ApplyStatus(NAME,...)` references |

## Caveats & Gotchas

- **StatusType is mandatory**: Every entry must specify StatusType, even though all subtypes share the same field pool.
- **StackId = entry name convention**: By convention, StackId matches the entry name, but this is not enforced. Different statuses can share a StackId to interact.
- **Tick functors need TickType**: Setting `TickFunctors` without `TickType` means the functors never fire. Always pair them.
- **AuraStatuses needs AuraRadius**: An aura without a radius has no area. Always set both.
- **OnApplyRoll inversion**: Like SpellData's SpellRoll, `"not SavingThrow(...)"` means the status applies on a failed save (the "not" inverts the save success into a "status succeeds" condition).
- **Boosts vs TickFunctors**: `Boosts` are passive (always-on while status is active). `TickFunctors` fire once per tick. Damage-over-time uses TickFunctors, not Boosts.
- **DOWNED death saves**: `StableRoll` + `StableRollDC` + `NumStableSuccess` + `NumStableFailed` form the complete death save system. `OnSuccess` fires on stabilization, `OnRollsFailed` fires on total failure.
- **MaterialParameters format**: Uses `key:value` with colon separator. `freezeDirection:SourceDirection` tells the shader which direction the freeze spreads from.
- **AI_ONLY prefix**: In TickFunctors, `AI_ONLY:` prefix means the functor only executes for AI-controlled characters (prevents griefy DoT on player).
- **Conditional functor scope**: `IF(Condition):Functor1(args);Functor2(args)` — the `IF()` only applies to `Functor1`. For multiple conditional TickFunctors or OnApplyFunctors, repeat: `IF(Condition):Functor1(args);IF(Condition):Functor2(args)`.
- **DealDamage CoinMultiplier null**: In TickFunctors, `DealDamage` arg 5 (CoinMultiplier) does NOT accept empty — use `0`. An empty arg silently fails.
- **OnDamage loop risk**: TickFunctors using `DealDamage` that trigger `OnDamage` passives can loop infinitely. Use `IgnoreOnDamage=true` (arg 8): `DealDamage(1d6,Fire,,0,,true)`.
- **OnStatusApply/Applied loop risk**: Passives with `OnStatusApply` or `OnStatusApplied` context that apply statuses can loop. The engine applies background statuses which re-trigger these contexts.
- **Cross-format name matching**: `Spells`, `Passives`, `AuraStatuses` fields reference entry names and are **case-sensitive**. Mismatches fail silently.
- **Inheritance load order**: `using "ParentStatus"` requires the parent in the same file or an earlier-loaded file. Forward references fail silently.
- **StatusGroups membership**: Statuses can belong to groups (SG_Condition, SG_Charmed, etc.) via `StatusGroups`. Group-based immunity (`PersonalStatusImmunities`) blocks all members of the group.
- **TECHNICAL suffix convention**: Some vanilla statuses have `_TECHNICAL` suffix variants that handle internal mechanics. E.g., `BURNING_TECHNICAL` applies the actual damage while `BURNING` is the visible status.

---

## Scripting & Runtime Notes

### Script Extender (SE) Lua

```lua
-- Read status stats
local stat = Ext.Stats.Get("BURNING")
local statusType = stat.StatusType
local tickFunctors = stat.TickFunctors

-- Modify at runtime (MUST sync after)
stat.Boosts = "Resistance(Fire,Vulnerable)"
Ext.Stats.Sync("BURNING")
```

> **CRITICAL:** `Ext.Stats.Sync()` is mandatory after any runtime change — without it modifications are invisible.

### Osiris Events

| Event | Signature | Relevance |
|-------|-----------|----------|
| `StatusApplied` | `(obj, status, causee, storyId)` | Fires when any status is applied |
| `StatusRemoved` | `(obj, status)` | Fires when any status expires or is removed |
| `Died` | `(entity, cause)` | Track deaths from DoT statuses |
| `ShortRested` | `(character, resting)` | Some statuses clear on rest |
| `LongRestFinished` | `(character, resting)` | Most statuses clear on long rest |

### Osiris Status Manipulation

```lua
-- Apply a status via Osiris
ApplyStatus(targetGuid, "BURNING", duration, sourceGuid)

-- Remove a status
RemoveStatus(targetGuid, "BURNING")

-- Check if active
IF HasActiveStatus(_Char, "BURNING", 1)
THEN ...
```
