# BG3 Stats: StatsFunctorContext Reference

> Which entity is `context.Target` and `context.Source` in each StatsFunctorContext, with behavioral notes.
> Used in Passive `StatsFunctors` and `StatsFunctorConditions` fields.

---

## Key Concepts

- **Passive owner** = the entity that has the passive with the StatsFunctorContext
- An asterisk (*) on `context.Source` or `context.Target` indicates the entity may differ between `StatsFunctorConditions` and `StatsFunctors` — see Notes
- Some contexts behave differently in `StatsFunctorConditions` vs `StatsFunctors` fields

---

## Context Reference

### OnCast
- **Trigger:** Passive owner casts a spell
- `context.Target` = Passive owner
- `context.Source` = Passive owner
- **Notes:** Happens before `OnAttack`

### OnCastResolved
- **Trigger:** Passive owner finishes casting a spell
- `context.Target` = Passive owner
- **Notes:** Happens after `OnCast`, `OnAttack`

### OnProjectileExploded
- **Trigger:** Passive owner's projectile explodes
- `context.Target` = Passive owner
- **Notes:** Fires when the projectile lands.

### OnAttack
- **Trigger:** Passive owner attacks
- `context.Target` = Target of the attack
- `context.Source` = Passive owner
- **Notes:** Assume that every spell counts as an attack.

### OnAttacked
- **Trigger:** Passive owner is attacked
- `context.Target` = Passive owner
- `context.Source` = Source of the attack
- **Notes:** Assume that every spell counts as an attack.

### OnDamage
- **Trigger:** Passive owner deals damage
- `context.Target` = Target of the damage
- `context.Source` = Passive owner
- **Notes:** Can loop — use conditions to guard. `DealDamage` has an `IgnoreOnDamage` argument to prevent re-triggering.

### OnDamaged
- **Trigger:** Passive owner is damaged
- `context.Target` = Passive owner
- `context.Source` = Source of the damage
- **Notes:** Can loop — use conditions to guard. `DealDamage` has an `IgnoreOnDamage` argument to prevent re-triggering.

### OnDamagePrevented
- **Trigger:** Target prevents all damage done by passive owner
- `context.Target` = Target of the damage
- `context.Source` = Passive owner
- **Notes:** Can check `DeathType` for damage type.

### OnDamagedPrevented
- **Trigger:** Damage is prevented on passive owner
- `context.Target` = Passive owner
- `context.Source` = Damage source
- **Notes:** Can check `DeathType` for damage type.

### OnStatusApply
- **Trigger:** Passive owner applies a status
- `context.Target` = Receiver of the status
- `context.Source` = Passive owner
- **Notes:** Can loop — use conditions for specific statuses. Includes 0-duration statuses.

### OnStatusApplied
- **Trigger:** Status applied to passive owner
- `context.Target` = Passive owner
- `context.Source` = Source of the status
- **Notes:** Can loop — use conditions for specific statuses. Engine applies background statuses (e.g., `FLANKED`, `INSURFACE`).

### OnStatusRemove
- **Trigger:** Passive owner removes a status
- `context.Target` = Target status was removed from
- `context.Source` = Passive owner
- **Notes:** Does not trigger on timeout or concentration breaking.

### OnStatusRemoved
- **Trigger:** Status removed from passive owner
- `context.Target` = Passive owner
- `context.Source`* = Entity that removed the status
- **Notes:** No `Source` on timeout or concentration breaking. Engine background statuses (e.g., `FLANKED`, `INSURFACE`) may trigger this.

### OnHeal
- **Trigger:** Passive owner heals something
- `context.Target` = Heal target
- `context.Source` = Passive owner
- **Notes:** Healing must come from a spell or status.

### OnHealed
- **Trigger:** Passive owner is healed
- `context.Target` = Passive owner
- `context.Source` = Heal source
- **Notes:** Healing must come from a spell or status.

### OnAbilityCheck
- **Trigger:** Passive owner rolls a SkillCheck or AbilityCheck
- `context.Target` = Target of the check
- `context.Source` = Passive owner*
- **Notes:** Passive owner is `context.Target` in `Conditions`.

### OnActionResourcesChanged
- **Trigger:** Passive owner spends or gains a resource
- `context.Target` = Passive owner
- `context.Source` = Passive owner*
- **Notes:** `context.Source` in `StatsFunctorConditions`, either one in `StatsFunctors`. Fires once if several resources change simultaneously. Turn-based mode required for Action and Movement resources. Moving rapidly can trigger this.

### OnMovedDistance
- **Trigger:** Passive owner moves
- `context.Target` = Passive owner*
- `context.Source` = Passive owner
- **Notes:** `context.Source` in `StatsFunctorConditions`, either in `StatsFunctors`. Use `SELF` targeting for functors like `DealDamage` and `ApplyStatus`. Not triggered by jump and rush spells.

### OnPush
- **Trigger:** Passive owner pushes an entity
- `context.Target` = Push target
- `context.Source` = Passive owner
- **Notes:** Triggers on landing.

### OnPushed
- **Trigger:** Passive owner is pushed
- `context.Target` = Passive owner
- `context.Source` = Push source
- **Notes:** Triggers on landing.

### OnSurfaceEnter
- **Trigger:** Passive owner enters a surface
- `context.Target` = Passive owner
- `context.Source` = Passive owner*
- **Notes:** `context.Source` in `StatsFunctorConditions`, either in `StatsFunctors`. Does not trigger when moving from one surface to another.

### OnTurn
- **Trigger:** Start of passive owner's turn
- `context.Target` = Passive owner
- `context.Source` = Passive owner
- **Notes:** Turn-based mode required. Use a status for real-time behavior.

### OnRound
- **Trigger:** Start of a new round
- `context.Target` = Passive owner
- `context.Source` = Passive owner
- **Notes:** Turn-based mode required.

### OnCombatStarted
- **Trigger:** Start of combat
- `context.Target` = Passive owner
- `context.Source` = Passive owner
- **Notes:** Does not trigger when joining existing combat.

### OnCombatEnded
- **Trigger:** End of combat
- `context.Target` = Passive owner
- `context.Source` = Passive owner*
- **Notes:** `context.Source` in `StatsFunctorConditions`, either in `StatsFunctors`.

### OnInventoryChanged
- **Trigger:** Item is added to or rearranged inside passive owner
- `context.Target` = Passive owner
- `context.Source` = Passive owner*
- **Notes:** `context.Source` in `StatsFunctorConditions`, either in `StatsFunctors`.

### OnEquip
- **Trigger:** Passive owner equips or unequips an item
- `context.Target` = Item
- `context.Source` = Passive owner
- **Notes:** Highly recommend using Osiris for applying/removing item statuses instead. Conditions for `ApplyStatus` are ignored in `StatsFunctors`. Works for `ApplyStatus(SELF..)`.

### OnConsumed
- **Trigger:** Passive owner consumes an item
- `context.Target` = Consumed item
- `context.Source` = Passive owner
- **Notes:** Can check tags on the item.

### OnProficiencyChange
- **Trigger:** Passive owner gains or loses proficiency
- `context.Target` = Passive owner
- **Notes:** `ApplyStatus` will not have a Source.

### OnObscurityChanged
- **Trigger:** Passive owner's obscurity changes
- `context.Target` = Passive owner
- `context.Source` = Passive owner
- **Notes:** `ApplyStatus` will not have a Source.

### OnShortRest
- **Trigger:** On short rest
- `context.Target` = Passive owner
- `context.Source` = Passive owner*
- **Notes:** `context.Source` in `StatsFunctorConditions`, either in `StatsFunctors`.

### OnLongRest
- **Trigger:** On long rest
- `context.Target` = Passive owner
- `context.Source` = Passive owner*
- **Notes:** `context.Source` in `StatsFunctorConditions`, either in `StatsFunctors`.

### OnCreate
- **Trigger:** The passive or another passive is added
- `context.Target` = Passive owner
- `context.Source` = Passive owner*
- **Notes:** `context.Source` in `Conditions`, either in `StatsFunctors`. Triggers when a toggle passive is added, not when toggled on. Can loop if applying a status that has a passive.

### OnInterruptUsed
- **Trigger:** (details TBD)

---

## Observer Contexts

These contexts involve a third-party observer entity and have different entity assignments in `StatsFunctorConditions` vs `StatsFunctors`.

### OnEntityAttackedWithinMeleeRange
- **Trigger:** Entity is attacked within melee range of passive owner
- **In `StatsFunctorConditions`:**
  - `context.Target` = Target of the attack
  - `context.Source` = Source of the attack
  - `context.Observer` = Passive owner
- **In `StatsFunctors`:**
  - `context.Target` = Target of the attack
  - `context.Source` = Passive owner
- **Notes:** Passive owner cannot be the target or attacker. `UseSpell()` and `UseAttack()` work. `DealDamage()` and `ApplyStatus()` are not compatible. Combat required.

### OnEntityAttackingWithinMeleeRange
- **Trigger:** Entity is attacking within melee range of passive owner
- **In `StatsFunctorConditions`:**
  - `context.Target` = Target of the attack
  - `context.Source` = Source of the attack
  - `context.Observer` = Passive owner
- **In `StatsFunctors`:**
  - `context.Target` = Source of the attack
  - `context.Source` = Passive owner
- **Notes:** Passive owner cannot be the target or attacker. `UseSpell()` and `UseAttack()` work. `DealDamage()` and `ApplyStatus()` are not compatible. Combat required.

### OnLeaveAttackRange
- **Trigger:** Entity leaves attack range of passive owner
- `context.Target` = Entity (the one leaving)
- `context.Source` = Passive owner
- **Notes:** Entity must be the one moving. Melee weapon set must be active. Combat required. Displays the same red arrow as Opportunity Attack.

### OnEnterAttackRange
- **Trigger:** Entity enters attack range of passive owner
- `context.Target` = Entity (the one entering)
- `context.Source` = Passive owner
- **Notes:** Entity must be the one moving. Melee weapon set must be active. Combat required. Displays the same red arrow as Opportunity Attack.

---

## Quick Lookup Table

| Context | Target | Source | Looping Risk | Combat Only |
|---------|--------|--------|:---:|:---:|
| OnCast | Self | Self | | |
| OnCastResolved | Self | — | | |
| OnProjectileExploded | Self | — | | |
| OnAttack | Attack target | Self | | |
| OnAttacked | Self | Attacker | | |
| OnDamage | Damage target | Self | Yes | |
| OnDamaged | Self | Damage source | Yes | |
| OnDamagePrevented | Damage target | Self | | |
| OnDamagedPrevented | Self | Damage source | | |
| OnStatusApply | Status receiver | Self | Yes | |
| OnStatusApplied | Self | Status source | Yes | |
| OnStatusRemove | Status target | Self | | |
| OnStatusRemoved | Self | Remover* | | |
| OnHeal | Heal target | Self | | |
| OnHealed | Self | Healer | | |
| OnAbilityCheck | Check target | Self* | | |
| OnActionResourcesChanged | Self | Self* | | |
| OnMovedDistance | Self* | Self | | |
| OnPush | Push target | Self | | |
| OnPushed | Self | Push source | | |
| OnSurfaceEnter | Self | Self* | | |
| OnTurn | Self | Self | | Yes |
| OnRound | Self | Self | | Yes |
| OnCombatStarted | Self | Self | | Yes |
| OnCombatEnded | Self | Self* | | |
| OnInventoryChanged | Self | Self* | | |
| OnEquip | Item | Self | | |
| OnConsumed | Item | Self | | |
| OnProficiencyChange | Self | — | | |
| OnObscurityChanged | Self | Self | | |
| OnShortRest | Self | Self* | | |
| OnLongRest | Self | Self* | | |
| OnCreate | Self | Self* | Yes | |
| OnEntityAttackedWithinMeleeRange | Attack target† | Self† | | Yes |
| OnEntityAttackingWithinMeleeRange | Attacker† | Self† | | Yes |
| OnLeaveAttackRange | Leaving entity | Self | | Yes |
| OnEnterAttackRange | Entering entity | Self | | Yes |

*\* = may differ between `StatsFunctorConditions` and `StatsFunctors` (see details above)*
*† = differs between `StatsFunctorConditions` and `StatsFunctors` (see Observer Contexts)*

---

## Common Pitfalls

- **OnDamage/OnDamaged loops**: `DealDamage` in an `OnDamage` context re-triggers itself infinitely. Use `IgnoreOnDamage=true` (arg 8): `DealDamage(1d6,Fire,,0,,true)`.
- **OnStatusApply/Applied loops**: Applying a status in an `OnStatusApplied` context can re-trigger when the engine applies background statuses (`FLANKED`, `INSURFACE`). Guard with specific status checks in Conditions.
- **OnCreate fires on passive add**: `OnCreate` triggers when the passive is added to the character, NOT when toggled on for toggle passives.
- **OnEquip + ApplyStatus**: The `OnEquip` context ignores `ApplyStatus` conditions. Use `StatusOnEquip` on the equipment entry or Osiris `Equipped` events instead.
- **Observer contexts swap Source/Target**: `OnEntityAttackedWithinMeleeRange` and `OnEntityAttackingWithinMeleeRange` swap `context.Source` between `StatsFunctorConditions` (= the attacker) and `StatsFunctors` (= the passive owner). This is the most common silent error in interrupt/passive design.
- **Combat-only contexts**: `OnTurn`, `OnRound`, `OnCombatStarted`, `OnLeaveAttackRange`, `OnEnterAttackRange`, and the Observer contexts only fire during turn-based combat. For real-time equivalents, use status-based approaches.
- **OnStatusRemoved has no Source on timeout**: When a status expires naturally or concentration breaks, `context.Source` is unset. Don't rely on Source for cleanup logic.
