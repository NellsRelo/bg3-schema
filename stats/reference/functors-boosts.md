# BG3 Stats: Functors, Boosts & Enumerations Reference

> Complete reference for all Stats functors, boosts, description params, and their associated enumerations.

### Type Distinction

| LSLib Type | Used In |
|------------|----------|
| `Type="Functor"` | `SpellProperties`, `SpellSuccess`, `OnApplyFunctors`, `StatsFunctors`, etc. |
| `Type="Boost"` | `Boosts`, `BoostsOnEquip`, `PassiveBoosts`, Status `Boosts`, etc. |

---

## 1. Functors

Functors are executable actions used in fields like `SpellProperties`, `SpellSuccess`, `OnApplyFunctors`, `StatsFunctors`, etc.

> **Syntax:** `CastEvent[TARGETING:IF(Condition):Functor(arg1,arg2,,arg4)];`

### AdjustRoll
- **Arguments:**
  - (Required) `Amount`: Lua
  - `Type`: RollAdjustmentType
  - `DamageType`: Damage Type

### ApplyEquipmentStatus
- **Arguments:**
  - (Required) `ItemSlot`: StatItemSlot
  - (Required) `StatusId`: StatusId
  - `Chance`: Int
  - `Duration`: Lua
  - `StatusSpecificParam1`: String
  - `StatusSpecificParam2`: Int
  - `StatusSpecificParam3`: Int
  - `StatsConditions`: Conditions
  - `RequiresConcentration`: Boolean

### ApplyStatus
- **Arguments:**
  - (Required) `StatusId`: StatusId
  - `Chance`: Int
  - `Duration`: Lua
  - `StatusSpecificParam1`: String
  - `StatusSpecificParam2`: Int
  - `StatusSpecificParam3`: Int
  - `StatsConditions`: Conditions
  - `RequiresConcentration`: Boolean

### BreakConcentration
- No arguments.

### CameraWait
- **Arguments:**
  - `Arg1`: Float

### Counterspell
- No arguments.

### CreateConeSurface
- **Arguments:**
  - (Required) `Radius`: Float
  - (Required) `Duration`: Float
  - (Required) `SurfaceType`: Surface Type
  - `IsControlledByConcentration`: Boolean

### CreateExplosion
- **Arguments:**
  - `SpellId`: SpellId

### CreateSurface
- **Arguments:**
  - (Required) `Radius`: Float
  - (Required) `Duration`: Float
  - (Required) `SurfaceType`: Surface Type
  - `IsControlledByConcentration`: Boolean

### CreateWall
- No arguments.

### CreateZone
- **Arguments:**
  - `Shape`: ZoneShape
  - `Arg2`: Float
  - `Duration`: Float
  - `Arg4`: String
  - `Arg5`: Boolean

### DealDamage
- **Arguments:**
  - (Required) `Damage`: Lua
  - `DamageType`: DamageTypeOrDealDamageWeaponDamageType
  - `Magical`: Magical
  - `Nonlethal`: Nonlethal
  - `CoinMultiplier`: Int
  - `Tooltip`: Guid
  - `IgnoreDamageBonus`: Boolean
  - `IgnoreOnDamage`: Boolean
  - `ConsumeCoin`: Boolean
  - `IgnoreImmune`: Boolean
- **Notes:** Arg5 (`CoinMultiplier`) does not accept null — use `0` to skip. Arg7 (`IgnoreDamageBonus`) and Arg8 (`IgnoreOnDamage`) control whether `OnDamage`/`OnDamaged` contexts trigger.

### DisarmAndStealWeapon
- No arguments.

### DisarmWeapon
- No arguments.

### DoTeleport
- **Arguments:**
  - `Arg1`: Float

### Douse
- **Arguments:**
  - `Radius`: Float
  - `Arg2`: Float

### Drop
- **Arguments:**
  - `Effect`: String

### ExecuteWeaponFunctors
- **Arguments:**
  - `WeaponType`: ExecuteWeaponFunctorsType

### FireProjectile
- **Arguments:**
  - (Required) `ProjectileTemplate`: String

### Force
- **Arguments:**
  - (Required) `Distance`: Lua
  - `Origin`: ForceFunctorOrigin
  - `Aggression`: ForceFunctorAggression
  - `ControlArc`: Boolean
  - `CanStand`: Boolean

### GainTemporaryHitPoints
- **Arguments:**
  - (Required) `Amount`: Lua

### Kill
- No arguments.

### MaximizeRoll
- **Arguments:**
  - (Required) `DamageType`: Damage Type

### Pickup
- **Arguments:**
  - `Effect`: String

### RegainHitPoints
- **Arguments:**
  - (Required) `HitPoints`: Lua
  - `Type`: ResurrectType

### RegainTemporaryHitPoints
- **Arguments:**
  - (Required) `Amount`: Lua

### RemoveAuraByChildStatus
- **Arguments:**
  - (Required) `StatusId`: StatusId

### RemoveStatus
- **Arguments:**
  - (Required) `StatusId`: StatusIdOrGroup

### RemoveStatusByLevel
- **Arguments:**
  - (Required) `StatusId`: StatusIdOrGroup
  - `Level`: Int
  - `Ability`: Ability

### RemoveUniqueStatus
- **Arguments:**
  - (Required) `StatusId`: StatusId

### ResetCombatTurn
- No arguments.

### ResetCooldowns
- **Arguments:**
  - (Required) `Type`: SpellCooldownType

### RestoreResource
- **Arguments:**
  - (Required) `ActionResource`: String
  - (Required) `Amount`: LuaOrPercentage
  - `Level`: Int

### Resurrect
- **Arguments:**
  - `Chance`: Float
  - `HealthPercentage`: Float
  - `Type`: ResurrectTypes

### Sabotage
- **Arguments:**
  - `Amount`: Int

### SetAdvantage
- No arguments.

### SetDamageResistance
- **Arguments:**
  - (Required) `DamageType`: Damage Type

### SetDisadvantage
- No arguments.

### SetReroll
- **Arguments:**
  - `Roll`: Int
  - `KeepNew`: Boolean

### SetRoll
- **Arguments:**
  - (Required) `Roll`: Int
  - `DistributionOrDamageType`: RollAdjustmentTypeOrDamageType

### SetStatusDuration
- **Arguments:**
  - (Required) `StatusId`: StatusId
  - (Required) `Duration`: Float
  - `ChangeType`: SetStatusDurationType

### ShortRest
- No arguments.

### Spawn
- **Arguments:**
  - (Required) `TemplateId`: Guid
  - `AiHelper`: String
  - `StatusToApply1`: StatusId
  - `StatusToApply2`: StatusId
  - `StatusToApply3`: StatusId
  - `StatusToApply4`: StatusId
  - `ApplyLateJoinPenalty`: Boolean

### SpawnExtraProjectiles
- **Arguments:**
  - `ProjectileSpell`: String

### SpawnInInventory
- **Arguments:**
  - (Required) `TemplateId`: Guid
  - `Amount`: Int
  - `PlaceInInventory`: Boolean
  - `Equip`: Boolean
  - `AllowOffHand`: Boolean
  - `AiSpellOverride`: String
  - `StatusToApply1`: String
  - `StatusToApply2`: String
  - `StatusToApply3`: String
  - `StatusToApply4`: String

### Stabilize
- No arguments.

### Summon
- **Arguments:**
  - (Required) `Template`: Guid
  - `Duration`: SummonDurationOrInt
  - `AiSpellOverride`: SpellId
  - `ExtendExistingConcentration`: Boolean
  - `StackId`: String
  - `StatusToApply1`: StatusId
  - `StatusToApply2`: StatusId
  - `StatusToApply3`: StatusId
  - `StatusToApply4`: StatusId
  - `LateJoinPenalty`: Boolean
  - `UseOwnerPassives`: Boolean

### SummonInInventory
- **Arguments:**
  - (Required) `TemplateId`: Guid
  - `Duration`: SummonDurationOrInt
  - `Amount`: Int
  - `EquipItem`: Boolean
  - `Equip`: Boolean
  - `AllowOffHand`: Boolean
  - `ExtendExistingConcentration`: Boolean
  - `AiSpellOverride`: String
  - `SpellContainer`: String
  - `StatusToApply1`: String
  - `StatusToApply2`: String
  - `StatusToApply3`: String
  - `StatusToApply4`: String

### SurfaceChange
- **Arguments:**
  - (Required) `SurfaceChange`: Surface Change
  - `Chance`: Float
  - `DetourMaxWaitTime`: Float
  - `Arg4`: Float
  - `Radius`: Float

### SurfaceClearLayer
- **Arguments:**
  - `Layer1`: SurfaceLayer
  - `Layer2`: SurfaceLayer

### SwapPlaces
- **Arguments:**
  - `Animation`: String
  - `Arg2`: Boolean
  - `Arg3`: Boolean

### SwitchDeathType
- **Arguments:**
  - (Required) `DeathType`: Death Type

### TeleportSource
- **Arguments:**
  - `FindValidPosition`: Boolean
  - `RotateTowardsTarget`: Boolean

### TriggerRandomCast
- **Arguments:**
  - (Required) `DC`: Int
  - (Required) `Delay`: Float
  - `RandomCastOutcome1`: String
  - `RandomCastOutcome2`: String
  - `RandomCastOutcome3`: String
  - `RandomCastOutcome4`: String

### TutorialEvent
- **Arguments:**
  - `Event`: Guid

### Unlock
- No arguments.

### Unsummon
- No arguments.

### UseActionResource
- **Arguments:**
  - (Required) `ActionResource`: String
  - `Amount`: FloatOrPercentage
  - `Level`: Int
  - `IgnoreResourceConsumeBoosts`: Boolean

### UseAttack
- **Arguments:**
  - `IgnoreChecks`: Boolean
  - `IgnoreBlindness`: Boolean

### UseSpell
- **Arguments:**
  - (Required) `SpellId`: SpellId
  - `IgnoreHasSpell`: Boolean
  - `IgnoreChecks`: Boolean
  - `Arg4`: Boolean
  - `SpellCastGuid`: Guid
  - `IgnoreBlindness`: Boolean

---

## 2. Boosts

Boosts are passive modifiers used in fields like `Boosts`, `BoostsOnEquip`, `PassiveBoosts`, Status `Boosts`, etc.

> **Syntax:** `IF(Condition):Boost(arg1,arg2,,arg4);`

### AC
- **Arguments:**
  - (Required) `AC`: Int

### ACOverrideFormula
- **Arguments:**
  - (Required) `AC`: Int
  - (Required) `Arg2`: Boolean
  - `Ability1`: Ability
  - `Ability2`: Ability
  - `Ability3`: Ability

### Ability
- **Arguments:**
  - (Required) `Ability`: Ability
  - (Required) `Amount`: Int
  - `Cap`: Int
  - `Arg4`: Boolean

### AbilityFailedSavingThrow
- **Arguments:**
  - (Required) `Ability`: Ability

### AbilityOverrideMinimum
- **Arguments:**
  - (Required) `Ability`: Ability
  - (Required) `Minimum`: Int
  - `Arg3`: Boolean

### ActionResource
- **Arguments:**
  - (Required) `Resource`: String
  - (Required) `Amount`: Float
  - `Level`: Int
  - `DieType`: DieType

### ActionResourceBlock
- **Arguments:**
  - (Required) `Resource`: String
  - `Level`: Int

### ActionResourceConsumeMultiplier
- **Arguments:**
  - (Required) `Resource`: String
  - (Required) `Multiplier`: Float
  - (Required) `Level`: Int

### ActionResourceMultiplier
- **Arguments:**
  - (Required) `Resource`: String
  - (Required) `Multiplier`: Int
  - `Level`: Int

### ActionResourceOverride
- **Arguments:**
  - (Required) `Resource`: String
  - (Required) `Amount`: Float
  - `Level`: Int
  - `DieType`: DieType

### ActionResourcePreventReduction
- **Arguments:**
  - (Required) `ActionResource`: String
  - `Level`: Int

### ActionResourceReplenishTypeOverride
- **Arguments:**
  - (Required) `ActionResource`: String
  - (Required) `ReplenishType`: ResourceReplenishType

### ActiveCharacterLight
- **Arguments:**
  - (Required) `Light`: String

### AddProficiencyToAC
- No arguments.

### AddProficiencyToDamage
- No arguments.

### AdvanceSpells
- **Arguments:**
  - (Required) `SpellId`: SpellId
  - `Arg2`: Int

### Advantage
- **Arguments:**
  - (Required) `Type`: AdvantageContext
  - `Arg2`: String
  - `Tag1`: String
  - `Tag2`: String
  - `Tag3`: String

### AiArchetypeOverride
- **Arguments:**
  - (Required) `Archetype`: String
  - `Arg2`: Int

### AreaDamageEvade
- No arguments.

### ArmorAbilityModifierCapOverride
- **Arguments:**
  - (Required) `ArmorType`: ArmorType
  - (Required) `Cap`: Int

### AttackSpellOverride
- **Arguments:**
  - (Required) `AttackSpell`: SpellId
  - `OriginalSpell`: SpellId

### Attribute
- **Arguments:**
  - (Required) `Flags`: AttributeFlags

### BlockAbilityModifierDamageBonus
- No arguments.

### BlockAbilityModifierFromAC
- **Arguments:**
  - (Required) `Ability`: Ability

### BlockGatherAtCamp
- No arguments.

### BlockRegainHP
- **Arguments:**
  - `Type`: ResurrectTypes

### BlockSomaticComponent
- No arguments.

### BlockSpellCast
- **Arguments:**
  - `Arg1`: Float

### BlockTravel
- No arguments.

### BlockVerbalComponent
- No arguments.

### CanSeeThrough
- **Arguments:**
  - (Required) `CanSeeThrough`: Boolean

### CanShootThrough
- **Arguments:**
  - (Required) `CanShootThrough`: Boolean

### CanWalkThrough
- **Arguments:**
  - (Required) `CanWalkThrough`: Boolean

### CannotBeDisarmed
- No arguments.

### CannotHarmCauseEntity
- **Arguments:**
  - (Required) `Type`: String

### CarryCapacityMultiplier
- **Arguments:**
  - (Required) `Multiplier`: Float

### CharacterUnarmedDamage
- **Arguments:**
  - (Required) `Damage`: Lua
  - `DamageType`: Damage Type

### CharacterWeaponDamage
- **Arguments:**
  - (Required) `Amount`: Lua
  - `DamageType`: Damage Type

### ConcentrationIgnoreDamage
- **Arguments:**
  - (Required) `SpellSchool`: SpellSchool

### ConsumeItemBlock
- No arguments.

### CriticalDamageOnHit
- No arguments.

### CriticalHit
- **Arguments:**
  - (Required) `Type`: CriticalHitType
  - (Required) `Result`: CriticalHitResult
  - (Required) `When`: CriticalHitWhen
  - `Arg4`: Float

### CriticalHitExtraDice
- **Arguments:**
  - (Required) `ExtraDice`: Int
  - `AttackType`: AttackType

### DamageBonus
- **Arguments:**
  - (Required) `Amount`: Lua
  - `DamageType`: Damage Type
  - `Arg3`: Boolean

### DamageReduction
- **Arguments:**
  - (Required) `DamageType`: AllOrDamageType
  - (Required) `ReductionType`: DamageReductionType
  - `Amount`: Lua

### DamageTakenBonus
- **Arguments:**
  - (Required) `Amount`: Lua
  - `DamageType`: Damage Type
  - `Arg3`: Boolean

### DarkvisionRange
- **Arguments:**
  - (Required) `Range`: Float

### DarkvisionRangeMin
- **Arguments:**
  - (Required) `Range`: Float

### DarkvisionRangeOverride
- **Arguments:**
  - (Required) `Range`: Float

### Detach
- No arguments.

### DetectDisturbancesBlock
- **Arguments:**
  - (Required) `Arg1`: Boolean

### DialogueBlock
- No arguments.

### Disadvantage
- **Arguments:**
  - (Required) `Type`: AdvantageContext
  - `Arg2`: String
  - `Tag1`: String
  - `Tag2`: String
  - `Tag3`: String

### DodgeAttackRoll
- **Arguments:**
  - (Required) `Arg1`: Int
  - (Required) `Arg2`: Int
  - `Status`: StatusIdOrGroup

### DownedStatus
- **Arguments:**
  - (Required) `StatusId`: StatusId
  - `Priority`: Int

### DualWielding
- **Arguments:**
  - (Required) `DW`: Boolean

### EnableBasicItemInteractions
- No arguments.

### EntityThrowDamage
- **Arguments:**
  - (Required) `Die`: String
  - `DamageType`: Damage Type

### ExpertiseBonus
- **Arguments:**
  - (Required) `Skill`: SkillType

### FactionOverride
- **Arguments:**
  - (Required) `Faction`: String

### FallDamageMultiplier
- **Arguments:**
  - (Required) `Multiplier`: Float

### GameplayLight
- **Arguments:**
  - (Required) `Distance`: Float
  - (Required) `Arg2`: Boolean
  - `Arg3`: Float
  - `Sunlight`: Boolean

### GameplayObscurity
- **Arguments:**
  - (Required) `Obscurity`: Float

### GuaranteedChanceRollOutcome
- **Arguments:**
  - (Required) `Arg1`: Boolean

### HalveWeaponDamage
- **Arguments:**
  - (Required) `Ability`: Ability

### HiddenDuringCinematic
- No arguments.

### HorizontalFOVOverride
- **Arguments:**
  - (Required) `FOV`: Float

### IgnoreDamageThreshold
- **Arguments:**
  - (Required) `DamageType`: AllOrDamageType
  - (Required) `Threshold`: Int

### IgnoreEnterAttackRange
- No arguments.

### IgnoreFallDamage
- No arguments.

### IgnoreLeaveAttackRange
- No arguments.

### IgnoreLowGroundPenalty
- **Arguments:**
  - (Required) `RollType`: StatsRollType

### IgnorePointBlankDisadvantage
- **Arguments:**
  - (Required) `Flags`: WeaponFlags

### IgnoreResistance
- **Arguments:**
  - (Required) `DamageType`: Damage Type
  - (Required) `Flags`: ResistanceBoostFlags

### IgnoreSurfaceCover
- **Arguments:**
  - (Required) `SurfaceType`: String

### IncreaseMaxHP
- **Arguments:**
  - (Required) `Amount`: String

### Initiative
- **Arguments:**
  - (Required) `Initiative`: Int

### IntrinsicSourceProficiency
- No arguments.

### IntrinsicSummonerProficiency
- No arguments.

### Invisibility
- No arguments.

### Invulnerable
- No arguments.

### ItemReturnToOwner
- No arguments.

### JumpMaxDistanceBonus
- **Arguments:**
  - (Required) `Bonus`: Float

### JumpMaxDistanceMultiplier
- **Arguments:**
  - (Required) `Multiplier`: Float

### LeaveTriggers
- No arguments.

### Lock
- **Arguments:**
  - `DC`: Guid

### Lootable
- No arguments.

### MaximizeHealing
- **Arguments:**
  - (Required) `Direction`: HealingDirection
  - `Type`: ResurrectType

### MaximumRollResult
- **Arguments:**
  - (Required) `RollType`: StatsRollType
  - (Required) `MinResult`: Int

### MinimumRollResult
- **Arguments:**
  - (Required) `RollType`: StatsRollType
  - (Required) `MinResult`: Int

### MonkWeaponAttackOverride
- No arguments.

### MonkWeaponDamageDiceOverride
- **Arguments:**
  - (Required) `Arg1`: Lua

### MovementSpeedLimit
- **Arguments:**
  - (Required) `Type`: MovementSpeedType

### NoAOEDamageOnLand
- No arguments.

### NoDamageOnThrown
- No arguments.

### NonLethal
- No arguments.

### NullifyAbilityScore
- **Arguments:**
  - (Required) `Ability`: Ability

### ObjectSize
- **Arguments:**
  - (Required) `Size`: Int

### ObjectSizeOverride
- **Arguments:**
  - (Required) `Size`: String

### PhysicalForceRangeBonus
- **Arguments:**
  - (Required) `Arg1`: String

### Proficiency
- **Arguments:**
  - (Required) `Arg1`: ProficiencyGroupFlags
  - `Arg2`: ProficiencyGroupFlags
  - `Arg3`: ProficiencyGroupFlags

### ProficiencyBonus
- **Arguments:**
  - (Required) `Type`: ProficiencyBonusBoostType
  - `AbilityOrSkill`: AbilityOrSkill

### ProficiencyBonusIncrease
- **Arguments:**
  - (Required) `Amount`: Int

### ProficiencyBonusOverride
- **Arguments:**
  - (Required) `Bonus`: Lua

### ProjectileDeflect
- **Arguments:**
  - `Type1`: String
  - `Type2`: String

### ReceivingCriticalDamageOnHit
- **Arguments:**
  - `Arg1`: Float

### RedirectDamage
- **Arguments:**
  - (Required) `Multiplier`: Float
  - `DamageTypeOut`: Damage Type
  - `DamageTypeIn`: Damage Type
  - `RedirectToDamageSource`: Boolean

### ReduceCriticalAttackThreshold
- **Arguments:**
  - (Required) `Threshold`: Int
  - `StatusId`: StatusIdOrGroup

### Reroll
- **Arguments:**
  - (Required) `RollType`: StatsRollType
  - (Required) `RollBelow`: Int
  - (Required) `RollAlways`: Boolean

### Resistance
- **Arguments:**
  - (Required) `DamageType`: AllOrDamageType
  - (Required) `ResistanceBoostFlags`: ResistanceBoostFlags

### RollBonus
- **Arguments:**
  - (Required) `RollType`: StatsRollType
  - (Required) `Bonus`: Lua
  - `AbilityOrSkill`: AbilityOrSkill

### Savant
- **Arguments:**
  - (Required) `SpellSchool`: SpellSchool

### ScaleMultiplier
- **Arguments:**
  - `Multiplier`: Float

### SightRangeAdditive
- **Arguments:**
  - (Required) `Range`: Float

### SightRangeMaximum
- **Arguments:**
  - (Required) `Range`: Float

### SightRangeMinimum
- **Arguments:**
  - (Required) `Range`: Float

### SightRangeOverride
- **Arguments:**
  - (Required) `Range`: Float

### Skill
- **Arguments:**
  - (Required) `Skill`: SkillType
  - (Required) `Amount`: Lua

### SoundsBlocked
- No arguments.

### SourceAdvantageOnAttack
- **Arguments:**
  - `Arg1`: Float

### SourceAllyAdvantageOnAttack
- No arguments.

### SpellResistance
- **Arguments:**
  - (Required) `Resistance`: ResistanceBoostFlags

### SpellSaveDC
- **Arguments:**
  - (Required) `DC`: Int

### StatusImmunity
- **Arguments:**
  - (Required) `StatusId`: StatusIdOrGroup
  - `Tag1`: String
  - `Tag2`: String
  - `Tag3`: String
  - `Tag4`: String
  - `Tag5`: String

### Tag
- **Arguments:**
  - (Required) `Tag`: String

### TemporaryHP
- **Arguments:**
  - (Required) `Amount`: Lua

### TwoWeaponFighting
- No arguments.

### UnarmedMagicalProperty
- No arguments.

### UnlockInterrupt
- **Arguments:**
  - (Required) `Interrupt`: Interrupt

### UnlockSpell
- **Arguments:**
  - (Required) `SpellId`: SpellId
  - `Type`: UnlockSpellType
  - `SpellGuid`: String
  - `Cooldown`: SpellCooldownType
  - `Ability`: Ability

### UnlockSpellVariant
- **Arguments:**
  - (Required) `Modification1`: Lua
  - `Modification2`–`Modification16`: Lua (up to 16 total)
- **Syntax:** `UnlockSpellVariant([conditions (khn)], Modifier1(), Modifier2(), ...)`
- **Notes:** The first argument is a Khonsu condition expression. Remaining arguments are spell variant modifiers — see **§5 Spell Variant Modifiers** for the full reference.

### UseBoosts
- **Arguments:**
  - (Required) `Boosts`: StatsFunctors

### VoicebarkBlock
- No arguments.

### WeaponAttackRollAbilityOverride
- **Arguments:**
  - (Required) `Ability`: AbilityOrAttackRollAbility

### WeaponAttackRollBonus
- **Arguments:**
  - (Required) `Amount`: Lua

### WeaponAttackTypeOverride
- **Arguments:**
  - (Required) `Type`: AttackType

### WeaponDamage
- **Arguments:**
  - (Required) `Amount`: Lua
  - (Required) `DamageType`: Damage Type
  - `Arg3`: Boolean

### WeaponDamageDieOverride
- **Arguments:**
  - (Required) `DamageDie`: String

### WeaponDamageResistance
- **Arguments:**
  - (Required) `DamageType1`: Damage Type
  - `DamageType2`: Damage Type
  - `DamageType3`: Damage Type

### WeaponDamageTypeOverride
- **Arguments:**
  - (Required) `DamageType`: Damage Type

### WeaponEnchantment
- **Arguments:**
  - (Required) `Enchantment`: Int

### WeaponProperty
- **Arguments:**
  - (Required) `Flags1`: WeaponFlags

### Weight
- **Arguments:**
  - (Required) `Weight`: Float

### WeightCategory
- **Arguments:**
  - (Required) `Category`: Int

---

## 3. Description Params

Description params are used in tooltip/description generation (`DescriptionParams` fields).

### ApplyStatus
- **Arguments:**
  - (Required) `StatusId`: StatusId
  - `Chance`: Int
  - `Duration`: Lua
  - `StatusSpecificParam1`: String
  - `StatusSpecificParam2`: Int
  - `StatusSpecificParam3`: Int
  - `StatsConditions`: Conditions
  - `RequiresConcentration`: Boolean

### DealDamage
- **Arguments:**
  - (Required) `Damage`: Lua
  - `DamageType`: DamageTypeOrDealDamageWeaponDamageType
  - `Magical`: Magical
  - `Nonlethal`: Nonlethal
  - `CoinMultiplier`: Int
  - `Tooltip`: Guid

### Distance
- **Arguments:**
  - (Required) `Distance`: Float

### GainTemporaryHitPoints
- **Arguments:**
  - (Required) `Amount`: Lua

### LevelMapValue
- **Arguments:**
  - (Required) `LevelMap`: String

### RegainHitPoints
- **Arguments:**
  - (Required) `HitPoints`: Lua
  - `Tooltip`: Guid

---

## 4. Enumerations

### AdvantageContext
`AttackRoll` · `AttackTarget` · `SavingThrow` · `AllSavingThrows` · `Ability` · `AllAbilities` · `Skill` · `AllSkills` · `SourceDialogue` · `DeathSavingThrow` · `Concentration`

### AllEnum
`All`

### AttackRollAbility
`SpellCastingAbility` · `UnarmedMeleeAbility` · `AttackAbility`

### AttackType
`DirectHit` · `MeleeWeaponAttack` · `RangedWeaponAttack` · `MeleeOffHandWeaponAttack` · `RangedOffHandWeaponAttack` · `MeleeSpellAttack` · `RangedSpellAttack` · `MeleeUnarmedAttack` · `RangedUnarmedAttack`

### CriticalHitResult
`Success` · `Failure`

### CriticalHitType
`AttackTarget` · `AttackRoll`

### CriticalHitWhen
`Never` · `Always` · `ForcedAlways`

### DamageReductionType
`Half` · `Flat` · `Threshold`

### DealDamageWeaponDamageType
`MainWeaponDamageType` · `OffhandWeaponDamageType` · `MainMeleeWeaponDamageType` · `OffhandMeleeWeaponDamageType` · `MainRangedWeaponDamageType` · `OffhandRangedWeaponDamageType` · `SourceWeaponDamageType` · `ThrownWeaponDamageType`

### EngineStatusType
`DYING` · `HEAL` · `KNOCKED_DOWN` · `TELEPORT_FALLING` · `BOOST` · `REACTION` · `STORY_FROZEN` · `SNEAKING` · `UNLOCK` · `FEAR` · `SMELLY` · `INVISIBLE` · `ROTATE` · `MATERIAL` · `CLIMBING` · `INCAPACITATED` · `INSURFACE` · `POLYMORPHED` · `EFFECT` · `DEACTIVATED` · `DOWNED`

### ExecuteWeaponFunctorsType
`MainHand` · `OffHand` · `BothHands`

### ForceFunctorAggression
`Aggressive` · `Friendly` · `Neutral`

### ForceFunctorOrigin
`OriginToEntity` · `OriginToTarget` · `TargetToEntity`

### HealingDirection
`Incoming` · `Outgoing`

### Magical
`Magical` · `Nonmagical`

### MovementSpeedType
`Stroll` · `Walk` · `Run` · `Sprint`

### Nonlethal
`Lethal` · `Nonlethal`

### ProficiencyBonusBoostType
`AttackRoll` · `AttackTarget` · `SavingThrow` · `AllSavingThrows` · `Ability` · `AllAbilities` · `Skill` · `AllSkills` · `SourceDialogue` · `WeaponActionDC`

### ResistanceBoostFlags
`None` · `Resistant` · `Immune` · `Vulnerable` · `BelowDamageThreshold` · `ResistantToMagical` · `ImmuneToMagical` · `VulnerableToMagical` · `ResistantToNonMagical` · `ImmuneToNonMagical` · `VulnerableToNonMagical`

### ResourceReplenishType
`Never` · `Default` · `Combat` · `Rest` · `ShortRest` · `FullRest` · `ExhaustedRest`

### Result
`Success` · `Failure`

### ResurrectType
`Living` · `Guaranteed` · `Construct` · `Undead`

### RollAdjustmentType
`All` · `Distribute`

### SetStatusDurationType
`SetMinimum` · `ForceSet` · `Add` · `Multiply`

### SkillType
`Deception` · `Intimidation` · `Performance` · `Persuasion` · `Acrobatics` · `SleightOfHand` · `Stealth` · `Arcana` · `History` · `Investigation` · `Nature` · `Religion` · `Athletics` · `AnimalHandling` · `Insight` · `Medicine` · `Perception` · `Survival`

### SpellCooldownType
`Default` · `OncePerTurn` · `OncePerCombat` · `UntilRest` · `OncePerTurnNoRealtime` · `UntilShortRest` · `UntilPerRestPerItem` · `OncePerShortRestPerItem`

### StatItemSlot
`Helmet` · `Breast` · `Cloak` · `MeleeMainHand` · `MeleeOffHand` · `RangedMainHand` · `RangedOffHand` · `Ring` · `Underwear` · `Boots` · `Gloves` · `Amulet` · `Ring2` · `Wings` · `Horns` · `Overhead` · `MusicalInstrument` · `VanityBody` · `VanityBoots` · `MainHand` · `OffHand`

### StatsRollType
`Attack` · `MeleeWeaponAttack` · `RangedWeaponAttack` · `MeleeSpellAttack` · `RangedSpellAttack` · `MeleeUnarmedAttack` · `RangedUnarmedAttack` · `SkillCheck` · `SavingThrow` · `RawAbility` · `Damage` · `MeleeOffHandWeaponAttack` · `RangedOffHandWeaponAttack` · `DeathSavingThrow` · `MeleeWeaponDamage` · `RangedWeaponDamage` · `MeleeSpellDamage` · `RangedSpellDamage` · `MeleeUnarmedDamage` · `RangedUnarmedDamage`

### SummonDuration
`UntilLongRest` · `Permanent`

### SurfaceLayer
`Ground` · `Cloud`

### UnlockSpellType
`Singular` · `AddChildren` · `MostPowerful`

### ZoneShape
`Cone` · `Square`

---

## 5. Spell Variant Modifiers

Modifiers used inside `UnlockSpellVariant(...)` to alter spell behavior. Each modifier takes a `ModifierType` (see §5.2) and a value unless otherwise noted.

### 5.1 Modifier Reference

#### ModifyAreaRadius
- **Arguments:** `(modifierType, value)`
- Modifies the spell's area-of-effect radius.

#### ModifyMaximumTargets
- **Arguments:** `(modifierType, value)`
- Modifies the maximum number of targets the spell can hit.

#### ModifyNumberOfTargets
- **Arguments:** `(modifierType, value, bool)`
- Modifies the number of targets.
- `bool` — whether targets must be different ("have to target different targets").

#### ModifySavingThrowDisadvantage
- **Arguments:** none
- Imposes disadvantage on the saving throw against the spell.

#### ModifySpellFlags
- **Arguments:** `(flag, 0or1)`
- Enables or disables a spell flag.
- `flag` — only supports: `Somatic`, `Verbal`, `Melee`, `Invisible`, `Stealth`
- `0` = disable, `1` = enable

#### ModifySpellRoll
- **Arguments:** `(search, replace)`
- Performs a string substitution on the spell's roll expression.
- `search` — string to look for in the roll
- `replace` — string to replace it with

#### ModifyStatusDuration
- **Arguments:** `(modifierType, float)`
- Modifies the duration of statuses applied by the spell.
- **Observation:** Multiple instances with `Multiplicative` do **not** appear to accumulate (needs verification).

#### ModifySummonDuration
- **Arguments:** `(modifierType, float)`
- Modifies how long summons from the spell persist.

#### ModifySurfaceDuration
- **Arguments:** `(modifierType, float)`
- Modifies how long surfaces created by the spell persist.

#### ModifyTargetRadius
- **Arguments:** `(modifierType, float)`
- Modifies the spell's target/cast range.
- **Observation:** Multiple instances with `Multiplicative` **do** accumulate (verified in status context with `MultiplyEffectsByDuration` — `0.5` rounds down).

#### ModifyUseCosts
- **Arguments:** `(Replace|Add, resource, amount, level, [replace])`
- Modifies the resource cost of the spell.
- `Replace` or `Add` — which version of the modifier to use
- `resource` — the replacement or added resource
- `amount` — cost amount
- `level` — resource level to modify; for `Replace`, `-1` removes the cost entirely
- `[replace]` — *(Replace version only)* the original resource being replaced
- **Observation:** Multiple instances of `Add` **accumulate**.

#### ModifyVisuals
- **Arguments:** `(icon)`
- Overrides the spell's icon.
- `icon` — new spell icon name

#### ModifyIconGlow
- **Arguments:** none
- Modifies the icon glow effect on the spell.

#### ModifyTooltipDescription
- **Arguments:** none
- Overrides the spell's tooltip. Uses the source entry's `Description` and `DescriptionParam` fields.

### 5.2 ModifierTypes

Used as the first argument to most modifiers above.

| ModifierType | Behavior | Examples |
|--------------|----------|----------|
| `AdditiveBase` | Adds value to the base total | `AdditiveBase,1` — adds 1 to base; `AdditiveBase,1,true` — adds 1 target (optional use); `AdditiveBase,1,false` |
| `AdditiveFinal` | Adds value after all other calculations | `AdditiveFinal,1` — adds 1 to final total; `AdditiveFinal,1,false` |
| `Override` | Replaces the value entirely | Overrides the original value |
| `Multiplicative` | Multiplies the value | Multiplies the current total |

### 5.3 Accumulation Behavior

> **Important:** Not all modifiers accumulate the same way when multiple instances apply.

| Modifier | ModifierType | Accumulates? | Notes |
|----------|-------------|-------------|-------|
| `ModifyUseCosts` (Add) | — | **Yes** | Multiple Add instances stack |
| `ModifyStatusDuration` | Multiplicative | **Probably not** | Needs further verification |
| `ModifyTargetRadius` | Multiplicative | **Yes** | Verified; used in status with `MultiplyEffectsByDuration` (0.5 rounds down) |

---

## 6. Common Gotchas

- **Conditional scope**: `IF(Condition):Boost1(args);Boost2(args)` — the `IF()` only applies to `Boost1`. Repeat for each: `IF(Condition):Boost1(args);IF(Condition):Boost2(args)`.
- **DealDamage CoinMultiplier**: Arg 5 does NOT accept empty — use `0` to skip: `DealDamage(1d6,Fire,,0)`. An empty arg causes silent failure.
- **IgnoreOnDamage prevents loops**: When using `DealDamage` in `OnDamage`/`OnDamaged` contexts, set arg 8 to `true` to prevent infinite re-triggering: `DealDamage(1d6,Fire,,0,,true)`.
- **IgnoreDamageBonus**: Arg 7 of `DealDamage` — when `true`, prevents proficiency/ability bonuses from being added to the damage.
- **Positional arguments**: All functor/boost arguments are positional. Skip optional args with empty commas: `ApplyStatus(BURNING,100,2,,,,not SavingThrow(...))`.
- **Semicolon = chain separator**: Multiple boosts/functors in a single field value are semicolon-separated: `"Boost1(args);Boost2(args)"`. Commas separate arguments within a single call.
- **UnlockSpellVariant first arg**: The first argument to `UnlockSpellVariant` is a Khonsu condition, NOT a spell ID. The condition selects which spells the variant modifiers apply to.
- **ApplyStatus Chance**: Arg 2 is 0–100 (percent), not 0.0–1.0. `ApplyStatus(BURNING,100,2)` = 100% chance for 2 turns.
- **Ext.Stats.Sync required**: All SE runtime stat changes require `Ext.Stats.Sync(entryName)` to take effect. Without it, modifications are invisible to the game.
