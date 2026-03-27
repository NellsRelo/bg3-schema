# SpellData

> **Type identifier**: `SpellData`
> **Source files**: `Stats/Generated/Data/Spell_*.txt`
> **Modifier definition**: [Modifiers.md](../formats/Modifiers.md#spelldata) (185 fields)

---

## Overview

The largest stat type by field count (185 fields) and file count (9 subtypes). Defines all spells in the game. The `SpellType` field discriminates between subtypes, but all share the same field pool — most subtype-specific fields are simply unused by other subtypes.

## Subtypes (File Mapping)

| SpellType | File | Description |
|-----------|------|-------------|
| `Projectile` | Spell_Projectile.txt | Projectile-based spells (Magic Missile, Fire Bolt) |
| `ProjectileStrike` | Spell_ProjectileStrike.txt | Multi-projectile strike spells (Call Lightning, Meteor Swarm) |
| `Rush` | Spell_Rush.txt | Charge/dash spells (Shield Bash, Rushing Attack) |
| `Shout` | Spell_Shout.txt | Self/AoE emanation spells (Rage, Bless, Shield of Faith) |
| `Target` | Spell_Target.txt | Single/multi-target spells (Cure Wounds, Hold Person) |
| `Teleportation` | Spell_Teleportation.txt | Teleportation (Misty Step, Dimension Door) |
| `Throw` | Spell_Throw.txt | Throw spells (alchemical, improvised weapon) |
| `Wall` | Spell_Wall.txt | Wall spells (Wall of Fire, Wall of Thorns) |
| `Zone` | Spell_Zone.txt | Zone/area spells (Thunderwave, Color Spray) |

## Entry Format

```
new entry "Target_HoldPerson"
type "SpellData"
data "SpellType" "Target"
using "Target_HoldPerson_2"
data "Level" "2"
data "SpellSchool" "Enchantment"
data "TargetConditions" "not Self() and not Dead() and Character()"
data "SpellRoll" "not SavingThrow(Ability.Wisdom, SourceSpellDC())"
data "SpellSuccess" "ApplyStatus(HOLD_PERSON,100,10)"
data "TargetRadius" "1800"
data "Icon" "Spell_Enchantment_HoldPerson"
data "DisplayName" "h...;1"
data "Description" "h...;5"
data "UseCosts" "ActionPoint:1;SpellSlotsGroup:1:1:2"
data "SpellFlags" "HasVerbalComponent;HasSomaticComponent;IsConcentration;IsSpell;IsHarmful"
```

## Pack Distribution

| Pack | Files | Largest |
|------|-------|---------|
| SharedDev | 10 | Spell_Target.txt (729 KB) |
| Shared | 9 | Spell_Target.txt (588 KB) |
| GustavDev | 9 | Spell_Target.txt (330 KB) |
| Gustav | 8 | Spell_Target.txt (49 KB) |
| Honour | 5 | Spell_Target.txt (49 KB) |
| GustavX | 8 | Spell_Target.txt (66 KB) |
| HonourX | 3 | Spell_Target.txt (1 KB) |

---

## Form Reference — All Fields

> Complete field table for form/editor construction. 185 fields defined in [Modifiers.md](../formats/Modifiers.md#spelldata). ✓ = observed in vanilla data.

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

### Boost Fields & Observed Boosts

None — SpellData does not have boost-accepting fields.

### Functor Fields & Observed Functors

| Functor Field | Purpose |
|---------------|--------|
| `SpellProperties` | Main spell property functors |
| `SpellSuccess` | Functors on successful hit/save |
| `SpellFail` | Functors on miss/failed save |
| `OriginSpellProperties` | Origin-specific property functors |
| `ThrowableSpellSuccess` | Throwable success functors |

**Functors used in vanilla (26):** `ApplyEquipmentStatus` · `ApplyStatus` · `BreakConcentration` · `CreateExplosion` · `CreateSurface` · `DealDamage` · `ExecuteWeaponFunctors` · `Force` · `RegainHitPoints` · `RemoveStatus` · `RestoreResource` · `Resurrect` · `SetStatusDuration` · `ShortRest` · `Spawn` · `SpawnExtraProjectiles` · `Stabilize` · `Summon` · `SummonInInventory` · `SurfaceChange` · `SurfaceClearLayer` · `SwitchDeathType` · `TeleportSource` · `Unlock` · `Unsummon` · `UseActionResource`

---

## Complete Field Reference

### Core Identity

#### `SpellType`
- **Type**: FixedString
- **Values**: `"Projectile"`, `"ProjectileStrike"`, `"Rush"`, `"Shout"`, `"Target"`, `"Teleportation"`, `"Throw"`, `"Wall"`, `"Zone"`
- **Notes**: Discriminates spell subtype. Determines which `Spell_*.txt` file the entry belongs to. All subtypes share the same 185-field pool.

#### `Level`
- **Type**: ConstantInt
- **Values**: `"0"` (cantrip), `"1"`, `"2"`, `"3"`, `"4"`, `"5"`, `"6"`
- **Notes**: Spell level. `"0"` for cantrips and non-spell abilities. Determines base spell slot requirement.

#### `SpellSchool`
- **Type**: SpellSchool (enum from [ValueLists](../formats/ValueLists.md))
- **Values**: `"Abjuration"`, `"Conjuration"`, `"Divination"`, `"Enchantment"`, `"Evocation"`, `"Illusion"`, `"Necromancy"`, `"Transmutation"`, `"None"`
- **Notes**: Magic school. `"None"` for non-spell abilities.

#### `Cooldown`
- **Type**: CooldownType (enum from [ValueLists](../formats/ValueLists.md))
- **Values**: `"OncePerTurn"`, `"OncePerCombat"`, `"OncePerShortRest"`, `"OncePerTurnNoRealtime"`, `"OncePerRest"`, `""` (none)
- **Notes**: Cooldown restriction. Most spells have no cooldown (limited by spell slots instead).

#### `PowerLevel`
- **Type**: ConstantInt
- **Values**: `"0"`, `"1"`, `"2"`, `"3"`, `"4"`, `"5"`, `"6"`
- **Notes**: Power level for scaling. Used in upcast variants — higher PowerLevel = stronger version.

#### `RootSpellID`
- **Type**: FixedString
- **Values**: `"Target_HoldPerson"`, `"Projectile_EldritchBlast"`, `"Shout_Rage"`
- **Notes**: Links upcast/variant spells back to the base spell. All variants of a spell share the same RootSpellID.

#### `SpellContainerID`
- **Type**: FixedString
- **Values**: `"Target_HoldPerson"`, `"Shout_Rage_Berserker"`
- **Notes**: Groups related spell variants into a single spell slot in the UI.

#### `ContainerSpells`
- **Type**: FixedString
- **Values**: `"Target_HoldPerson_2;Target_HoldPerson_3"`, `"Target_CureWounds_2;Target_CureWounds_3;Target_CureWounds_4;Target_CureWounds_5;Target_CureWounds_6"`
- **Notes**: Semicolon-separated list of spell entry names contained in this container. Defines the upcast/variant picker.

#### `ConcentrationSpellID`
- **Type**: FixedString
- **Values**: `"Target_HoldPerson"`, `"Shout_Bless"`
- **Notes**: Links to the concentration-maintaining spell. Used by spells that share concentration tracking.

#### `FollowUpOriginalSpell`
- **Type**: FixedString
- **Values**: `"Target_FlameStrike"`, `"Teleportation_MistyStep"`
- **Notes**: Links a follow-up spell back to the original that triggered it.

#### `InterruptPrototype`
- **Type**: FixedString
- **Values**: `"Counterspell"`, `"CuttingWords"`
- **Notes**: Links spell to an interrupt (reaction) definition in InterruptData.

### Display & UI

#### `DisplayName`
- **Type**: TranslatedString
- **Values**: `"hd543b3c4g1c66g4f92g897eg4ac26f04b3f0;1"` (handle format)
- **Notes**: Localized display name. Handle format: `h<UUID>;<version>`.

#### `DisplayNameRef`
- **Type**: TranslatedString
- **Notes**: Display name reference (alternate). Not commonly used.

#### `Description`
- **Type**: TranslatedString
- **Values**: `"hb0e18e26gc0f7g495dg82c9g55a1c7a0b4e6;5"`
- **Notes**: Full spell description. Version number tracks translation iterations.

#### `DescriptionRef`
- **Type**: TranslatedString
- **Notes**: Description reference (alternate).

#### `DescriptionParams`
- **Type**: FixedString
- **Values**: `"DealDamage(1d8,Fire)"`, `"DealDamage(2d6,Radiant);Distance(9)"`, `"RegainHitPoints(1d8+SpellcastingAbilityModifier)"`
- **Notes**: Semicolon-separated functor expressions that provide numeric values for description placeholders (`[1]`, `[2]`, etc.).

#### `ShortDescription`
- **Type**: TranslatedString
- **Notes**: Short description for compact UI contexts.

#### `ShortDescriptionRef`
- **Type**: TranslatedString
- **Notes**: Short description reference.

#### `ShortDescriptionParams`
- **Type**: FixedString
- **Notes**: Parameters for short description placeholders.

#### `ExtraDescription`
- **Type**: TranslatedString
- **Values**: Handle format
- **Notes**: Additional description shown in expanded tooltip. Used for upcast effects, conditional effects.

#### `ExtraDescriptionRef`
- **Type**: TranslatedString
- **Notes**: Extra description reference.

#### `ExtraDescriptionParams`
- **Type**: FixedString
- **Values**: `"DealDamage(1d8,Fire)"`, `"ApplyStatus(BURNING,100,1)"`
- **Notes**: Parameters for extra description placeholders.

#### `Icon`
- **Type**: FixedString
- **Values**: `"Spell_Enchantment_HoldPerson"`, `"Spell_Evocation_FireBolt"`, `"Action_Dash"`, `"GenericIcon_DamageType_Bludgeoning"`
- **Notes**: Icon asset name. Naming convention: `Spell_{School}_{Name}` for spells, `Action_{Name}` for abilities.

#### `PreviewCursor`
- **Type**: CursorMode (enum)
- **Values**: `"Cast"`, `"Melee"`, `"Ranged"`
- **Notes**: Cursor icon shown during spell targeting.

#### `SpellCategory`
- **Type**: SpellCategoryFlags (flags enum)
- **Values**: `"SC_None"`, `"SC_TargetSingle"`, `"SC_TargetMultiselect"`, `"SC_TargetAoE"`, `"SC_IntentDamage"`, `"SC_IntentHealing"`, `"SC_IntentBuff"`, `"SC_IntentDebuff"`, `"SC_IntentUtility"`, `"SC_Jump"`, `"SC_Dash"`, `"SC_DetectThoughts"`
- **Notes**: Categorization for UI grouping and AI decision-making.

### Targeting

#### `Range`
- **Type**: ConstantInt
- **Values**: `"0"` (self), `"150"` (touch), `"1800"` (standard), `"3600"` (long range), `"9000"` (crossbow)
- **Notes**: Cast range in centimeters. `0` = self only, `150` = touch, `1800` = 18m (standard 60ft equivalent).

#### `TargetRadius`
- **Type**: FixedString
- **Values**: `"150"`, `"1800"`, `"RangedMainWeaponRange"`, `"MeleeMainWeaponRange"`, `"TargetRadiusCrouch"`
- **Notes**: Target selection radius. Can be numeric (centimeters) or a dynamic reference to weapon range.

#### `AreaRadius`
- **Type**: ConstantInt
- **Values**: `"3"`, `"6"`, `"9"`, `"12"`, `"18"`, `"20"`
- **Notes**: Radius of area effect in meters. Used for AoE spells after the target point is chosen.

#### `ExplodeRadius`
- **Type**: ConstantInt
- **Values**: `"2"`, `"3"`, `"5"`, `"16"`
- **Notes**: Explosion radius on impact (ProjectileStrike). Per-strike explosion area.

#### `EndPosRadius`
- **Type**: ConstantInt
- **Values**: `"1"`, `"2"`
- **Notes**: Radius at the end position of a rush/charge.

#### `AmountOfTargets`
- **Type**: FixedString
- **Values**: `"1"`, `"2"`, `"3"`, `"4"`, `"MaximumTargets(3)"`, `""` (unlimited)
- **Notes**: Number of targets. Can be a literal or function reference.

#### `MaximumTargets`
- **Type**: ConstantInt
- **Values**: `"1"`, `"2"`, `"3"`, `"6"`
- **Notes**: Hard cap on target count. Used for Zone/AoE spells.

#### `MaximumTotalTargetHP`
- **Type**: ConstantInt
- **Values**: `"33"`, `"44"`, `"55"`
- **Notes**: HP-based target limit. Used by Color Spray (affects creatures up to X total HP). Higher values at higher spell levels.

#### `Shape`
- **Type**: FixedString
- **Values**: `"Cone"`, `"Square"`
- **Notes**: AoE geometry for Zone spells. Determines how the area is visualized and which targets are hit.

#### `Angle`
- **Type**: ConstantInt
- **Values**: `"60"`, `"120"`
- **Notes**: Cone angle in degrees. Only relevant when `Shape` = `"Cone"`.

#### `Base`
- **Type**: ConstantInt
- **Values**: `"3"`, `"5"`
- **Notes**: Square width in meters. Only relevant when `Shape` = `"Square"`.

#### `Height`
- **Type**: ConstantInt
- **Values**: `"0"`, `"5"`
- **Notes**: Vertical extent of wall/zone. `"0"` for ground-level effects.

#### `FrontOffset`
- **Type**: ConstantInt
- **Values**: `"-2"`, `"0"`, `"1"`
- **Notes**: Offset from caster position in meters. Negative values start behind caster.

#### `TargetCeiling`
- **Type**: FixedString
- **Values**: `"20"`, `"100"`
- **Notes**: Maximum height for target selection.

#### `TargetFloor`
- **Type**: FixedString
- **Values**: `"-1"`, `"0"`
- **Notes**: Minimum height for target selection. `"-1"` allows targeting below caster.

### Conditions

#### `TargetConditions`
- **Type**: TargetConditions
- **Values**: `"not Self() and not Dead() and Character()"`, `"not Self() and not Dead() and Ally()"`, `"Enemy() and not Dead()"`, `"Tagged('YOURFEARS_TARGET') and not Dead()"`
- **Notes**: Boolean expressions filtering valid targets. Functions include `Self()`, `Dead()`, `Character()`, `Ally()`, `Enemy()`, `Tagged()`, `HasStatus()`, `HasPassive()`, `HasWeaponInMainHand()`. Combined with `and`/`or`/`not`.

#### `AoEConditions`
- **Type**: TargetConditions
- **Values**: `"not Self() and Character()"`, `"not Dead() and not Ally(context.Source)"`, `"HasStatus('YOURFEARS_TARGET')"`
- **Notes**: Conditions applied to targets within the AoE after the area is placed.

#### `CycleConditions`
- **Type**: TargetConditions
- **Values**: `"Enemy() and not Dead()"`, `"Character() and not Dead()"`
- **Notes**: Conditions for tab-cycling through targets in the UI.

#### `HighlightConditions`
- **Type**: TargetConditions
- **Values**: `"not Self() and not Dead()"`, `"Character() and not Dead()"`
- **Notes**: Conditions determining which entities get highlighted during targeting.

#### `ForkingConditions`
- **Type**: TargetConditions
- **Values**: `"not Self() and Enemy()"`, `"Character() and not Dead()"`
- **Notes**: Conditions for projectile forking (chain lightning style).

#### `ExtraProjectileTargetConditions`
- **Type**: TargetConditions
- **Values**: Complex condition strings
- **Notes**: Conditions for extra projectile targets beyond the primary.

#### `RequirementConditions`
- **Type**: TargetConditions
- **Values**: `"not HasStatus('YOURFEARS_TARGET')"`, `"HasWeaponInMainHand()"`
- **Notes**: Conditions that must be true for the caster to use the spell.

#### `OriginTargetConditions`
- **Type**: TargetConditions
- **Values**: Complex condition strings
- **Notes**: Target conditions applied at the origin point (Teleportation spells — who is affected where the caster teleported from).

### Costs & Requirements

#### `UseCosts`
- **Type**: FixedString
- **Values**: `"ActionPoint:1"`, `"BonusActionPoint:1"`, `"ActionPoint:1;SpellSlotsGroup:1:1:2"`, `"ActionPoint:1;SpellSlot:1:1:3"`, `"KiPoint:2"`, `"Movement:6"`, `"ChannelDivinity:1;BonusActionPoint:1"`, `"SuperiorityDie:1"`, `"BardicInspiration:1;ReactionActionPoint:1"`, `"WildShape:1;BonusActionPoint:1"`, `"SorceryPoint:2"`, `"RageCharge:1;BonusActionPoint:1"`
- **Notes**: Semicolon-separated `Resource:Amount` pairs. Special format: `SpellSlotsGroup:minimum:count:level` — e.g., `SpellSlotsGroup:1:1:2` = 1 slot of level 2+. `SpellSlot:1:1:3` = 1 slot of exactly level 3.

#### `HitCosts`
- **Type**: FixedString
- **Values**: `"SorceryPoint:1"`, `"SuperiorityDie:1"`, `""` (empty)
- **Notes**: Costs consumed on each hit. Used for abilities that spend resources per target hit.

#### `DualWieldingUseCosts`
- **Type**: FixedString
- **Values**: `"BonusActionPoint:1"`, `""` (empty)
- **Notes**: Alternate costs when dual wielding.

#### `RitualCosts`
- **Type**: FixedString
- **Values**: `"ActionPoint:1"`
- **Notes**: Costs when casting as a ritual (no spell slot consumed).

#### `Requirements`
- **Type**: Requirements
- **Values**: `"!Immobile"`, `"!Combat"`, `"Combat"`, `"!Tagged(YOURFEARS_TARGET)"`
- **Notes**: General prerequisites. `!` prefix = must NOT have. Common: `!Immobile` for movement spells, `Combat` for combat-only actions.

#### `Requirement`
- **Type**: SpellRequirement (enum)
- **Values**: `"None"`, `"MeleeWeapon"`, `"RangedWeapon"`, `"StaffWeapon"`, `"DaggerWeapon"`, `"ShieldWeapon"`, `"RifleWeapon"`, `"ArrowWeapon"`
- **Notes**: Weapon type required to cast. `"MeleeWeapon"` for melee attack spells, `"RangedWeapon"` for ranged. Distinct from `Requirements` — this is specifically weapon type.

#### `MemorizationRequirements`
- **Type**: MemorizationRequirements
- **Notes**: Requirements for memorizing/preparing the spell. Not observed in vanilla data.

#### `RequirementEvents`
- **Type**: StatusEvent
- **Values**: event names
- **Notes**: Events that trigger requirement re-evaluation.

### Rolls & Effects

#### `SpellRoll`
- **Type**: RollConditions
- **Values**: `"Attack(AttackType.MeleeSpellAttack)"`, `"Attack(AttackType.RangedSpellAttack)"`, `"Attack(AttackType.MeleeWeaponAttack)"`, `"Attack(AttackType.RangedWeaponAttack)"`, `"not SavingThrow(Ability.Wisdom, SourceSpellDC())"`, `"not SavingThrow(Ability.Constitution, SourceSpellDC(), AdvantageOnPoisoned())"`, `"not SavingThrow(Ability.Dexterity, 13)"`, `"SkillCheck(Skill.Perception, 10)"`
- **Notes**: Primary roll expression. Attack rolls use `Attack(AttackType.X)`. Saving throws use `not SavingThrow(Ability.X, DC, [advantageFn], [disadvantageFn])`. Skill checks use `SkillCheck(Skill.X, DC)`. Can chain: `"Attack(...)"|"not SavingThrow(...)"` using `|` for branched rolls.

#### `SpellSuccess`
- **Type**: StatsFunctors
- **Values**: `"DealDamage(1d8,Fire)"`, `"ApplyStatus(HOLD_PERSON,100,10)"`, `"RegainHitPoints(1d8+SpellcastingAbilityModifier)"`, `"DealDamage(2d6,Radiant);ApplyStatus(BURNING,100,2)"`, `"IF(not Player(context.Source)):ApplyStatus(SELF,AI_HELPER,100,1)"`, `"GROUND:CreateSurface(3,3,Fire)"`, `"Force(6)"`, `"Resurrect(100,1)"`
- **Notes**: Semicolon-separated functor chain executed on success. Supports target prefixes (`GROUND:`, `TARGET:`, `SELF:`, `AOE:`), conditional branching (`IF(condition):functor`), and offhand wrappers (`CastOffhand[functor]`).

#### `SpellFail`
- **Type**: StatsFunctors
- **Values**: `"DealDamage(1d8/2,Fire)"`, `"ApplyStatus(PRONE,100,1)"`, `""` (empty)
- **Notes**: Functors executed on failure (save succeeded, attack missed). Often half damage — note division syntax: `1d8/2`.

#### `SpellProperties`
- **Type**: StatsFunctors
- **Values**: `"GROUND:CreateSurface(3,3,Fire)"`, `"ApplyStatus(SELF,CONCENTRATING,100,-1)"`, `"TARGET:DealDamage(1d6,Fire)"`, `"Summon(UUID, Duration, StatusOnSummon)"`, `"GROUND:SummonInInventory(UUID,Amount,EquipSlot,Equip)"`, `"ExecuteWeaponFunctors(MainHand)"`, `"Stabilize()"`, `"CreateExplosion(UUID)"`
- **Notes**: Always-execute functors (regardless of roll outcome). Common for surface creation, self-buffs, summons. Same syntax as SpellSuccess.

#### `Damage`
- **Type**: FixedString
- **Values**: `"1d8"`, `"2d6"`, `"3d8+3"`, `"MainMeleeWeapon"`, `"MainRangedWeapon"`, `"max(1,MainMeleeWeapon)"`, `"LevelMapValue(WildShapeHP_Brown_Bear)"`, `"ThrownWeapon"`
- **Notes**: Damage roll expression. Can be dice (`XdY+Z`), weapon references (`MainMeleeWeapon`), functions (`max()`, `LevelMapValue()`), or special tokens (`ThrownWeapon`).

#### `Damage Range`
- **Type**: ConstantInt
- **Values**: `"5"`, `"10"`, `"100"`
- **Notes**: Range modifier for damage falloff.

#### `DamageType`
- **Type**: Damage Type (enum from [ValueLists](../formats/ValueLists.md))
- **Values**: `"Fire"`, `"Cold"`, `"Lightning"`, `"Thunder"`, `"Acid"`, `"Poison"`, `"Necrotic"`, `"Radiant"`, `"Psychic"`, `"Force"`, `"Bludgeoning"`, `"Piercing"`, `"Slashing"`, `"None"`
- **Notes**: Primary damage type. `"None"` for non-damaging spells.

#### `DeathType`
- **Type**: Death Type (enum from [ValueLists](../formats/ValueLists.md))
- **Values**: `"None"`, `"Physical"`, `"Acid"`, `"Incinerate"`, `"Explode"`, `"Electrocution"`, `"FrozenShatter"`, `"DoT"`, `"Lifetime"`, `"Disintegrate"`
- **Notes**: Kill animation type. `"Incinerate"` for fire kills, `"FrozenShatter"` for cold kills, etc.

### Throwable-Specific

#### `ThrowableSpellRoll`
- **Type**: RollConditions
- **Values**: `"ThrowableCheck()"`
- **Notes**: Secondary roll for thrown items. `ThrowableCheck()` validates throw is possible.

#### `ThrowableSpellSuccess`
- **Type**: StatsFunctors
- **Values**: `"IF(Character()):ApplyStatus(PRONE_AFTER_THROW,100,1);"`, `"DealDamage(ThrownWeapon,ThrownWeaponDamageType);ExecuteWeaponFunctors(MainHand)"`
- **Notes**: Functors on successful throw. Uses `context.HitDescription.ThrownObject` and weight functions: `IsLightThrownObject()`, `IsMediumThrownObject()`, `IsHeavyThrownObject()`.

#### `ThrowableSpellFail`
- **Type**: StatsFunctors
- **Notes**: Functors on failed throw. Not commonly used.

#### `ThrowableSpellProperties`
- **Type**: StatsFunctors
- **Notes**: Always-execute functors for throws.

#### `ThrowableTargetConditions`
- **Type**: TargetConditions
- **Values**: `"CanThrowWeight() and not Grounded() and not IsItemDisabled() and not Tagged('YOURFEARS_DONT_PICKUP')"`
- **Notes**: Complex condition chain for what can be thrown. Weight, grounding, and tag checks.

#### `ThrowOrigin`
- **Type**: ThrowOrigin (enum)
- **Notes**: Where the throw originates from.

### Origin-Specific (Teleportation)

#### `OriginSpellProperties`
- **Type**: StatsFunctors
- **Values**: `"RegainHitPoints(1);Resurrect(100,1)"`, `"GROUND:TeleportSource()"`, `"GROUND:Summon(UUID,...)"`, `"DealDamage(4d10,Force)"`
- **Notes**: Functors executed at the origin point (where the caster teleported FROM). Two patterns: resurrection effects, or area damage/surface left behind.

#### `OriginSpellRoll`
- **Type**: RollConditions
- **Values**: `"not SavingThrow(Ability.Intelligence, 13)"`
- **Notes**: Roll applied to targets at the origin location.

#### `OriginSpellSuccess`
- **Type**: StatsFunctors
- **Values**: `"DealDamage(2d8, Psychic)"`
- **Notes**: Success functors at origin.

#### `OriginSpellFail`
- **Type**: StatsFunctors
- **Values**: `"DealDamage(2d8/2, Psychic)"`
- **Notes**: Fail (half damage) functors at origin.

### Spell Flags

#### `SpellFlags`
- **Type**: SpellFlagList (flags enum from [ValueLists](../formats/ValueLists.md))
- **Values**: Semicolon-separated. Common combinations:
  - `"HasVerbalComponent;HasSomaticComponent;IsConcentration;IsSpell;IsHarmful"` (Concentration damage spell)
  - `"HasVerbalComponent;HasSomaticComponent;IsSpell"` (Buff/utility spell)
  - `"IsAttack;IsMelee;IsDefaultWeaponAction;AddWeaponRange"` (Melee weapon action)
  - `"IsJump;HasHighGroundRangeExtension"` (Jump spell)
- **Notes**: 56+ possible flags. Key flags:
  - **Components**: `HasVerbalComponent`, `HasSomaticComponent`
  - **Type**: `IsSpell`, `IsAttack`, `IsMelee`, `IsJump`, `IsTrap`
  - **Behavior**: `IsConcentration`, `ConcentrationIgnoresResting`, `ImmediateCast`, `Stealth`, `CanDualWield`, `Wildshape`, `AllowMoveAndCast`, `PickupEntityAndMove`
  - **Targeting**: `CannotTargetCharacter`, `CannotTargetItems`, `CannotTargetTerrain`, `IgnoreVisionBlock`, `RangeIgnoreSourceBounds`, `RangeIgnoreTargetBounds`, `RangeIgnoreVerticalThreshold`, `RangeIgnoreBlindness`, `TargetClosestEqualGroundSurface`
  - **UI**: `InventorySelection`, `Invisible`, `Temporary`, `UnavailableInDialogs`, `DisplayInItemTooltip`, `HideInItemTooltip`, `DisplayDamageModifiers`
  - **AI**: `CallAlliesSpell`, `IsEnemySpell`, `IsHarmful`, `NoSurprise`, `IgnoreAoO`, `IgnorePreviouslyPickedEntities`
  - **Combat**: `AddFallDamageOnLand`, `AddWeaponRange`, `CombatLogSetSingleLineRoll`, `AbortOnSpellRollFail`, `AbortOnSecondarySpellRollFail`, `CanAreaDamageEvade`, `NoCooldownOnMiss`, `NoAOEDamageOnLand`, `IsSwarmAttack`, `DisableBlood`, `DontAbortPerforming`
  - **Container**: `IsLinkedSpellContainer`, `IsDefaultWeaponAction`, `HasHighGroundRangeExtension`
  - **Special**: `ChasmRecovery`, `CannotRotate`, `NoCameraMove`

### Projectile Settings

#### `ProjectileCount`
- **Type**: FixedString
- **Values**: `"1"`, `"3"`, `"4"`, `"6"`, `"MaximumTargets(3)"`
- **Notes**: Number of projectiles. Can be a function reference. Magic Missile uses `"3"` at base level.

#### `ProjectileDelay`
- **Type**: ConstantInt
- **Values**: `"0"`, `"1"`, `"50"`
- **Notes**: Delay between projectiles in milliseconds.

#### `ProjectileType`
- **Type**: ProjectileType (enum)
- **Values**: `"Grenade"`, `"Arrow"`, `""` (default)
- **Notes**: Visual projectile type. Affects trajectory arc and visuals.

#### `Distribution`
- **Type**: ProjectileDistribution (enum)
- **Values**: `"Normal"`, `"Random"`, `"EdgeCenter"`
- **Notes**: How projectiles are distributed across the target area (ProjectileStrike).

#### `ForkChance`
- **Type**: ConstantInt
- **Values**: `"100"` (always fork)
- **Notes**: Percentage chance for a projectile to fork to additional targets (chain lightning style).

#### `ForkLevels`
- **Type**: ConstantInt
- **Values**: `"1"`, `"2"`
- **Notes**: Number of fork generations.

#### `MaxForkCount`
- **Type**: ConstantInt
- **Values**: `"3"`, `"5"`
- **Notes**: Maximum total forked projectiles.

#### `StopAtFirstContact`
- **Type**: ConstantInt
- **Values**: `"0"`, `"1"`
- **Notes**: Boolean. Whether a projectile stops on first hit (1) or pierces through (0).

#### `Trajectories`
- **Type**: FixedString
- **Values**: `"rules:UUID1,UUID2,UUID3"` (prefix + comma-separated UUIDs)
- **Notes**: Trajectory data. Multiple trajectory UUIDs define projectile arc curves.

#### `Template`
- **Type**: FixedString
- **Values**: UUID
- **Notes**: Template ID for the projectile visual.

#### `TargetProjectiles`
- **Type**: YesNo
- **Values**: `"Yes"`
- **Notes**: Whether projectiles can be targeted/destroyed.

### ProjectileStrike-Specific

#### `StrikeCount`
- **Type**: ConstantInt
- **Values**: `"3"`, `"9"`, `"14"`, `"24"`
- **Notes**: Number of barrage strikes in a ProjectileStrike spell. Key field differentiating PS from Projectile.

#### `SingleSource`
- **Type**: YesNo
- **Values**: `"Yes"`, `"No"`
- **Notes**: Whether all strikes originate from the same point.

#### `PreviewStrikeHits`
- **Type**: YesNo
- **Values**: `"Yes"`
- **Notes**: Show impact preview markers during targeting.

#### `Shuffle`
- **Type**: YesNo
- **Values**: `"Yes"`
- **Notes**: Randomize strike order.

#### `ForceTarget`
- **Type**: ConstantInt
- **Values**: `"0"`
- **Notes**: Force targeting override.

#### `CastTargetHitDelay`
- **Type**: ConstantInt
- **Values**: `"15"`, `"42"`
- **Notes**: Delay from cast to first impact.

### Rush-Specific

#### `MovementSpeed`
- **Type**: ConstantInt
- **Values**: `"12000"`, `"40000"`
- **Notes**: Rush travel speed. High values (40000) for fast charges.

#### `HitRadius`
- **Type**: ConstantFloat
- **Values**: `"1"`, `"1.5"`, `"2"`
- **Notes**: Width of the hit zone during charge movement.

#### `HitExtension`
- **Type**: ConstantFloat
- **Values**: `"1"`, `"1.5"`, `"4"`
- **Notes**: Extends the hit zone beyond `HitRadius`.

#### `OnlyHit1Target`
- **Type**: ConstantInt
- **Values**: `"0"`, `"1"`
- **Notes**: Boolean. If `"1"`, rush stops after hitting one target.

#### `MaxAttacks`
- **Type**: ConstantInt
- **Notes**: Maximum attack count during rush. Rarely set explicitly.

### Teleportation-Specific

#### `TeleportSelf`
- **Type**: YesNo
- **Values**: `"Yes"`, `"No"`
- **Notes**: Whether the caster teleports. `"Yes"` for Misty Step, `"No"` for Dimension Door (teleporting another).

#### `TeleportSurface`
- **Type**: YesNo
- **Values**: `"Yes"`, `"No"`
- **Notes**: Whether the teleportation creates/moves a surface.

#### `TeleportDelay`
- **Type**: ConstantInt
- **Notes**: Delay before teleportation executes.

#### `IgnoreTeleport`
- **Type**: YesNo
- **Values**: `"Yes"`
- **Notes**: Bypasses teleport restrictions (e.g., Arcane Gate).

#### `Acceleration`
- **Type**: ConstantInt
- **Values**: `"0"`
- **Notes**: Teleport projectile acceleration. `"0"` for instant teleports.

### Wall-Specific

#### `ItemWall`
- **Type**: FixedString
- **Values**: `"BladeBarrier"`, `"WallOfFire"`, `"WallOfIce"`, `"WallOfStone"`, `"WallOfThorns"`, `"VossWallOfFire"`
- **Notes**: Wall entity template name. Defines the physical wall object.

#### `ItemWallStatus`
- **Type**: FixedString
- **Values**: `"BLADE_BARRIER"`, `"WALLOFFIRE"`, `"WALLOFICE"`, `"WALLOFTHORN"`, `"WALLOFFIRE_5"`, `"WALLOFFIRE_6"`, `"END_DRAGONFIRE_TECHNICAL"`
- **Notes**: Status applied by the wall. Numbered variants for upcast levels.

#### `MaxDistance`
- **Type**: ConstantInt
- **Values**: `"6"`, `"9"`, `"18"`
- **Notes**: Maximum wall length in meters.

#### `Lifetime`
- **Type**: ConstantInt
- **Values**: `"10"`, `"60"`
- **Notes**: Wall duration in rounds. `"10"` = 1 minute, `"60"` = 10 minutes.

#### `WallStartEffect`
- **Type**: FixedString
- **Notes**: VFX at the start of the wall. Not observed in vanilla data.

#### `WallEndEffect`
- **Type**: FixedString
- **Notes**: VFX at the end of the wall. Not observed in vanilla data.

### Zone/Surface-Specific

#### `SurfaceType`
- **Type**: Surface Type (enum from [ValueLists](../formats/ValueLists.md))
- **Values**: `"Fire"`, `"BladeBarrier"`, `"WaterFrozen"`, `"Vines"`, `"Mud"`, `"Sentinel"`, `"None"`
- **Notes**: Surface type created. `"Sentinel"` = invisible trigger zone (for spells like Spirit Guardians).

#### `SurfaceRadius`
- **Type**: ConstantInt
- **Values**: `"1"`, `"2"`
- **Notes**: Surface width around the wall/zone.

#### `SurfaceLifetime`
- **Type**: ConstantInt
- **Values**: `"0"`, `"3"`
- **Notes**: How long the surface persists. `"0"` = instant (one-time effect), `"3"` = persists 3 rounds.

#### `SurfaceGrowStep`
- **Type**: ConstantInt
- **Values**: `"5"`, `"50"`, `"100"`
- **Notes**: Growth rate per step. Higher values = faster surface spread.

#### `SurfaceGrowInterval`
- **Type**: ConstantInt
- **Values**: `"1"`, `"10"`
- **Notes**: Tick interval for growth.

### AI Behavior

#### `AIFlags`
- **Type**: AIFlags (flags enum from [ValueLists](../formats/ValueLists.md))
- **Values**: `"CanNotUse"`, `"IgnoreSelf"`, `"IgnoreDebuff"`, `"IgnoreBuff"`, `"StatusIsSecondary"`, `"IgnoreControl"`, `"CanNotTargetFrozen"`, `"GrantsResources;UseAsSupportingActionOnly"`, `"UseAsSeekActionOnly"`
- **Notes**: Semicolon-separated AI behavior flags. `"CanNotUse"` = AI never uses this spell. `"GrantsResources;UseAsSupportingActionOnly"` = used by Dash (grants movement but isn't a primary action).

#### `AiCalculationSpellOverride`
- **Type**: FixedString
- **Values**: Spell entry name
- **Notes**: AI uses a different spell's parameters for decision making.

#### `CombatAIOverrideSpell`
- **Type**: FixedString
- **Values**: Spell entry name
- **Notes**: Override spell for combat AI evaluation.

#### `Autocast`
- **Type**: YesNo
- **Values**: `"Yes"`
- **Notes**: AI auto-casts this spell. Used for NPC-specific abilities: `Shout_CRA_DyingMindflayer_Enthrall`, `Shout_HAG_UseCharm`, `Shout_UND_MonkAmulet_TalkToAmulet`.

### Animation & Visual

#### `SpellAnimation`
- **Type**: FixedString
- **Values**: 9-phase format, each phase = `UUID,,` separated by `;`. Example: `"5dbfc67e-...,,;6f957f78-...,,;63c0501c-...,,;e6af1757-...,,;08e862c4-...,,;3ed0eebd-...,,;0b07883a-...,,;,,;,,"`
- **Notes**: 9 animation phases: (1) Prepare, (2) Prepare Loop, (3) Cast, (4) Cast Loop, (5) Hit, (6) Land, (7) End, (8-9) reserved. Each phase has `UUID,variant,slot` — empty phases shown as `,,`. Multi-animation variant uses colon separator within a phase: `"UUID1,,:UUID2,,"`.

#### `DualWieldingSpellAnimation`
- **Type**: FixedString
- **Values**: Same 9-phase format as SpellAnimation
- **Notes**: Alternate animation when dual wielding.

#### `SpellAnimationType`
- **Type**: SpellAnimationType (enum)
- **Values**: `"None"`, `"Throwing"`, `"ImprovisedWeapon"`
- **Notes**: Animation category. `"Throwing"` for throw spells.

#### `SpellAnimationIntentType`
- **Type**: SpellAnimationIntentType (enum)
- **Values**: `"None"`, `"Aggressive"`, `"Peaceful"`, `"Buff"`, `"Debuff"`, `"Utility"`
- **Notes**: Animation intent for cinematic framing.

#### `HitAnimationType`
- **Type**: HitAnimationType (enum)
- **Values**: `"Default"`, `"None"`, `"Somatic"`
- **Notes**: Animation played on the target when hit.

#### `Sheathing`
- **Type**: SpellSheathing (enum)
- **Values**: `"Somatic"`, `"DontChange"`, `"Instrument"`, `"Melee"`, `"Ranged"`
- **Notes**: Weapon sheathing behavior. `"Melee"` = draw melee weapon, `"Somatic"` = put weapons away for spell gestures, `"DontChange"` for jumps.

### VFX

#### `PrepareEffect`
- **Type**: FixedString
- **Values**: UUID
- **Notes**: VFX played during spell preparation.

#### `PrepareEffectBone`
- **Type**: FixedString
- **Values**: Bone name
- **Notes**: Bone attachment point for prepare VFX.

#### `CastEffect`
- **Type**: FixedString
- **Values**: UUID
- **Notes**: VFX on cast.

#### `CastEffectTextEvent`
- **Type**: FixedString
- **Values**: Event name
- **Notes**: Text event trigger synced to cast VFX.

#### `TargetEffect`
- **Type**: FixedString
- **Values**: UUID
- **Notes**: VFX at target location.

#### `TargetGroundEffect`
- **Type**: FixedString
- **Values**: UUID
- **Notes**: VFX on ground at target.

#### `TargetHitEffect`
- **Type**: FixedString
- **Values**: UUID
- **Notes**: VFX on target when hit.

#### `HitEffect`
- **Type**: FixedString
- **Values**: UUID
- **Notes**: VFX on hit.

#### `ImpactEffect`
- **Type**: FixedString
- **Values**: UUID
- **Notes**: VFX on projectile impact.

#### `SpellEffect`
- **Type**: FixedString
- **Values**: UUID
- **Notes**: Generic spell VFX.

#### `PositionEffect`
- **Type**: FixedString
- **Values**: UUID
- **Notes**: VFX at specific positions (rush trail, etc.).

#### `DisappearEffect`
- **Type**: FixedString
- **Values**: UUID
- **Notes**: VFX when caster vanishes (Teleportation).

#### `ReappearEffect`
- **Type**: FixedString
- **Values**: UUID
- **Notes**: VFX when caster reappears.

#### `ReappearEffectTextEvent`
- **Type**: FixedString
- **Values**: Event name
- **Notes**: Text event synced to reappear VFX.

#### `PreviewEffect`
- **Type**: FixedString
- **Values**: UUID
- **Notes**: VFX during preview/targeting.

#### `SelectedCharacterEffect`
- **Type**: FixedString
- **Values**: UUID
- **Notes**: VFX on selected character during targeting.

#### `SelectedObjectEffect`
- **Type**: FixedString
- **Values**: UUID
- **Notes**: VFX on selected object during targeting.

#### `SelectedPositionEffect`
- **Type**: FixedString
- **Values**: UUID
- **Notes**: VFX at selected position during targeting.

#### `SpawnEffect`
- **Type**: FixedString
- **Values**: UUID
- **Notes**: VFX on summon/spawn.

#### `StormEffect`
- **Type**: FixedString
- **Values**: UUID
- **Notes**: Storm atmosphere VFX (Call Lightning).

#### `FXScale`
- **Type**: ConstantInt
- **Values**: `"100"`
- **Notes**: VFX scale percentage.

#### `BeamEffect`
- **Type**: FixedString
- **Values**: `"0ceeadd7-b6a7-43f0-882b-2509ecb5c635"`, `"73f914ff-726e-4e4a-a156-f1ac02b8753c"` (UUID)
- **Notes**: Beam VFX. Used for continuous beam effects (Spectator eye rays, Witch Bolt).

#### `MaleImpactEffects`
- **Type**: FixedString
- **Notes**: Male-specific VFX on impact. Not observed in vanilla data.

#### `FemaleImpactEffects`
- **Type**: FixedString
- **Notes**: Female-specific VFX on impact. Not observed in vanilla data.

### Sound

#### `PrepareSound`
- **Type**: FixedString
- **Values**: `"Spell_Prepare_Damage_Gen_L1to3"`, `"Spell_Prepare_Healing_Gen_L1to3"`, `"Spell_Prepare_Buff_Gen_L1to3"`, `"Spell_Prepare_Control_Gen_L1to3"`
- **Notes**: Sound ID during preparation. Naming pattern: `Spell_Prepare_{Intent}_{School}_{Level}`.

#### `PrepareLoopSound`
- **Type**: FixedString
- **Values**: `"Spell_Prepare_Damage_Gen_L1to3_Loop"`, `"Spell_Prepare_Healing_Gen_L1to3_Loop"`
- **Notes**: Looping sound during extended prepare.

#### `CastSound`
- **Type**: FixedString
- **Values**: `"Spell_Cast_Damage_Fire_L1to3"`, `"Spell_Cast_Healing_Gen_L1to3"`, `"Spell_Cast_Utility_Gen_L1to3"`
- **Notes**: Sound ID on cast. Pattern: `Spell_Cast_{Intent}_{Type}_{Level}`.

#### `TargetSound`
- **Type**: FixedString
- **Values**: `"Spell_Impact_Damage_Fire_L1to3"`, `"Spell_Impact_Healing_Gen_L1to3"`
- **Notes**: Sound at target location.

#### `VocalComponentSound`
- **Type**: FixedString
- **Values**: `"Vocal_Component_Enchantment"`, `"Vocal_Component_Evocation"`, `"Vocal_Component_Abjuration"`
- **Notes**: Verbal component vocalization. By spell school.

#### `CastTextEvent`
- **Type**: FixedString
- **Values**: Event name
- **Notes**: Text event synced to cast sound.

#### `AlternativeCastTextEvents`
- **Type**: FixedString
- **Values**: Event name
- **Notes**: Alternative cast text events.

#### `SpellSoundMagnitude`
- **Type**: SpellSoundMagnitude (enum)
- **Values**: `"Normal"`, `"None"`, `"Small"`, `"Big"`
- **Notes**: Sound magnitude category. `"Big"` for wall spells, `"Small"` for jumps.

#### `InstrumentComponentPrepareSound`
- **Type**: FixedString
- **Values**: `"Instrument_Bard_CounterCharm_Prepare"`
- **Notes**: Instrument-specific prepare sound. Used for Bard spells with instrument components.

#### `InstrumentComponentLoopingSound`
- **Type**: FixedString
- **Values**: `"Instrument_Bard_CounterCharm_Loop"`
- **Notes**: Instrument loop sound.

#### `InstrumentComponentCastSound`
- **Type**: FixedString
- **Values**: `"Instrument_Bard_CounterCharm_Cast"`
- **Notes**: Instrument cast sound.

#### `InstrumentComponentImpactSound`
- **Type**: FixedString
- **Values**: `"Instrument_Bard_CounterCharm_Impact"`
- **Notes**: Instrument impact sound.

#### `SpellSoundAftermathTrajectory`
- **Type**: FixedString
- **Notes**: Aftermath trajectory sound for lingering effects.

### Cinematic

#### `CinematicArenaFlags`
- **Type**: CinematicArenaFlags (enum)
- **Values**: `"None"`, `"Ignore"`, `"AlwaysShow"`
- **Notes**: Camera behavior. `"Ignore"` skips cinematic camera for minor actions (Dash, Crouch, Disengage).

#### `CinematicArenaTimelineOverride`
- **Type**: Guid
- **Notes**: UUID override for cinematic timeline. Not observed in vanilla data.

### Weapon Integration

#### `UseWeaponDamage`
- **Type**: YesNo
- **Notes**: Whether to use the equipped weapon's damage. Not observed in vanilla data (use `Damage` = `"MainMeleeWeapon"` instead).

#### `UseWeaponProperties`
- **Type**: YesNo
- **Notes**: Whether to inherit weapon properties. Not observed in vanilla data.

#### `WeaponTypes`
- **Type**: WeaponFlags (flags enum)
- **Values**: `"None"`, `"Light"`, `"Ammunition"`, `"Finesse"`, `"Heavy"`, `"Loading"`, `"Range"`, `"Reach"`, `"Lance"`, `"Net"`, `"Thrown"`, `"Twohanded"`, `"Versatile"`, `"Melee"`, `"Dippable"`, `"Torch"`, `"NoDualWield"`, `"Magical"`, `"NeedDualWieldingBoost"`, `"NotSheathable"`, `"Unstowable"`, `"AddToHotbar"`
- **Notes**: Required weapon property flags. `"Melee"` for melee attacks, `"Ammunition"` for ranged.

#### `WeaponBones`
- **Type**: FixedString
- **Notes**: Weapon bone attachment points. Not observed in vanilla data.

#### `SourceLimbIndex`
- **Type**: ConstantInt
- **Values**: `"1"`
- **Notes**: Source limb for the attack. Used by Spectator eye stalk rays (limb index selects which eye stalk).

### Misc Mechanics

#### `VerbalIntent`
- **Type**: VerbalIntent (enum)
- **Values**: `"None"`, `"Damage"`, `"Healing"`, `"Buff"`, `"Debuff"`, `"Utility"`, `"Control"`, `"Summon"`
- **Notes**: Verbal intent classification. Affects vocal component sound selection.

#### `SpellStyleGroup`
- **Type**: SpellStyleGroup (enum)
- **Values**: `"Intent"`, `"Class"`, `"Class_Intent"`
- **Notes**: Animation style selection group.

#### `LineOfSightFlags`
- **Type**: LineOfSightFlags (enum)
- **Values**: `"None"`, `"AddSourceHeight"`
- **Notes**: Line-of-sight calculation modifiers.

#### `SpellJumpType`
- **Type**: SpellJumpType (enum)
- **Values**: `"None"`, `"Jump"`, `"Pounce"`, `"Flight"`
- **Notes**: Jump behavior classification.

#### `SpellActionType`
- **Type**: SpellActionType (enum)
- **Values**: `"Throw"`, `"ImprovisedWeapon"`
- **Notes**: Action type classification (Throw subtype).

#### `SpellActionTypePriority`
- **Type**: ConstantInt
- **Notes**: Priority ordering for action type.

#### `Stealth`
- **Type**: YesNo
- **Notes**: Whether spell can be used from stealth. Not observed as standalone field — use `SpellFlags` `"Stealth"` flag instead.

#### `OverrideSpellLevel`
- **Type**: YesNo
- **Notes**: Override the spell's level calculation. Not observed in vanilla data.

#### `RechargeValues`
- **Type**: FixedString
- **Values**: `"3-6"`, `"4-6"`, `"5-6"`
- **Notes**: Recharge range in format `Min-Max`. At start of turn, roll d6 — recharges on Min or higher. Used for NPC abilities (Spectator rays, enemy spells).

#### `MinJumpDistance`
- **Type**: ConstantFloat
- **Values**: `"2"`
- **Notes**: Minimum jump distance in meters. Only used in jump spells.

#### `Spellbook`
- **Type**: FixedString
- **Notes**: Spellbook assignment. Not observed in vanilla data.

#### `SteerSpeedMultipler`
- **Type**: ConstantFloat
- **Notes**: Steer speed multiplier for guided projectiles. Note: the typo (`Multipler` not `Multiplier`) is in the game data.

### Costs (Alternate Fields)

#### `Memory Cost`
- **Type**: ConstantInt
- **Notes**: Memory cost (space in field name). Not observed in vanilla — use `MemoryCost` instead.

#### `MemoryCost`
- **Type**: ConstantInt
- **Values**: `"1"`, `"2"`
- **Notes**: Memory cost for prepared spell slots.

#### `Magic Cost`
- **Type**: ConstantInt
- **Notes**: Magic cost. Not observed in vanilla data.

### Delay Mechanics

#### `DelayRollDie`
- **Type**: DieType (enum)
- **Notes**: Die type for delay rolls. Not observed in vanilla data.

#### `DelayRollTarget`
- **Type**: ConstantInt
- **Notes**: Target number for delay rolls. Not observed in vanilla data.

#### `DelayTurnsCount`
- **Type**: ConstantInt
- **Notes**: Number of turns to delay. Not observed in vanilla data.

### Hit Limits

#### `MinHitsPerTurn`
- **Type**: ConstantInt
- **Notes**: Minimum hits per turn. Not observed in vanilla data.

#### `MaxHitsPerTurn`
- **Type**: ConstantInt
- **Notes**: Maximum hits per turn. Not observed in vanilla data.

#### `NextAttackChance`
- **Type**: ConstantInt
- **Notes**: Percentage chance for next attack in a chain. Not observed in vanilla data.

#### `NextAttackChanceDivider`
- **Type**: ConstantInt
- **Notes**: Divider for next attack chance calculation. Not observed in vanilla data.

### Tooltips

#### `TooltipDamageList`
- **Type**: FixedString
- **Values**: `"DealDamage(1d8,Fire)"`, `"DealDamage(2d6,Radiant);DealDamage(1d6,Fire)"`
- **Notes**: Tooltip damage display. Uses functor syntax — semicolon-separated for multiple damage types.

#### `TooltipAttackSave`
- **Type**: FixedString
- **Values**: `"MeleeSpellAttack"`, `"RangedSpellAttack"`, `"WisdomSavingThrow"`, `"ConstitutionSavingThrow"`, `"DexteritySavingThrow"`
- **Notes**: Tooltip text for attack/save type.

#### `TooltipStatusApply`
- **Type**: FixedString
- **Values**: `"ApplyStatus(BURNING,100,2)"`, `"ApplyStatus(HOLD_PERSON,100,10);ApplyStatus(PARALYZED,100,10)"`
- **Notes**: Tooltip status application info.

#### `TooltipOnSave`
- **Type**: FixedString
- **Values**: `"DealDamage(1d8/2,Fire)"`
- **Notes**: Tooltip text for "on save" effect (typically half damage).

#### `TooltipOnMiss`
- **Type**: FixedString
- **Values**: `"DealDamage(1d8/2,Fire)"`
- **Notes**: Tooltip text for miss effect.

#### `TooltipPermanentWarnings`
- **Type**: FixedString
- **Values**: Warning text strings
- **Notes**: Permanent tooltip warnings (e.g., "This action is irreversible").

#### `TooltipSpellDCAbilities`
- **Type**: AbilityFlags (flags enum)
- **Values**: `"Wisdom"`, `"Intelligence"`, `"Charisma"`, `"Constitution"`, `"Dexterity"`, `"Strength"`
- **Notes**: Which ability modifier is used for the spell DC display.

#### `TooltipUpcastDescription`
- **Type**: Guid
- **Values**: UUID
- **Notes**: UUID referencing upcast description text.

#### `TooltipUpcastDescriptionParams`
- **Type**: FixedString
- **Values**: Functor expressions
- **Notes**: Parameters for upcast description placeholders.

### Priority

#### `Priority`
- **Type**: ConstantInt
- **Notes**: Resolution priority.

---

## Value Syntax Patterns

### Functor Chain Syntax
```
"DealDamage(1d8,Fire);ApplyStatus(BURNING,100,2)"
```
Semicolon-separated function calls.

### Target Prefixes
```
"GROUND:CreateSurface(3,3,Fire)"
"TARGET:DealDamage(1d6,Fire)"
"SELF:ApplyStatus(RAGING,100,-1)"
"AOE:DealDamage(1d6,Radiant)"
```
Prefix determines where/who the functor affects.

### Conditional Functors
```
"IF(not Player(context.Source)):ApplyStatus(SELF,AI_HELPER,100,1)"
"IF(HasStatus('BURNING')):DealDamage(1d6,Fire)"
```
`IF(condition):functor` syntax for conditional execution.

### Offhand Wrappers
```
"CastOffhand[DealDamage(OffhandMeleeWeapon)]"
```
Bracket-delimited alternatives for offhand attacks.

### Saving Throw Syntax
```
"not SavingThrow(Ability.Wisdom, SourceSpellDC())"
"not SavingThrow(Ability.Constitution, SourceSpellDC(), AdvantageOnPoisoned())"
"not SavingThrow(Ability.Dexterity, 13)"
```
`not SavingThrow(Ability, DC, [advantageFn], [disadvantageFn])` — "not" because failure to save = spell succeeds.

### Attack Roll Syntax
```
"Attack(AttackType.MeleeSpellAttack)"
"Attack(AttackType.RangedWeaponAttack)"
"Attack(AttackType.MeleeWeaponAttack)"
```

### Cost Expression Syntax
```
"ActionPoint:1;SpellSlotsGroup:1:1:2"
"BonusActionPoint:1"
"KiPoint:2"
"WildShape:1;BonusActionPoint:1"
"SpellSlot:1:1:3"
```
Format: `Resource:Amount`. `SpellSlotsGroup:Min:Count:Level` = Count slots of Level or higher. `SpellSlot:Min:Count:Level` = Count slots of exactly Level.

### Condition Syntax
```
"not Self() and not Dead() and Character()"
"Enemy() and not Dead()"
"HasStatus('BURNING') or HasStatus('ENTANGLED')"
"Tagged('YOURFEARS_TARGET') and not Dead()"
"CanThrowWeight() and not Grounded() and not IsItemDisabled()"
```
Boolean DSL with `and`/`or`/`not` operators. Functions: `Self()`, `Dead()`, `Character()`, `Ally()`, `Enemy()`, `Tagged()`, `HasStatus()`, `HasPassive()`, `HasWeaponInMainHand()`, `Player()`, `IsLightThrownObject()`, etc.

### SpellAnimation Phase Format
```
"UUID,,;UUID,,;UUID,,;UUID,,;UUID,,;UUID,,;UUID,,;,,;,,"
```
9 phases separated by `;`. Each phase = `UUID,variant,slot`. Empty phases = `,,`.

---

## Cross-References

| From | To | Via |
|------|----|----|
| SpellData.RootSpellID | SpellData | Entry name link to base spell |
| SpellData.ContainerSpells | SpellData | Semicolon-separated entry names |
| SpellData.ConcentrationSpellID | SpellData | Entry name for concentration |
| SpellData.InterruptPrototype | InterruptData | Interrupt definition name |
| SpellData.SpellSuccess/Fail | StatusData | `ApplyStatus(NAME,...)` references |
| SpellData.DamageType | ValueLists | Damage Type enum |
| SpellData.SpellFlags | ValueLists | SpellFlagList flags enum |
| SpellData.SpellSchool | ValueLists | SpellSchool enum |
| SpellData.SurfaceType | ValueLists | Surface Type enum |
| SpellData.ItemWallStatus | StatusData | Wall status reference |
| SpellData (Stats attribute) | GameObjects | GameObjects.Stats references entry name |

## Caveats & Gotchas

- **SpellType is mandatory**: Every entry must have `SpellType` set. The field pool is shared but certain fields are only meaningful for specific subtypes.
- **"not SavingThrow" inversion**: `SpellRoll` uses `not SavingThrow(...)` because the roll condition represents "spell succeeds" — a failed save means the spell worked.
- **SpellSlotsGroup vs SpellSlot**: `SpellSlotsGroup:1:1:2` = any slot of level 2+. `SpellSlot:1:1:3` = only a level 3 slot.
- **`Memory Cost` vs `MemoryCost`**: Two field names exist — `Memory Cost` (with space) is unused, `MemoryCost` (no space) is the real one.
- **`SteerSpeedMultipler`**: The typo in the field name is intentional — it's in the game's Modifiers.txt.
- **SpellAnimation 9 phases**: All 9 phases must be present even if empty. Missing phases cause parse errors.
- **Spell_Wall.txt**: Does NOT exist under `Shared/Public/Shared/` — only found in SharedDev, GustavX, and Gustav.
- **Recharge format**: `"4-6"` means roll d6 at start of turn; on 4, 5, or 6 the ability recharges. D&D 5e "Recharge X–6" mechanic.
- **Flag separation**: SpellFlags, AIFlags, WeaponTypes all use semicolons. Don't confuse with comma-separated animation UUIDs.
- **Conditional functor scope**: `IF(Condition):Functor1(args);Functor2(args)` — the `IF()` only applies to `Functor1`. For multiple conditional functors, repeat: `IF(Condition):Functor1(args);IF(Condition):Functor2(args)`.
- **DealDamage CoinMultiplier null**: Arg 5 (CoinMultiplier) in `DealDamage` does NOT accept empty — use `0`: `DealDamage(1d6,Fire,,0)`. An empty arg silently fails.
- **ContainerSpells naming**: Container children must match exact entry names (case-sensitive). `ContainerSpells "Target_Bless;Target_Command"` — wrong casing or extra whitespace breaks the link silently.
- **RootSpellID**: Links child variants to a base spell. The UI groups spells by `RootSpellID`. If missing, the spell appears as standalone in the spellbook.
- **Upcast pattern**: Upcasting creates `[SpellName]_1`, `[SpellName]_2`, etc., each with `using "[SpellName]"` and `SpellType "[same as parent]"`. The parent's `SpellFlags` must include `IsSpell` (not `IsCantrip`).
- **MetaConditions overlay**: Conditions can be injected into spells without editing them via LSX `MetaConditions` entries (region `MetaConditions` in `Public/{Mod}/Content/Spell/`). `OverrideOriginalCondition=false` adds conditions; `true` replaces them entirely.
- **XML escaping in LSX conditions**: String arguments in LSX condition attributes require `&apos;` instead of `'`: `SpellId(&apos;Target_Web&apos;)`. Plain quotes cause parse errors.
- **SpellAnimation cast sequence**: Prepare (1) → Idle (5) → Smear Cast (2) → Attack/Cast (3) → Return Smear (4). Cancel sequence: Prepare (1) → Idle (5) → Cancel Smear (6) → Cancel Return (7). Most spells only populate phases 3 and 4.

---

## Scripting & Runtime Notes

### Script Extender (SE) Lua

```lua
-- Read spell stats
local stat = Ext.Stats.Get("Projectile_Fireball")
local damage = stat.Damage
local spellType = stat.SpellType

-- Modify at runtime (MUST sync after)
stat.Damage = "10d6"
stat.AreaRadius = 6
Ext.Stats.Sync("Projectile_Fireball")

-- Create new spell inheriting from existing
local custom = Ext.Stats.Create("Projectile_Fireball_Mega", "SpellData", "Projectile_Fireball")
custom.Damage = "12d6"
Ext.Stats.Sync("Projectile_Fireball_Mega")
```

> **CRITICAL:** `Ext.Stats.Sync()` is mandatory after any runtime change — without it modifications are invisible.

### Osiris Events

| Event | Signature | Relevance |
|-------|-----------|----------|
| `CastedSpell` | `(character, spell)` | Fires when a spell is cast; `spell` matches the entry name |
| `StatusApplied` | `(obj, status, causee, storyId)` | Fires when `SpellSuccess` applies a status |
| `EnteredCombat` | `(character, combatId)` | Combat-only spell availability |

### Condition Functions for Spells

Common condition functions usable in `TargetConditions`, `SpellRoll`, etc.:

| Function | Purpose |
|----------|--------|
| `SpellId('SpellName')` | Match a specific spell by entry name |
| `IsSpellOfSchool()` | Match spells by school of magic |
| `HasSpellFlag()` | Match by SpellFlags field |
| `HasUseCosts()` | Match by action resource costs |
| `HasFunctor()` | Match by functor type |

> These can also be used in `MetaConditions.Filter` to target spells for condition overlay.
