# ValueLists.txt — Enum / ValueList Definitions

> **Source**: `Shared/Public/Shared/Stats/Generated/Structure/Base/ValueLists.txt`
> **Size**: 39,385 bytes (1,787 lines)
> **Pack**: Shared only — no other pack overrides this file

## Purpose

Defines **all enum types** (valuelists) referenced by [Modifiers.txt](Modifiers.md). When `Modifiers.txt` declares a field with type `"Ability"`, this file provides the mapping `Ability = {None:0, Strength:1, …, Charisma:6}`.

## Format

```
valuelist "ListName"
value "ValueName" : IntegerIndex
value "ValueName" : IntegerIndex
...
```

Each `valuelist` block defines a named enumeration. Values map display names to integer indices.

## Valuelist Categories

### Free-Form Types (Empty Lists — No Enum Constraint)

These appear as declarations with no values, meaning the field accepts arbitrary input of that type:

| List Name | Meaning |
|-----------|---------|
| `FixedString` | Arbitrary string |
| `ConstantInt` | Arbitrary integer |
| `ConstantFloat` | Arbitrary float |
| `Guid` | UUID string |
| `TranslatedString` | Localized string handle |
| `Requirements` | Requirement expression |
| `Conditions` | Condition expression |
| `TargetConditions` | Target condition expression |
| `RollConditions` | Roll condition expression |
| `StatsFunctors` | Functor expression (see [functors-boosts.md](../reference/functors-boosts.md)) |
| `StatusIDs` | Status ID list |
| `MemorizationRequirements` | Memorization requirement expression |
| `SurfaceCollisionFlags` | Surface collision flag expression |
| `Properties` | Property expression |

### Core D&D Enums

| List Name | Values | Notes |
|-----------|--------|-------|
| `Ability` | None(0), Strength(1), Dexterity(2), Constitution(3), Intelligence(4), Wisdom(5), Charisma(6) | Six D&D abilities |
| `Damage Type` | None(0), Slashing(1), Piercing(2), Bludgeoning(3), Acid(4), Thunder(5), Necrotic(6), Fire(7), Lightning(8), Cold(9), Psychic(10), Poison(11), Radiant(12), Force(13) | 13 damage types |
| `Death Type` | None(0), Acid(1), Chasm(2), DoT(3), Electrocution(4), Explode(5), Falling(6), Incinerate(7), KnockedDown(8), Lifetime(9), Necrotic(10), Physical(11), Psychic(12), Radiant(13), CinematicDeath(14), Cold(15), Disintegrate(16) | Death animation triggers |
| `SpellSchool` | None(0), Abjuration(1), Conjuration(2), Divination(3), Enchantment(4), Evocation(5), Illusion(6), Necromancy(7), Transmutation(8) | 8 spell schools |
| `DieType` | None(0), d4(1), d6(2), d8(3), d10(4), d12(5), d20(6), d100(7) | Dice types |
| `Rarity` | Common(0), Uncommon(1), Rare(2), VeryRare(3), Legendary(4) | Item rarity tiers |

### Equipment & Weapon Enums

| List Name | Values | Notes |
|-----------|--------|-------|
| `ArmorType` | None(0)..Plate(13) | 14 armor types: Cloth, Padded, Leather, StuddedLeather, Hide, ChainShirt, ScaleMail, BreastPlate, HalfPlate, RingMail, ChainMail, Splint, Plate |
| `Weapon Group` | SimpleMeleeWeapon(0), SimpleRangedWeapon(1), MartialMeleeWeapon(2), MartialRangedWeapon(3) | 4 weapon categories |
| `WeaponFlags` | None(0)..AddToHotbar(21) | Light, Ammunition, Finesse, Heavy, Loading, Range, Reach, Lance, Net, Thrown, Twohanded, Versatile, Melee, Dippable, Torch, NoDualWield, Magical, NeedDualWieldingBoost, NotSheathable, Unstowable, AddToHotbar |
| `Itemslot` | Helmet(0)..VanityBoots(18) | 19 equipment slots including VanityBody(17), VanityBoots(18), MusicalInstrument(16) |
| `InventoryTabs` | Auto(0)..Hidden(7) | Equipment, Consumable, Magical, Ingredient, BooksAndKeys, Misc, Hidden |
| `ProficiencyGroupFlags` | None(0)..MusicalInstrument(40) | All weapon & armor proficiency groups |
| `InstrumentType` | None(0)..Saxophone(11) | Bagpipes, Drum, Dulcimer, Flute, Lute, Lyre, Horn, Shawm, Violin, Musicbox, Saxophone |

### Spell Enums

| List Name | Values | Notes |
|-----------|--------|-------|
| `SpellFlagList` | None(0)..ChasmRecovery(58) | 59 spell flags. Key flags: HasVerbalComponent, HasSomaticComponent, IsConcentration, IsSpell, IsAttack, IsHarmful, CanDualWield |
| `SpellRequirement` | None(0)..ArrowWeapon(7) | Weapon requirements for spell casting |
| `SpellActionType` | None(0)..ImprovisedWeapon(12) | Dash, Dip, Disengage, Distract, Help, Hide, Jump, Knockout, Shove, Throw, Dismiss, ImprovisedWeapon |
| `SpellAnimationType` | None(0)..Telekinesis(8) | Dipping, Assisting, Throwing, ImprovisedWeapon, Restrain, Shoving, Jumping, Telekinesis |
| `SpellAnimationIntentType` | None(0), Aggressive(1), Peaceful(2), Action(3) | Animation intent |
| `SpellCategoryFlags` | SC_None(0)..SC_DetectThoughts(11) | Target type + intent classification |
| `SpellStyleGroup` | Intent(0), Class(1), Class_Intent(2) | Spell style grouping |
| `SpellSheathing` | Somatic(0)..WeaponSet(6) | Weapon state during casting |
| `SpellJumpType` | None(0), Jump(1), Pounce(2), Flight(3) | Jump spell variants |
| `SpellSoundMagnitude` | Normal(0), None(1), Small(2), Big(3) | Sound intensity |
| `CooldownType` | None(0)..OncePerShortRestPerItem(7) | 8 cooldown types |
| `VerbalIntent` | None(0)..Summon(7) | Damage, Healing, Buff, Debuff, Utility, Control, Summon |

### Status Enums

| List Name | Values | Notes |
|-----------|--------|-------|
| `StatusPropertyFlags` | None(0)..RemoveOnLongRest(37) | 38 status property flags. Key: Performing, InitiateCombat, IsChanneled, IsInvulnerable, LoseControl, Toggle |
| `StatusGroupFlags` | SG_None(0)..SG_Sleeping_Magical(47) | 48 status groups: conditions, debuffs, polymorphs, etc. |
| `StatusStackType` | Stack(0), Ignore(1), Overwrite(2), Deactivate(3), Variable(4), Additive(5) | Status stacking behavior |
| `StatusHealType` | None(0)..Source(6) | Vitality, PhysicalArmor, MagicArmor, AllArmor, All, Source |
| `StatusAnimationType` | None(0)..Performing10(36) | 37 animation types for statuses |
| `StillAnimPriority` | Suffocating(0)..Downed(17) | Animation priority ordering |
| `StatusSheathing` | None(0)..Sheathed(4) | Weapon state during status |
| `StatusEvent` | None(0)..OnDisarmingFinished(28) | 29 status event triggers |
| `TickType` | StartTurn(0), EndTurn(1), StartRound(2), EndRound(3) | When status ticks |
| `ManagedStatusEffectType` | Positive(0), Negative(1) | Effect polarity |

### Interrupt Enums

| List Name | Values | Notes |
|-----------|--------|-------|
| `InterruptContext` | None(0)..OnDeath(8) | When interrupts trigger |
| `InterruptContextScope` | None(0), Self(1), Nearby(2), Far(3) | Interrupt range |
| `InterruptDefaultValue` | None(0), Ask(1), Enabled(2) | Default prompt behavior |
| `InterruptFlagsList` | None(0), InterruptWhileInvisible(1) | Interrupt flags |

### Passive Enums

| List Name | Values | Notes |
|-----------|--------|-------|
| `PassiveFlags` | None(0)..DisplayBoostInTooltip(18) | 19 passive flags. Key: OncePerTurn, IsToggled, ToggledDefaultOn, MetaMagic, Highlighted, Temporary |
| `StatsFunctorContext` | None(0)..OnConsumed(44) | 45 functor trigger contexts. Key: Target, AOE, OnCast, OnEquip, OnAttack, OnDamage, OnHeal, OnStatusApply |

### Combat & Damage Enums

| List Name | Values | Notes |
|-----------|--------|-------|
| `ResistanceFlags` | None(0)..VulnerableToNonMagical(9) | Resistance, Immune, Vulnerable + Magical/NonMagical variants |
| `HitAnimationType` | Default(0)..AnimationSetOverride(8) | Physical, Electric, External, Internal, Psychic, MagicalNonDamage, None, Override |
| `AttributeFlags` | None(0)..ReallyArmor(24) | 25 item attribute flags |
| `ProjectileType` | None(0), Arrow(1), Grenade(2) | Projectile categories |
| `ProjectileDistribution` | Random(0), Normal(1), Edge(2), EdgeCenter(3) | Projectile spread pattern |
| `CinematicArenaFlags` | None(0), Ignore(1), AlwaysShow(2) | Cinematic camera behavior |
| `AuraFlags` | None(0)..DangerousForPathfinding(7) | 8 aura behavior flags |
| `LineOfSightFlags` | None(0), AddSourceHeight(1) | LoS calculation |

### Surface Enums

| List Name | Values | Notes |
|-----------|--------|-------|
| `Surface Type` | None(0)..Sentinel(75) | 76 surface types including liquids, clouds, potions |
| `Surface Change` | None(0)..UnturnHellfire(13) | Ignite, Douse, Electrify, Deelectrify, Freeze, Melt, Vaporize, Condense, DestroyWater, Clear, Daylight, TurnHellfire, UnturnHellfire |

### UI & Visual Enums

| List Name | Values | Notes |
|-----------|--------|-------|
| `FormatStringColor` | White(0)..Healing(34), Charm(35) | 36 text colors for UI display |
| `CursorMode` | None(0)..Listen_Warning(48) | 49 cursor types |
| `LEDEffectType` | NONE(0)..Drunk(24) | 25 LED peripheral effects |

### Miscellaneous Enums

| List Name | Values | Notes |
|-----------|--------|-------|
| `YesNo` | No(0), Yes(1) | Boolean |
| `Handedness` | Any(0), 1(1), 2(2) | Weapon handedness |
| `ObjectSize` | Tiny(0)..Gargantuan(5) | D&D size categories |
| `StepsType` | Bare(0)..Clawed(6) | Footstep sound types |
| `Skill` | None(0)..Sulfurology(42) | 43 skills (D&D + leftover DOS2) |
| `HealValueType` | FixedValue(0)..DamagePercentage(5) | Heal calculation methods |
| `Progression Type` | Level(0), ChallengeRating(1) | Progression scaling |
| `Qualifier` | None(0), 0..10 (1-11) | Numeric qualifier (0–10) |
| `BigQualifier` | None(0), 1..100 (1-100) | Large numeric qualifier (1–100) |
| `PreciseQualifier` | None(0), 0.0..10.0 in 0.1 steps | Precise float qualifier |
| `Penalty PreciseQualifier` | None(0), -10.0..10.0 in 0.1 steps | Penalty float qualifier |
| `Penalty Qualifier` | None(0), -10..10 + 100 | Penalty integer qualifier |
| `SoundVocalType` | NONE(0)..MAX(32) | 33 vocal sound types |
| `TagCategory` | None(0)..Voice(8) | Code, Dialog, Gender, Origin, Profession, Race, Story, Voice |
| `FlagType` | Invalid(0)..Dialog(6) | Local, User, Party, Character, Global, Dialog |
| `Act` | 1(0) | Single act value |
| `ItemUseTypes` | None(0)..Consumable(7) | Item use categories |
| `IngredientType` | None(0)..Property(3) | Object, Category, Property |
| `IngredientTransformType` | None(0)..Dye(4) | Consume, Transform, Poison, Dye |
| `IngredientCombineType` | None(0), Base(1), Additive(2) | Ingredient combination method |
| `AlchemyCombinationType` | None(0), IngredientsToExtract(1), ExtractToSolution(2) | Alchemy pipeline |
| `WeaponSet` | Melee(0), Ranged(1) | Weapon set toggle |
| `Relation` | Ally(0), Neutral(1), Enemy(2), Persistent Neutral(3) | Faction relationship |
| `MaterialType` | None(0), Overlay(1), FadingOverlay(2), Replacement(3) | Material application type |
| `RestErrorFlags` | None(0)..DownedOrDead(7) | Rest blocking conditions |
| `Tension` | any(0), low(1), high(2) | Combat tension level |
| `AbilityFlags` | None(0), Strength(1)..Charisma(6) | Same as Ability but flag variant |

### Crime/Disturbance Enums

| List Name | Values | Notes |
|-----------|--------|-------|
| `DisturbanceMergeConditions` | SameNonNullVictimOrCommonEvidence(0)..Never(3) | Crime merge rules |
| `DisturbanceInvestigationKind` | InvestigateInterrogate(0)..ForceInvestigateCriminalReact(10) | 11 investigation behaviors |
| `DisturbanceYesNoIgnoreStats` | No(0), Yes(1), YesIgnoreStats(2) | Extended boolean for disturbance |
| `DisturbanceDialogueCapability` | Excl_CanTalk(0)..Incl_OtherCannotTalk(3) | Dialog capability filtering |

---

## Cross-References

| From | To | Via |
|------|----|----|
| [Modifiers.txt](Modifiers.md) field types | ValueLists.txt | Enum name match (e.g., `ArmorType`, `Damage Type`) |
| SpellData `SpellFlags` field | `SpellFlagList` enum | Semicolon-separated flag values |
| SpellData `DamageType` field | `Damage Type` enum | Single enum value |
| StatusData `StatusGroups` field | `StatusGroupFlags` enum | Semicolon-separated group flags |
| All stats type field references | Respective enum | Values must match enum member names exactly |

## Caveats

- **Enum member names are case-sensitive**: `"Resistant"` ≠ `"resistant"`. Always match the exact case from the enum definition.
- **Numeric values are internal IDs**: The `(N)` after each member name is the engine's internal integer. Stats TXT files use the **string name**, not the number.
- **Not all enums are flags**: Some enums (like `Ability`, `Damage Type`) accept a single value. Others (like `SpellFlagList`, `StatusGroupFlags`) accept semicolon-separated combinations.
