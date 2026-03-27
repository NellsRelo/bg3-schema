# InterruptData

> **Type identifier**: `InterruptData`
> **Source file**: `Stats/Generated/Data/Interrupt.txt`
> **Modifier definition**: [Modifiers.md](../formats/Modifiers.md#interruptdata) (30 fields)

---

## Overview

Defines interrupt/reaction abilities — triggered responses that fire during other creatures' turns or in response to specific events (attacks, spell casts, movement, death). Includes conditions for triggering, roll mechanics, success/failure functors, and resource costs. The interrupt system powers reactions like Counterspell, Attack of Opportunity, Divine Smite, and Bardic Inspiration.

## Entry Format

```
new entry "Counterspell"
type "InterruptData"
data "DisplayName" "h...;2"
data "Description" "h...;3"
data "Icon" "PassiveFeature_Counterspell"
data "InterruptContext" "OnSpellCast"
data "InterruptContextScope" "Nearby"
data "InterruptDefaultValue" "Ask;Enabled"
data "Container" "YesNoDecision"
data "Conditions" "SpellLevelLessThanOrEqual(3) and not Self()"
data "Roll" "TryCounterspellHigherLevel(3)"
data "Success" "Counterspell();UseSpell(OBSERVER_SOURCE,Target_Counterspell_Success,true,true,true)"
data "Failure" "UseSpell(OBSERVER_SOURCE,Target_Counterspell_Failure,true,true,true)"
data "Cost" "ReactionActionPoint:1;SpellSlotsGroup:1:1:3"
data "Properties" ""
data "InterruptFlags" ""
```

## Pack Distribution

| Pack | Notes |
|------|-------|
| Shared | Primary — core reactions (Counterspell, Shield, AoO, Smite) |
| SharedDev | Development entries |
| Gustav | Module-specific interrupts |
| GustavDev | Development entries |
| GustavX | DLC interrupts |
| Honour | Honour-mode additions (Legendary Actions) |

---

## Form Reference — All Fields

> Complete field table for form/editor construction. 30 fields defined in [Modifiers.md](../formats/Modifiers.md#interruptdata). ✓ = observed in vanilla data.

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

### Boost Fields & Observed Boosts

None — InterruptData does not have boost-accepting fields.

### Functor Fields & Observed Functors

| Functor Field | Purpose |
|---------------|--------|
| `Properties` | Main interrupt effect functors |
| `Success` | Functors on successful roll |
| `Failure` | Functors on failed roll |

**Functors used in vanilla (11):** `AdjustRoll` · `ApplyStatus` · `Counterspell` · `DealDamage` · `RemoveStatus` · `SetAdvantage` · `SetDisadvantage` · `SetRoll` · `TutorialEvent` · `UseAttack` · `UseSpell`

---

## Complete Field Reference

### Display

#### `DisplayName`
- **Type**: TranslatedString
- **Values**: `"h48686e1eg13fdg4ee5g8b51gb3eb602d599d;2"` (handle format)
- **Notes**: Localized display name.

#### `DisplayNameRef`
- **Type**: TranslatedString
- **Notes**: Alternate display name reference.

#### `Description`
- **Type**: TranslatedString
- **Values**: Handle format
- **Notes**: Full interrupt description.

#### `DescriptionRef`
- **Type**: TranslatedString
- **Notes**: Alternate description reference.

#### `DescriptionParams`
- **Type**: FixedString
- **Values**: `"1d6"`, `"DealDamage(2d8,Radiant)"`, `"DealDamage(ClassLevel(Sorcerer)/2,Lightning);Distance(6)"`, `"ProficiencyBonus"`, `"10"`
- **Notes**: Semicolon-separated expressions for description placeholders.

#### `ExtraDescription`
- **Type**: TranslatedString
- **Notes**: Additional description for expanded tooltip.

#### `ExtraDescriptionRef`
- **Type**: TranslatedString
- **Notes**: Alternate extra description reference.

#### `ExtraDescriptionParams`
- **Type**: FixedString
- **Notes**: Parameters for extra description placeholders.

#### `LoreDescription`
- **Type**: TranslatedString
- **Notes**: Lore/flavor text. Not commonly used.

#### `LoreDescriptionRef`
- **Type**: TranslatedString
- **Notes**: Alternate lore description reference.

#### `ShortDescription`
- **Type**: TranslatedString
- **Notes**: Short description for compact UI.

#### `ShortDescriptionRef`
- **Type**: TranslatedString
- **Notes**: Alternate short description reference.

#### `ShortDescriptionParams`
- **Type**: FixedString
- **Notes**: Parameters for short description placeholders.

#### `Icon`
- **Type**: FixedString
- **Values**: `"PassiveFeature_Counterspell"`, `"Action_Paladin_DivineSmite"`, `"PassiveFeature_AttackOfOpportunity"`, `"Spell_Abjuration_Shield"`, `"Spell_Evocation_HellishRebuke"`
- **Notes**: Icon asset name.

### Interrupt Mechanics

#### `InterruptContext`
- **Type**: InterruptContext (enum, semicolon-combinable)
- **Values**: `"OnSpellCast"`, `"OnPostRoll"`, `"OnPreDamage"`, `"OnCastHit"`, `"OnLeaveAttackRange"`, `"OnEnterAttackRange"`, `"OnDeath"`, `"OnStatusApplied"`, `"OnSpellCast;OnCastHit"`, `"OnPostRoll;OnPreDamage"`
- **Notes**: When the interrupt can trigger. Multiple contexts can be combined with semicolons.
  - `OnSpellCast` — when an enemy casts a spell (Counterspell, Mage Slayer)
  - `OnPostRoll` — after a roll is made (Bardic Inspiration, Cutting Words, Defensive Duelist)
  - `OnPreDamage` — before damage is applied (Shield Master, Adamantine reactions)
  - `OnCastHit` — when a cast/attack hits (Divine Smite, Riposte, Hellish Rebuke)
  - `OnLeaveAttackRange` — when a creature leaves melee range (Attack of Opportunity)
  - `OnEnterAttackRange` — when a creature enters range (Sentinel-style)
  - `OnDeath` — when a creature dies (necromantic reactions)
  - `OnStatusApplied` — when a status is applied

#### `InterruptContextScope`
- **Type**: InterruptContextScope (enum)
- **Values**: `"Self"`, `"Nearby"`, `"Far"`
- **Notes**: Range scope for the interrupt trigger.
  - `Self` — only triggers for/on the interrupt holder (Bardic Inspiration on own rolls, Defensive Duelist)
  - `Nearby` — triggers for nearby allies/enemies within normal range (Counterspell, Cutting Words)
  - `Far` — triggers at extended range (rare, e.g., soul-link effects)

#### `InterruptDefaultValue`
- **Type**: InterruptDefaultValue (semicolon-separated combo)
- **Values**: `"Enabled"`, `"Ask;Enabled"`, `"Enabled;Ask"`
- **Notes**: Default reaction behavior.
  - `Enabled` — auto-triggers without asking (Divine Smite, Attack of Opportunity)
  - `Ask;Enabled` — prompts the player and defaults to enabled
  - `Enabled;Ask` — enabled by default but prompts for confirmation

#### `InterruptFlags`
- **Type**: InterruptFlagsList (flags enum)
- **Values**: `"InterruptWhileInvisible"`
- **Notes**: Only one flag observed: `InterruptWhileInvisible` — allows interrupts while invisible (used by Orthon enemy abilities).

#### `Container`
- **Type**: FixedString
- **Values**: `"YesNoDecision"`
- **Notes**: Container UI for interrupt prompt. Almost always `"YesNoDecision"` for player-facing interrupts.

#### `Stack`
- **Type**: FixedString
- **Values**: `"AttackOfOpportunity"`, `"BardicInspiration"`, `"BendLuck"`, `"CosmicOmen"`, `"DivineSmite"`, `"HeartOfTheStorm"`, `"HellishRebuke"`, `"LegendaryResistance"`, `"SneakAttack"`, `"SongOfDefense"`, `"SwarmKeeper"`
- **Notes**: Stack ID for mutually exclusive interrupts. Multiple variants of the same interrupt share a Stack (e.g., all Divine Smite levels share `"DivineSmite"`).

#### `Cooldown`
- **Type**: CooldownType (enum from [ValueLists](../formats/ValueLists.md))
- **Values**: `"None"`, `"OncePerTurn"`, `"OncePerCombat"`, `"OncePerRestPerItem"`, `"OncePerShortRestPerItem"`
- **Notes**: Cooldown between uses. `"OncePerTurn"` for standard reactions. `"OncePerRestPerItem"` for item-granted reactions (ring, armor enchantment).

### Conditions

#### `Conditions`
- **Type**: Conditions
- **Values**: `"IsAbleToReact(context.Observer) and not Self(context.Observer, context.Source) and Enemy(context.Source, context.Observer)"`, `"SpellLevelLessThanOrEqual(3) and not Self()"`, `"HasInterruptedAttack() and not Uninterruptible()"`, `"TotalDamageDoneGreaterThan(0) and not Self(context.Observer, context.Source)"`, `"IsFlatValueInterruptInteresting(6, context.Source)"`, `"HasLastAttackTriggered()"`, `"HasStringInSpellRoll('WeaponAttack')"`
- **Notes**: Boolean conditions for when the interrupt triggers. Key interrupt-specific functions:
  - `IsAbleToReact(context.Observer)` — standard reaction availability check
  - `Self(context.Observer, context.Source)` — observer is the source
  - `Enemy(context.Source, context.Observer)` / `Ally()` — relationship checks
  - `HasInterruptedAttack()` / `HasInterruptedSavingThrow()` — type of interrupting action
  - `IsFlatValueInterruptInteresting(N, context.Source)` — is a +N bonus worth prompting for
  - `IsRerollInterruptInteresting(context.Source)` — is reroll beneficial
  - `InterruptHasAdvantage()` / `InterruptHasDisadvantage()` — advantage state
  - `CounterspellCheck()` — counterspell-specific validation
  - `SpellPowerLevelEqualOrLessThan()` — power level check
  - `HasStringInSpellRoll('WeaponAttack')` — roll type matching
  - `not Uninterruptible()` — target can be interrupted

#### `EnableCondition`
- **Type**: Conditions
- **Values**: `"not HasStatus('SG_Polymorph') or HasAnyStatus({'SG_Disguise','WILDSHAPE_STARRY_ARCHER_PLAYER'})"`, `"HasShieldEquipped(context.Source) and (not HasStatus('SG_Polymorph') or ...)"`, `"HasActionResource('Interrupt_MAG_Counterspell', 1, 0, false, false, context.Source)"`, `"IsWeaponOfProficiencyGroup('Greatswords', GetActiveWeapon())"`, `"not HasStatus('SG_Blinded')"`
- **Notes**: Conditions for the interrupt to be available in the UI. Checks: polymorph state, equipment, action resources, weapon proficiency, status effects.

#### `EnableContext`
- **Type**: StatsFunctorContext (flags enum)
- **Values**: `"OnStatusApplied;OnStatusRemoved"`, `"OnEquip"`, `"OnEquip;OnStatusApplied;OnStatusRemoved"`, `"OnActionResourcesChanged"`, `"OnActionResourcesChanged;OnStatusApplied;OnStatusRemoved"`
- **Notes**: Events that trigger EnableCondition re-evaluation. Most common: `"OnStatusApplied;OnStatusRemoved"` — re-check when status changes.

### Rolls & Effects

#### `Roll`
- **Type**: Conditions
- **Values**: `"TryCounterspellHigherLevel(3)"`, `"TryCounterspellHigherLevel(4)"`, `"TryCounterspellHigherLevel(5)"`, `"TryCounterspellHigherLevel(6)"`, `"not SavingThrow(Ability.Wisdom, SourceSpellDC(14,context.Observer,Ability.Intelligence),AdvantageOnCharmPerson(),false,context.Source)"`, `"not SavingThrow(Ability.Constitution, SourceSpellDC(10,context.Observer,Ability.Wisdom))"`, `"RollDieAgainstPercent(DiceType.d4,2)"`
- **Notes**: Roll expression for the interrupt. Similar to SpellData.SpellRoll but with interrupt-specific functions like `TryCounterspellHigherLevel(N)`. `SourceSpellDC()` uses extended syntax with observer/ability overrides.

#### `Success`
- **Type**: StatsFunctors
- **Values**: `"Counterspell();UseSpell(OBSERVER_SOURCE,Target_Counterspell_Success,true,true,true)"`, `"SetRoll(OBSERVER_TARGET,1);UseSpell(OBSERVER_SOURCE,Target_ArmorOfHexes,true,true,true,UUID)"`, `"ApplyStatus(OBSERVER_TARGET,PRONE,100,1)"`, `"ApplyStatus(BLINDED,100,1);ApplyStatus(SLOW,100,1)"`
- **Notes**: Functors on success. Uses interrupt-specific target prefixes: `OBSERVER_SOURCE` (the interrupt holder), `OBSERVER_TARGET` (the interrupted creature), `SWAP` (reverse source/target).

#### `Failure`
- **Type**: StatsFunctors
- **Values**: `"UseSpell(OBSERVER_SOURCE,Target_Counterspell_Failure,true,true,true)"`, `"ApplyStatus(OBSERVER_SOURCE,INSTINCTIVE_CHARM_UNTARGETABLE, 100, -1)"`, `"ApplyStatus(OBSERVER_TARGET,BEE_MISS_VFX,100,0)"`
- **Notes**: Functors on failure. Common pattern: apply a VFX/status to indicate the failed attempt.

#### `Properties`
- **Type**: StatsFunctors
- **Values**: Always-execute functors. Key patterns:
  - **AdjustRoll**: `"AdjustRoll(-10)"`, `"AdjustRoll(1d4)"`, `"AdjustRoll(-1d4)"`, `"AdjustRoll(OBSERVER_OBSERVER,ResourceRoll(BardicInspiration,1))"`, `"AdjustRoll(99)"`, `"AdjustRoll(-99)"`
  - **SetAdvantage/Disadvantage**: `"SetAdvantage()"`, `"SetDisadvantage()"`
  - **SetRoll**: `"SetRoll(0)"`, `"SetRoll(20)"`
  - **ApplyStatus**: `"ApplyStatus(OBSERVER_OBSERVER,RECKLESS_ATTACK,100,1)"`, `"ApplyStatus(SWAP,PASSIVE_DEFENSIVE_DUELIST,100,0)"`
  - **UseSpell/UseAttack**: `"UseSpell(SWAP,Target_Riposte,true,true,true)"`, `"UseAttack()"`, `"UseAttack(SWAP)"`
  - **DealDamage**: `"DealDamage(ResourceRoll(BardicInspiration,1), MainMeleeWeaponDamageType)"`, `"DealDamage(OBSERVER_SOURCE,1d4*SpellPowerLevel,Psychic)"`
  - **SetDamageResistance**: `"SetDamageResistance(Acid);SetDamageResistance(Cold);..."` (all types)
  - **Conditional**: `"IF(not UndeadOrFiend(context.Target)):DealDamage(2d8,Radiant,Magical);IF(UndeadOrFiend(context.Target)):DealDamage(3d8,Radiant,Magical)"`
  - **Special**: `"Counterspell()"`, `"TriggerRandomCast(OBSERVER_SOURCE,1,0,WildMagicEvil)"`
- **Notes**: Properties are always-execute functors (regardless of Roll outcome). This is the primary field for interrupt effects that don't depend on a roll.

### Costs

#### `Cost`
- **Type**: FixedString
- **Values**: `"ReactionActionPoint:1"`, `"ReactionActionPoint:1;SpellSlotsGroup:1:1:3"`, `"ReactionActionPoint:1;SuperiorityDie:1"`, `"ReactionActionPoint:1;BardicInspiration:1"`, `"ReactionActionPoint:1;SorceryPoint:2"`, `"ReactionActionPoint:1;KiPoint:1"`, `"ChannelDivinity:1"`, `"SorceryPoint:1"`, `"BardicInspiration:1"`, `"KiPoint:1"`, `"LuckPoint:1"`, `"LegendaryResistanceCharge:1"`, `"SneakAttack_Charge:1"`, `"SpellSlotsGroup:1:1:1"`, `"ReactionActionPoint:1;Interrupt_MAG_Counterspell:1"`, `"Interrupt_Portent_1:1"`, `"FungalInfestationCharge:1;ReactionActionPoint:1"`, `"TidesOfChaos:1"`, `"SwarmCharge:1"`
- **Notes**: Semicolon-separated `Resource:Amount` pairs. Most interrupts cost `ReactionActionPoint:1` (standard reaction). Additional resources: spell slots, superiority dice, bardic inspiration, ki points, sorcery points. Item-specific charges use custom resource names like `Interrupt_MAG_Counterspell:1`. Some interrupts don't need a reaction (just resource cost).

### Tooltips

#### `TooltipDamageList`
- **Type**: FixedString
- **Values**: `"DealDamage(6d10,Psychic)"`, `"DealDamage(2d6,Slashing)"`, `"DealDamage(3d6,Slashing)"`
- **Notes**: Tooltip damage display.

#### `TooltipAttackSave`
- **Type**: FixedString
- **Values**: `"Constitution"`, `"Dexterity"`, `"Intelligence"`
- **Notes**: Tooltip save ability.

#### `TooltipStatusApply`
- **Type**: FixedString
- **Values**: `"ApplyStatus(SILENCED)"`, `"ApplyStatus(BLEEDING,100,3)"`, `"ApplyStatus(PARALYZED_SPECTATOR,100,2);ApplyStatus(CONFUSION_RAY,100,2);ApplyStatus(FRIGHTENED,100,2)"`
- **Notes**: Tooltip status application info.

#### `TooltipOnSave`
- **Type**: FixedString
- **Notes**: Tooltip "on save" text.

#### `TooltipOnMiss`
- **Type**: FixedString
- **Notes**: Tooltip "on miss" text.

#### `TooltipPermanentWarnings`
- **Type**: FixedString
- **Notes**: Permanent tooltip warnings.

---

## Interrupt Target Prefixes

Interrupts use a unique set of target prefixes distinct from spell functors:

| Prefix | Meaning |
|--------|---------|
| `OBSERVER_SOURCE` | The interrupt holder (who is reacting) |
| `OBSERVER_TARGET` | The interrupted creature (who triggered it) |
| `OBSERVER_OBSERVER` | Self-reference for the observer (same as OBSERVER_SOURCE in most cases) |
| `SWAP` | Reverse source/target (attacker becomes target for Riposte-style effects) |

---

## Cross-References

| From | To | Via |
|------|----|----|
| InterruptData.Success/Failure `UseSpell()` | SpellData | Spell entry name |
| InterruptData.Success/Failure `ApplyStatus()` | StatusData | Status entry name |
| InterruptData.Properties `UseAttack()` | SpellData | Attack action |
| InterruptData.Stack | InterruptData | Mutual exclusion group |
| PassiveData.Boosts `UnlockInterrupt()` | InterruptData | Interrupt entry name |
| SpellData.InterruptPrototype | InterruptData | Interrupt entry name |

## Caveats & Gotchas

- **OBSERVER prefix**: Interrupt functors use `OBSERVER_SOURCE`/`OBSERVER_TARGET` — not `SELF`/`TARGET` like spell functors. Using spell-style prefixes in interrupts won't work correctly.
- **Container = YesNoDecision**: Almost all player-facing interrupts use `"YesNoDecision"` as the Container. This triggers the reaction prompt UI.
- **Stack mutual exclusion**: Interrupts with the same Stack value can't both trigger. All Divine Smite levels share `"DivineSmite"` stack — only one fires per event.
- **InterruptDefaultValue order matters**: `"Ask;Enabled"` and `"Enabled;Ask"` differ in default toggle behavior in the reactions panel.
- **Cost without ReactionActionPoint**: Some interrupts cost only resources (no reaction): `"BardicInspiration:1"`, `"KiPoint:1"`. These can trigger multiple times per round.
- **Properties vs Success/Failure**: `Properties` always execute. `Success`/`Failure` only execute based on the `Roll` result. If there's no `Roll`, use `Properties`.
- **context.Observer**: In interrupt conditions, `context.Observer` is the interrupt holder, `context.Source` is the actor who triggered the event, `context.Target` is the target of the triggering action. These differ from spell contexts.
- **Observer context source/target swap**: In Observer contexts (`OnEntityAttackedWithinMeleeRange`, `OnEntityAttackingWithinMeleeRange`), `context.Source`/`context.Target` can **swap** between `Conditions` and `Success`/`Failure`/`Properties` fields. In `Conditions`, Source = attacker; in functors, Source = passive owner.
- **Conditional functor scope**: `IF(Condition):Functor1(args);Functor2(args)` — the `IF()` only applies to `Functor1`. Repeat for each conditional functor.
- **DealDamage CoinMultiplier null**: In `Success`/`Failure`/`Properties`, `DealDamage` arg 5 (CoinMultiplier) does NOT accept empty — use `0`. Empty arg silently fails.
- **Cross-format name matching**: Interrupt entry names referenced from `SpellData.InterruptPrototype`, `PassiveData.Boosts "UnlockInterrupt(...)"`, etc. are **case-sensitive**. Mismatches fail silently.
- **Inheritance load order**: `using "ParentInterrupt"` requires the parent in the same file or an earlier-loaded file. Forward references fail silently.
- **EnableCondition polymorph check**: Most interrupts include `not HasStatus('SG_Polymorph')` in `EnableCondition` to prevent use while polymorphed. Wildshape exemptions use `or HasAnyStatus({'SG_Disguise','WILDSHAPE_...'})` to whitelist specific forms.
- **SpellSlotsGroup in Cost**: `SpellSlotsGroup:1:1:3` = 1 slot of level 3 or higher. Distinguished from `SpellSlot:1:1:3` = exactly level 3. Most smite-type interrupts use `SpellSlotsGroup` for flexible slot consumption.

---

## Scripting & Runtime Notes

### Script Extender (SE) Lua

```lua
-- Read interrupt stats
local stat = Ext.Stats.Get("Interrupt_AttackOfOpportunity")
local cost = stat.Cost
local conditions = stat.Conditions

-- Modify at runtime (MUST sync after)
stat.Cost = "ReactionActionPoint:1"
Ext.Stats.Sync("Interrupt_AttackOfOpportunity")
```

> **CRITICAL:** `Ext.Stats.Sync()` is mandatory after any runtime change — without it modifications are invisible.

### Osiris Events

| Event | Signature | Relevance |
|-------|-----------|----------|
| `StatusApplied` | `(obj, status, causee, storyId)` | Fires when interrupt's `Success`/`Properties` applies a status |
| `CastedSpell` | `(character, spell)` | Fires when interrupt's `UseSpell()` casts a spell |
| `EnteredCombat` | `(character, combatId)` | Interrupt availability begins |

### Interrupt-Specific Targeting Prefixes

| Prefix | Entity | Use In |
|--------|--------|--------|
| `OBSERVER_SOURCE` | The interrupt holder | `Success`, `Failure`, `Properties` |
| `OBSERVER_TARGET` | The interrupted creature | `Success`, `Failure`, `Properties` |
| `OBSERVER_OBSERVER` | Same as interrupt holder | Rare — used when the interrupt holder is also the target |
| `SWAP` | Reverses Source/Target | Same as spell functors |
