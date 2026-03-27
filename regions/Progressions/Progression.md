# Node: `Progression`

> **Region**: [Progressions](_REGION.md)
> **Folder**: `Progressions/`

---

## Attributes

| Attribute | Type | Frequency | Examples | Notes |
|-----------|------|-----------|----------|-------|
| `UUID` | guid | always | — | Primary key |
| `Name` | LSString | always | `Barbarian`, `BerserkerPath`, `Bard`, `LoreCollege` | Class/subclass identifier |
| `Level` | uint8 | always | `1`–`12` | Character level for this row |
| `ProgressionType` | uint8 | always | `0` (class), `1` (subclass), `2` (race) | Row type |
| `TableUUID` | guid | always | links to ClassDescription.ProgressionTableUUID | Which class table |
| `Boosts` | LSString | common | `ProficiencyBonus(SavingThrow,Strength);Proficiency(LightArmor)` | **Semicolon-delimited** boosts granted |
| `PassivesAdded` | LSString | common | `RageUnlock;UnarmouredDefence_Barbarian` | **Semicolon-delimited** passives granted |
| `PassivesRemoved` | LSString | rare | `RageUnlock` | **Semicolon-delimited** passives removed at this level |
| `Selectors` | LSString | common | `SelectSkills(UUID,2);AddSpells(UUID)` | **Semicolon-delimited** selector function calls |
| `AllowImprovement` | bool | rare | `true` | Level 4/8/12 ASI flag |

## Boosts Format

Semicolon-delimited boost expressions:

| Boost | Syntax | Example |
|-------|--------|---------|
| `ActionResource` | `ActionResource(Name, Amount, Offset)` | `ActionResource(Rage,2,0)` |
| `ProficiencyBonus` | `ProficiencyBonus(SavingThrow, Ability)` | `ProficiencyBonus(SavingThrow,Strength)` |
| `Proficiency` | `Proficiency(ArmorType\|WeaponType)` | `Proficiency(LightArmor)` |
| `Attribute` | `Attribute(AttrName)` | `Attribute(UseMusicalInstrumentForCasting)` |

> For the complete boost reference, see [stats/reference/functors-boosts.md](../../stats/reference/functors-boosts.md).

## Selectors Format

Semicolon-delimited selector function calls. **Parameter order is CRITICAL** — wrong order causes silent failure.

| Selector | Full Syntax | Purpose |
|----------|------------|---------|
| `AddSpells` | `AddSpells(SpellListUUID, [SelectorId], [CastingAbility], [ActionResourceUUID], [PrepareType], [CooldownType])` | Auto-learn **all** spells from a SpellList |
| `SelectSpells` | `SelectSpells(SpellListUUID, Amount, SwapAmount, [SelectorId], [CastingAbility], [ActionResourceUUID], [PrepareType], [CooldownType])` | Player **chooses N** spells from a SpellList |
| `SelectSkills` | `SelectSkills(SkillListUUID, Amount, [SelectorId])` | Choose N skills from a SkillList |
| `SelectSkillsExpertise` | `SelectSkillsExpertise(SkillListUUID, Amount, [SelectorId], [LimitToProficiency])` | Choose N expertise skills |
| `SelectPassives` | `SelectPassives(PassiveListUUID, [Amount], [SelectorId])` | Choose N passives from a PassiveList |
| `ReplacePassives` | `ReplacePassives(PassiveListUUID, [AmountToSwap], [SelectorId])` | Swap existing passives for new ones |
| `SelectAbilities` | `SelectAbilities(AbilityListUUID, Amount, AbilityAmount, [SelectorId])` | Choose N abilities with bonus |
| `SelectAbilityBonus` | `SelectAbilityBonus(AbilityListUUID, [BonusType], SelectionAmount, [Amounts])` | ASI-style ability bonus selection |
| `SelectEquipment` | `SelectEquipment(EquipmentListUUID, Amount, [SelectorId])` | Choose starting equipment |

### AddSpells vs SelectSpells

This distinction is a **common source of modding bugs**:
- **`AddSpells`** — Automatically learns ALL spells in the referenced SpellList. No player choice.
- **`SelectSpells`** — Presents a picker UI for the player to choose `Amount` spells from the list. `SwapAmount` allows swapping previously learned spells on level-up (set `0` to disable).

### Selector Parameter Details

- **SelectorId** — String identifier used by [ProgressionDescription](../ProgressionDescriptions/ProgressionDescription.md) to match UI labels (e.g., `"FightingStyle"`, `"Maneuvers"`, `"BardInstrument"`).
- **CastingAbility** — Overrides the class's default spellcasting ability for these spells (e.g., `"Intelligence"` for Eldritch Knight on a Fighter).
- **ActionResourceUUID** — Overrides the resource consumed when casting (links to [ActionResourceDefinition](../ActionResourceDefinitions/ActionResourceDefinition.md)).
- **PrepareType** / **CooldownType** — Control spell preparation and cooldown behavior.
- **LimitToProficiency** — Boolean; when `true`, limits expertise selection to skills the character is already proficient in.
- **BonusType** — Default `"AbilityBonus"`; controls the type of bonus granted by SelectAbilityBonus.
- **Amounts** — Comma-separated int list for SelectAbilityBonus selection caps (e.g., `1` means max +1 per ability per selection).

## Child Nodes

### SubClasses

Optional child — lists available subclass choices at the subclass selection level.

```xml
<children>
  <node id="SubClasses">
    <children>
      <node id="SubClass">
        <attribute id="Object" type="guid" value="..." />
      </node>
    </children>
  </node>
</children>
```

| Node | Attribute | Type | Notes |
|------|-----------|------|-------|
| SubClasses | — | container | Wrapper node |
| SubClass | `Object` | guid | ClassDescription UUID of a subclass |

## Patterns of Use

### Level-Up Feature Table

Each Progression entry represents **one level of one class**:
- Level 1 Barbarian: grants proficiencies, Rage, Unarmoured Defence
- Level 3 Barbarian: SubClasses child with 3 subclass options
- Level 4 Barbarian: `AllowImprovement=true` for ASI/Feat

### Class vs Subclass Rows

- `ProgressionType=0` ? class rows (appear for all characters of that class)
- `ProgressionType=1` ? subclass rows (only activate after subclass selection)
- `ProgressionType=2` ? race rows (granted by racial progression table, linked via Race.ProgressionTableUUID)
- Both class and subclass share the same `TableUUID` — the engine combines them by level

## Cross-References

| From | To | Via |
|------|----|-----|
| Progression.TableUUID | [ClassDescription](../ClassDescriptions/ClassDescription.md) | ClassDescription.ProgressionTableUUID |
| Selector GUIDs | [SpellList](../SpellLists/SpellList.md) | SpellList.UUID |
| Selector GUIDs | [PassiveList](../PassiveLists/PassiveList.md) | PassiveList.UUID |
| Selector GUIDs | [SkillList](../SkillLists/SkillList.md) | SkillList.UUID |
| SubClass.Object | [ClassDescription](../ClassDescriptions/ClassDescription.md) | ClassDescription.UUID |
| [Race](../Races/Race.md).ProgressionTableUUID | Progression.TableUUID | Racial progression features |

## Caveats & Gotchas

- **Delimiter is SEMICOLONS** for Boosts, PassivesAdded, PassivesRemoved, and Selectors fields.
- **PassivesRemoved** — Use sparingly. Only removes passives granted by earlier levels of the same class.
- **AllowImprovement** — Only appears on ASI levels (4, 8, 12). Feat selection is handled by the engine, not by a Selector.
- **Selector UUID arguments** — Must match a list UUID (SpellList, PassiveList, etc.), not a spell/passive name.
- **Name field** can differ from ClassDescription.Name — e.g., progression `Name="Barbarian"` at Level 1 vs `Name="BerserkerPath"` subclass rows.
- **UUID vs TableUUID — #1 confusion point**: Every Progression row has a unique `UUID` (one per level), but shares `TableUUID` with all rows of the same class/subclass. `ClassDescription.ProgressionTableUUID` MUST exactly match `Progression.TableUUID` — a mismatch causes **silent failure** (class features never appear in-game).
- **PassivesAdded references entry NAMES, not UUIDs** — These are case-sensitive string matches against `Passive.txt` entry names. Typos cause silent failure with no error message.
- **Selector parameter order is CRITICAL** — Wrong order = silent failure. See Selectors Format section above.
- **Level cap**: Vanilla only goes to Level 12. Entries beyond Level 12 are mod-only.
- **Authoring scale**: A class with 3 subclasses requires ~48 Progression entries (12 levels × 1 base + 12 × 3 subclasses). Each must have a unique UUID, share the correct TableUUID, and have corresponding ProgressionDescription entries.

## Scripting & Runtime Notes

- **Script Extender** can modify Progression data at runtime via `Ext.Stats` — useful for compatibility patches that add spells/passives to existing progressions.
- **Osiris events**: `LeveledUp(character, newLevel)` fires after progression features are applied. Mods can hook this for post-level-up logic.
- **Khonsu conditions** can reference progression state via `HasClass(className, level)`, `HasSubClass(subclassName)` in custom condition functions used by passives and interrupts.

## Boosts DSL Reference

Boosts are a **mini-DSL** embedded in the `Boosts` field. Semicolon-delimited, positional parameters, no spaces around delimiters.

### Common Boost Functions

| Boost | Syntax | Example |
|-------|--------|---------|
| `ActionResource` | `ActionResource(Name, Amount, Level)` | `ActionResource(Rage,2,0)` — grants 2 Rage charges |
| `ProficiencyBonus` | `ProficiencyBonus(Type, Ability)` | `ProficiencyBonus(SavingThrow,Strength)` |
| `Proficiency` | `Proficiency(Category)` | `Proficiency(LightArmor)`, `Proficiency(MartialWeapons)` |
| `Ability` | `Ability(Name, Modifier)` | `Ability(Strength,1)` — +1 STR |
| `Advantage` | `Advantage(Type)` | `Advantage(SavingThrow)` |
| `Resistance` | `Resistance(DamageType, Level)` | `Resistance(Fire,Resistant)` |
| `UnlockSpell` | `UnlockSpell(SpellName)` | `UnlockSpell(Shout_Rage)` — name-based, NOT UUID |
| `Tag` | `Tag(TagUUID)` | `Tag(d4f8d414-...)` — assigns a Tag to the entity |
| `Attribute` | `Attribute(AttrName)` | `Attribute(UseMusicalInstrumentForCasting)` |
| `MovementSpeed` | `MovementSpeed(Amount)` | `MovementSpeed(10)` — +10 feet |
| `StatusImmunity` | `StatusImmunity(StatusName)` | `StatusImmunity(FRIGHTENED)` |
| `Immunity` | `Immunity(ConditionName)` | `Immunity(Poisoned)` |

### Boost Formatting Rules

1. **Semicolon-delimited, NO spaces**: `"Func1;Func2;Func3"` not `"Func1 ; Func2"`
2. **Parameters are positional** — `Ability(Strength,1)` not `Ability(amount=1)`
3. **Typo = silent failure** — Wrong functor name or parameter count is silently ignored, no error
4. **Cross-format references**: `UnlockSpell()` uses Stats entry names (LSX?TXT); `ActionResource()` uses [ActionResourceDefinition](../ActionResourceDefinitions/ActionResourceDefinition.md) Name field; `Tag()` uses Tag UUIDs

> For the full functor/boost catalog, see [stats/reference/functors-boosts.md](../../stats/reference/functors-boosts.md).

## Similarities to Other Nodes

- [Feat](../Feats/Feat.md) also uses `Selectors` with the same function syntax
- [Feat](../Feats/Feat.md) also has `PassivesAdded` with semicolon delimiters
- Both Progression and Feat feed into the same engine systems for granting features
