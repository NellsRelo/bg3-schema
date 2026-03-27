# PassiveData

> **Type identifier**: `PassiveData`
> **Source file**: `Stats/Generated/Data/Passive.txt`
> **Modifier definition**: [Modifiers.md](../formats/Modifiers.md#passivedata) (29 fields)

---

## Overview

Defines passive features, abilities, and toggleable effects. These are referenced by `Passives` and `PassivesOnEquip` fields in other stat types (Character, Armor, Weapon, Object, StatusData). Passives provide always-on boosts, triggered functors, and togglable abilities (e.g., Non-Lethal Attacks, Metamagic).

## Entry Format

```
new entry "ColossusSlayer"
type "PassiveData"
data "DisplayName" "h...;1"
data "Description" "h...;3"
data "DescriptionParams" "DealDamage(1d8,MainRangedWeaponDamageType)"
data "Icon" "PassiveFeature_ColossusSlayer"
data "Properties" "OncePerTurn;Highlighted"
data "Boosts" ""
data "StatsFunctors" "DealDamage(1d8, MainRangedWeaponDamageType)"
data "StatsFunctorContext" "OnDamage"
data "Conditions" "IsWeaponAttack() and HasDamageEffectFlag(DamageFlags.Hit) and not HasMaxHP()"
```

## Pack Distribution

| Pack | Notes |
|------|-------|
| Shared | Primary — class features, racial traits, feats |
| SharedDev | Development entries |
| Gustav | Module-specific passives |
| GustavDev | Development entries |
| GustavX | DLC passives |
| Honour | Honour-mode overrides |

---

## Form Reference — All Fields

> Complete field table for form/editor construction. 29 fields defined in [Modifiers.md](../formats/Modifiers.md#passivedata). ✓ = observed in vanilla data.

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

### Boost Fields & Observed Boosts

| Boost Field | Purpose |
|-------------|--------|
| `Boosts` | Passive boost expressions (conditional via BoostConditions/BoostContext) |

**Boosts used in vanilla (53):** `Ability` · `AbilityOverrideMinimum` · `AC` · `ACOverrideFormula` · `ActionResource` · `ActionResourceOverride` · `ActionResourceReplenishTypeOverride` · `ActiveCharacterLight` · `AddProficiencyToAC` · `AddProficiencyToDamage` · `Advantage` · `ArmorAbilityModifierCapOverride` · `Attribute` · `BlockVerbalComponent` · `CannotBeDisarmed` · `CarryCapacityMultiplier` · `CharacterUnarmedDamage` · `CharacterWeaponDamage` · `CriticalDamageOnHit` · `CriticalHit` · `DamageBonus` · `DamageReduction` · `DarkvisionRangeMin` · `Disadvantage` · `DownedStatus` · `DualWielding` · `EntityThrowDamage` · `ExpertiseBonus` · `FallDamageMultiplier` · `IgnoreLowGroundPenalty` · `IgnorePointBlankDisadvantage` · `IgnoreResistance` · `IgnoreSurfaceCover` · `IncreaseMaxHP` · `Initiative` · `JumpMaxDistanceMultiplier` · `MinimumRollResult` · `NonLethal` · `Proficiency` · `ProficiencyBonus` · `ReduceCriticalAttackThreshold` · `Reroll` · `Resistance` · `RollBonus` · `Skill` · `StatusImmunity` · `Tag` · `TwoWeaponFighting` · `UnlockInterrupt` · `UnlockSpell` · `UnlockSpellVariant` · `Weight` · `WeightCategory`

### Functor Fields & Observed Functors

| Functor Field | Purpose |
|---------------|--------|
| `StatsFunctors` | Main passive functors (triggered by StatsFunctorContext) |
| `ToggleOnFunctors` | Functors when toggled on |
| `ToggleOffFunctors` | Functors when toggled off |

**Functors used in vanilla (12):** `ApplyStatus` · `CreateExplosion` · `DealDamage` · `Kill` · `RegainHitPoints` · `RemoveStatus` · `RestoreResource` · `SetStatusDuration` · `SwapPlaces` · `TriggerRandomCast` · `UseActionResource` · `UseSpell`

---

## Complete Field Reference

### Display

#### `DisplayName`
- **Type**: TranslatedString
- **Values**: `"ha0a9d4d4gdd96g431dgb386g6a35a5eb2878;1"` (handle format)
- **Notes**: Localized display name.

#### `DisplayNameRef`
- **Type**: TranslatedString
- **Notes**: Alternate display name reference.

#### `Description`
- **Type**: TranslatedString
- **Values**: `"hcc220960g681dg4db6g8cbag2c055807eed3;7"`
- **Notes**: Full description. Version number after `;` tracks translation iterations.

#### `DescriptionRef`
- **Type**: TranslatedString
- **Notes**: Alternate description reference.

#### `DescriptionParams`
- **Type**: FixedString
- **Values**: `"DealDamage(2, Piercing)"`, `"Distance(12)"`, `"LevelMapValue(SuperiorityDie)"`, `"ClassLevel(Wizard)"`, `"DealDamage(1d8,Radiant)"`, `"1d6"`, `"DealDamage(2d6,Slashing); 50"` (multi-param)
- **Notes**: Semicolon-separated expressions providing values for description placeholders (`[1]`, `[2]`). Uses functor syntax, stat references, and literal values.

#### `ExtraDescription`
- **Type**: TranslatedString
- **Notes**: Additional description for expanded tooltip.

#### `ExtraDescriptionRef`
- **Type**: TranslatedString
- **Notes**: Alternate extra description reference.

#### `ExtraDescriptionParams`
- **Type**: FixedString
- **Values**: `"1"`, `"GainTemporaryHitPoints(7)"`, `"Distance(1.5)"`
- **Notes**: Parameters for extra description placeholders.

#### `LoreDescription`
- **Type**: TranslatedString
- **Notes**: Flavor/lore text.

#### `LoreDescriptionRef`
- **Type**: TranslatedString
- **Notes**: Alternate lore description reference.

#### `Icon`
- **Type**: FixedString
- **Values**: `"PassiveFeature_HeavyArmorMaster"`, `"PassiveFeature_AttackOfOpportunity"`, `"Spell_Abjuration_MageArmor"`, `"Action_KnockOut"`, `"GenericIcon_DamageType_Necrotic"`, `"statIcons_Ettercap_Infested"`, `"unknown"`
- **Notes**: Icon asset name. Naming patterns: `PassiveFeature_{Name}` for features, `Spell_{School}_{Name}` for spell-based, `Action_{Name}` for actions, `GenericIcon_*` for generic. `"unknown"` as fallback.

### Properties

#### `Properties`
- **Type**: PassiveFlags (flags enum)
- **Values**: Semicolon-separated. All observed flags:
  - **Display**: `Highlighted` (shown in passive list), `ForceShowInCC` (shown in character creation), `IsHidden` (hidden from UI), `DisplayBoostInTooltip`
  - **Toggle**: `IsToggled` (can be toggled), `ToggledDefaultAddToHotbar` (added to hotbar), `ToggledDefaultOn` (starts active), `ToggleForParty` (toggles for whole party)
  - **Frequency**: `OncePerTurn`, `OncePerCombat`, `OncePerShortRest`
  - **Special**: `Temporary` (removed on rest), `MetaMagic` (metamagic passive)
- **Notes**: Common combinations:
  - `"IsHidden"` — hidden passive
  - `"Highlighted"` — visible feature
  - `"Highlighted;ForceShowInCC"` — shown in character creation
  - `"IsToggled;ToggledDefaultAddToHotbar;ToggleForParty"` — full toggle (Non-Lethal)
  - `"IsToggled;ToggledDefaultAddToHotbar;MetaMagic"` — metamagic toggle
  - `"OncePerTurn;Highlighted"` — per-turn feature (Colossus Slayer)

#### `PriorityOrder`
- **Type**: ConstantInt
- **Values**: `"1"`, `"2"`
- **Notes**: Priority ordering when multiple passives compete.

### Boost System

#### `Boosts`
- **Type**: FixedString
- **Values**: Wide variety of boost expressions, semicolon-separated:
  - **Ability**: `"Ability(Charisma, 1)"`, `"Ability(Strength, -1)"`
  - **AC**: `"AC(1)"`, `"ACOverrideFormula(13,true,Dexterity)"`
  - **Proficiency**: `"Proficiency(Rapiers);Proficiency(Shortswords);Proficiency(HandCrossbows)"`, `"ProficiencyBonus(Skill,History);ExpertiseBonus(History)"`
  - **Advantage**: `"Advantage(SavingThrow, Wisdom)"`, `"Advantage(Ability, Strength)"`
  - **Resistance**: `"Resistance(Poison, Resistant)"`, `"DamageReduction(Fire,Resistant)"`
  - **Resources**: `"ActionResource(BonusActionPoint,1,0)"`, `"ActionResource(Movement, -1.5, 0)"`, `"ActionResource(SpellSlot,1,1)"`
  - **Unlock**: `"UnlockInterrupt(Interrupt_AttackOfOpportunity)"`, `"UnlockSpell(Target_BardicInspiration)"`, `"UnlockSpell(Target_Grease,AddChildren,UUID,Charisma)"`
  - **Tags**: `"Tag(BLINDSIGHT);StatusImmunity(SG_Blinded)"`
  - **Rerolls**: `"Reroll(Attack,1,true);Reroll(SkillCheck,1,true)"` — Reroll(type, threshold, spend)
  - **Roll Bonus**: `"RollBonus(SkillCheck,1d6);RollBonus(RawAbility,1d6)"`
  - **Combat**: `"CriticalHitExtraDice(1,MeleeWeaponAttack)"`, `"CriticalDamageOnHit()"`, `"TwoWeaponFighting()"`, `"DamageBonus(4d8, Slashing,1)"`
  - **Special**: `"CarryCapacityMultiplier(2)"`, `"FallDamageMultiplier(0.5)"`, `"EntityThrowDamage(8)"`, `"ActionResourceMultiplier(Movement,200,0);IgnoreLeaveAttackRange()"`
  - **Conditional**: `"IF(HasStatus('SURPRISED')):CriticalDamageOnHit()"`, `"IF(SpellId('Projectile_EldritchBlast') and IsCharismaModifierPositive()):DamageBonus(CharismaModifier,Force)"`
  - **SpellVariant**: `"UnlockSpellVariant(SpellId('Throw_Throw'),ModifyVisuals(Action_ThrowWeapon))"`, `"UnlockSpellVariant(CarefulSpellCheck(),ModifySpellRoll('not SavingThrow','SpellAutoResolveOnAlly'),ModifyUseCosts(Add,SorceryPoint,1,0))"`
- **Notes**: Boosts are always-on while the passive is active. They modify stats, grant abilities, unlock spells/interrupts. Conditional boosts use `IF(condition):Boost(...)` syntax.

#### `BoostConditions`
- **Type**: Conditions
- **Values**: `"not WearingArmor(context.Source)"`, `"WearingArmor(context.Source)"`, `"HasThrownWeaponInInventory(context.Source)"`, `"not SizeEqualOrGreater(Size.Huge, context.Source)"`, `"not HasStatus('BLINDED') and not HasStatus('KNOCKED_OUT')"`, `"InSurface('SurfaceAlcohol') or InSurface('SurfaceBlood')"`, `"not Dead() and HasHPPercentageWithoutTemporaryHPLessThan(20, context.Target)"`
- **Notes**: Boolean condition for boost activation. Uses `context.Source` (the passive holder) and `context.Target` (for attack/effect targets). Common checks: armor state, size, status, HP percentage, surface.

#### `BoostContext`
- **Type**: StatsFunctorContext (flags enum)
- **Values**: `"OnEquip;OnCreate"`, `"OnCreate;OnInventoryChanged"`, `"OnStatusApplied;OnStatusRemoved;OnCreate"`, `"OnPushed;OnMovedDistance"`, `"OnDamaged;OnHealed"`
- **Notes**: Events that trigger boost condition re-evaluation. Semicolon-separated. `"OnEquip;OnCreate"` is most common — evaluates on equip and initial creation.

### Functor System

#### `StatsFunctors`
- **Type**: StatsFunctors
- **Values**: `"RegainHitPoints(MaxHP/2)"`, `"DealDamage(max(1,StrengthModifier), MainMeleeWeaponDamageType)"`, `"ApplyStatus(GAPING_WOUND_DAMAGE, 100, 0)"`, `"RestoreResource(BonusActionPoint, 100%, 0);RestoreResource(ActionPoint, 100%, 0)"`, `"RemoveStatus(SELF,BARDIC_INSPIRATION)"`, `"DealDamage(SWAP,2d8, Lightning,Magical)"`, `"CreateExplosion(Projectile_ClarifiedMortality)"`, `"UseSpell(SELF,Shout_StillnessOfMind,true,true,true)"`, `"UseActionResource(ReactionActionPoint,1)"`
- **Notes**: Semicolon-separated functor chain executed when `Conditions` is met in the given `StatsFunctorContext`. Supports target prefixes (`SELF:`, `SWAP:`), conditional `IF()`, and complex expressions. `SWAP` = swap source/target for reflexive damage.

#### `StatsFunctorContext`
- **Type**: StatsFunctorContext (flags enum)
- **Values**: `"OnShortRest"`, `"OnDamaged"`, `"OnDamage"`, `"OnAttack"`, `"OnAttacked"`, `"OnTurn"`, `"OnCast;OnAttack"`, `"OnCast;OnStatusRemoved;OnStatusApplied"`, `"OnHeal"`, `"OnAbilityCheck"`, `"OnStatusApplied"`, `"OnLongRest;OnCreate"`, `"OnShortRest;OnLongRest"`
- **Notes**: When StatsFunctors fire. `"OnDamage"` = when you deal damage, `"OnDamaged"` = when you take damage, `"OnAttack"` = when you make an attack, `"OnAttacked"` = when you are attacked. Multiple contexts can be combined.

#### `Conditions`
- **Type**: Conditions
- **Values**: `"IsAttack()"`, `"IsCritical()"`, `"IsWeaponAttack() and HasDamageEffectFlag(DamageFlags.Hit) and not HasMaxHP()"`, `"HasHPLessThan(1) and Enemy() and Character()"`, `"SpellId('Projectile_EldritchBlast') and HasDamageEffectFlag(DamageFlags.Hit)"`, `"HealDoneGreaterThan(0) and IsSpell() and not IsCantrip()"`, `"(context.HasContextFlag(StatsFunctorContext.OnCast) and ExtraAttackSpellCheck() and HasUseCosts('ActionPoint', true)) or (context.HasContextFlag(StatsFunctorContext.OnStatusRemoved) and StatusId('INITIAL_ATTACK_TECHNICAL') and TurnBased())"`
- **Notes**: Boolean condition expressions determining when `StatsFunctors` execute. Very expressive — includes attack type checks, spell ID matching, damage flag checks, HP thresholds, context flag branching. Used with `StatsFunctorContext` to filter when + what.

### Enable System (Toggle Gating)

#### `EnabledConditions`
- **Type**: Conditions
- **Values**: `"HasActionResource('SorceryPoint', 1, 0, false, false, context.Source)"`, `"HasActionResource('SorceryPoint', 3, 0, false, false, context.Source)"`
- **Notes**: Conditions for the toggle to become usable. Primarily used by Metamagic — requires sorcery points to activate.

#### `EnabledContext`
- **Type**: StatsFunctorContext (flags enum)
- **Values**: `"OnCastResolved;OnLongRest;OnActionResourcesChanged"`
- **Notes**: Events that trigger EnabledConditions re-evaluation.

### Toggle System

#### `ToggleGroup`
- **Type**: FixedString
- **Values**: `"NonLethal"`, `"Metamagic"`
- **Notes**: Mutual exclusion group. Only one toggle in the same group can be active. All Metamagic passives share `"Metamagic"` group.

#### `ToggleOnFunctors`
- **Type**: StatsFunctors
- **Values**: `"ApplyStatus(NON_LETHAL,100,-1)"`, `"ApplyStatus(SELF,TWINNED_ON,100,-1)"`, `"ApplyStatus(FLAMING_SPHERE_AURA_3,100,-1)"`
- **Notes**: Executed when toggle is turned on. Typically applies a persistent status.

#### `ToggleOffFunctors`
- **Type**: StatsFunctors
- **Values**: `"RemoveStatus(NON_LETHAL)"`, `"RemoveStatus(SELF,TWINNED_ON,100,-1)"`, `"RemoveStatus(FLAMING_SPHERE_AURA_3)"`
- **Notes**: Executed when toggle is turned off. Typically removes the status applied by ToggleOnFunctors.

#### `ToggleOnEffect`
- **Type**: FixedString
- **Values**: `"VFX_Spells_Cast_Bard_Generic_BodyFX_Passive_BardicInspiration_Ability_01:Dummy_BodyFX:;"`, `"VFX_Spells_Cast_Sorcerer_Metamagic_Careful_HeadFX_01:Dummy_HeadFX"`, `""` (empty override)
- **Notes**: VFX played on toggle on. Format: `VFXName:BoneAttachment:;`. Empty string clears inherited VFX.

#### `ToggleOffEffect`
- **Type**: FixedString
- **Notes**: VFX played on toggle off.

#### `ToggleOffContext`
- **Type**: StatsFunctorContext (flags enum)
- **Values**: `"OnCastResolved"`, `"OnAbilityCheck"`, `""` (empty override)
- **Notes**: Auto-deactivation event. `"OnCastResolved"` = turns off after a spell is cast (Metamagic consumes on use).

### Animation

#### `DynamicAnimationTag`
- **Type**: Guid
- **Values**: UUID
- **Notes**: Animation tag UUID for dynamic animation selection.

### Tooltips

#### `TooltipConditionalDamage`
- **Type**: FixedString
- **Values**: `"DealDamage(3d4, MainMeleeWeaponDamageType,true)"`, `"DealDamage(8, Piercing)"`, `"DealDamage(1d6,Necrotic)"`, `""` (empty override)
- **Notes**: Conditional damage shown in tooltip. Uses functor syntax.

#### `TooltipSave`
- **Type**: FixedString
- **Values**: `"Dexterity"`, `"Strength"`, `"Constitution"`, `"Wisdom"`, `""` (empty override)
- **Notes**: Ability name for tooltip save display.

#### `TooltipPermanentWarnings`
- **Type**: FixedString
- **Values**: `"8892b93b-721f-4b99-b9b4-05ac25aadb33"` (UUID reference), `""` (empty override)
- **Notes**: UUID referencing warning text.

---

## Cross-References

| From | To | Via |
|------|----|----|
| PassiveData.Boosts `UnlockSpell()` | SpellData | Spell entry name |
| PassiveData.Boosts `UnlockInterrupt()` | InterruptData | Interrupt entry name |
| PassiveData.StatsFunctors `ApplyStatus()` | StatusData | Status entry name |
| PassiveData.ToggleOnFunctors | StatusData | `ApplyStatus(NAME,...)` |
| Character.Passives | PassiveData | Passive entry names |
| Weapon.PassivesOnEquip | PassiveData | Passive entry names |
| Armor.PassivesOnEquip | PassiveData | Passive entry names |
| StatusData.Passives | PassiveData | Passive entry names |

## Caveats & Gotchas

- **StatsFunctorContext required**: Setting `StatsFunctors` without `StatsFunctorContext` means functors never fire. Always pair them.
- **OnDamage vs OnDamaged**: `"OnDamage"` = you deal damage (offensive trigger). `"OnDamaged"` = you receive damage (defensive trigger). These are different events.
- **ToggleGroup mutual exclusion**: All passives in the same ToggleGroup are mutually exclusive. Enabling one disables others.
- **BoostContext re-evaluation**: Boosts are cached and only re-evaluated on context events. Without proper `BoostContext`, conditional boosts won't update when conditions change.
- **Toggle lifecycle**: Toggle passives need `IsToggled` in Properties plus `ToggleOnFunctors`/`ToggleOffFunctors` for behavior. `ToggleOffContext` auto-deactivates when the event fires.
- **SWAP target prefix**: In StatsFunctors, `SWAP` swaps source and target — used for reflexive damage (e.g., thorns/retribution effects where the attacker takes damage).
- **context.HasContextFlag**: In complex `Conditions`, `context.HasContextFlag(StatsFunctorContext.OnCast)` allows branching behavior based on which trigger fired when `StatsFunctorContext` lists multiple contexts.
- **Empty string override**: Setting a field to `""` when using `using` (inheritance) explicitly clears the inherited value. Important for VFX/conditions.
- **OnDamage loop risk**: Passives with `OnDamage` context and `DealDamage` functors can loop infinitely. Use `IgnoreOnDamage=true` (arg 8): `DealDamage(1d6,Fire,,0,,true)`.
- **OnStatusApply/Applied loop risk**: Passives with `OnStatusApply` or `OnStatusApplied` context that apply statuses can trigger re-entrantly. The engine applies background statuses that re-fire these contexts.
- **OnCreate triggers on passive add**: `OnCreate` fires when the passive is added to the character, NOT when toggled on. Adding a toggle passive triggers `OnCreate` regardless of toggle state.
- **OnEquip limitations**: `StatsFunctorContext.OnEquip` sets `context.Target = Item`, `context.Source = Self`. Not ideal for status application — prefer `StatusOnEquip` on the equipment's stats entry or Osiris `Equipped` events.
- **EnabledConditions resource gating**: `HasActionResource('SorceryPoint', 1, 0, false, false, context.Source)` gates a toggle on resource availability. Without `EnabledContext` listing relevant events, the UI won't re-evaluate when resources change.
- **Conditional functor scope**: `IF(Condition):Functor1(args);Functor2(args)` — the `IF()` only applies to `Functor1`. Repeat for each: `IF(Condition):Functor1(args);IF(Condition):Functor2(args)`.
- **DealDamage CoinMultiplier null**: In `StatsFunctors`, `DealDamage` arg 5 (CoinMultiplier) does NOT accept empty — use `0`. Empty arg silently fails.
- **Cross-format name matching**: Passive entry names referenced from `Progression.PassivesAdded`, `Character.Passives`, `Feat.PassivesAdded`, etc. are **case-sensitive**. Mismatches fail silently.
- **Inheritance load order**: `using "ParentPassive"` requires the parent in the same file or an earlier-loaded file. Forward references fail silently.

---

## Scripting & Runtime Notes

### Script Extender (SE) Lua

```lua
-- Read passive stats
local stat = Ext.Stats.Get("GreatWeaponMaster_BonusAttack")
local boosts = stat.Boosts
local context = stat.StatsFunctorContext

-- Modify at runtime (MUST sync after)
stat.Boosts = "CharacterWeaponDamage(10)"
Ext.Stats.Sync("GreatWeaponMaster_BonusAttack")
```

> **CRITICAL:** `Ext.Stats.Sync()` is mandatory after any runtime change — without it modifications are invisible.

### Osiris Events

| Event | Signature | Relevance |
|-------|-----------|----------|
| `StatusApplied` | `(obj, status, causee, storyId)` | Fires when passive's `ToggleOnFunctors` applies a status |
| `StatusRemoved` | `(obj, status)` | Fires when passive's `ToggleOffFunctors` removes a status |
| `LeveledUp` | `(character, level)` | Progressions may add/remove passives |

### StatsFunctorContext Source/Target Reference

The meaning of `context.Source` and `context.Target` varies by context. Key passive contexts:

| Context | Target | Source | Loop Risk |
|---------|--------|--------|:---------:|
| `OnDamage` | Damage target | Self | **Yes** |
| `OnDamaged` | Self | Damage source | **Yes** |
| `OnAttack` | Attack target | Self | — |
| `OnAttacked` | Self | Attacker | — |
| `OnStatusApplied` | Self | Status source | **Yes** |
| `OnTurn` | Self | Self | — |
| `OnCast` | Self | Self | — |
| `OnShortRest` | Self | Self | — |
| `OnLongRest` | Self | Self | — |
| `OnCreate` | Self | Self | **Yes** |
