# SpellSet.txt

> **Path**: `Stats/Generated/SpellSet.txt`
> **Format**: `new spellset` + `add spell` commands
> **Packs**: GustavDev, Shared, SharedDev

## Purpose

Defines named spell sets — predefined collections of spells assigned to NPCs or debug contexts.

## Format

```
new spellset "NAME"
add spell "SPELL_ENTRY_NAME"
add spell "SPELL_ENTRY_NAME"
...
```

## Keywords

| Keyword | Purpose |
|---------|---------|
| `new spellset "NAME"` | Starts a new spell set |
| `add spell "NAME"` | Adds a spell to the set (references SpellData entry) |

## Example

```
new spellset "DEBUG_Common"
add spell "Projectile_Jump"
add spell "Shout_Dash"
add spell "Target_Shove"
add spell "Shout_Hide"
add spell "Throw_Throw"
add spell "Shout_RegainHP"
add spell "Target_KnockOut_Person"
```

## Notes

- Spell names use the `SubType_Name` convention (e.g., `Target_RangersCompanion_Bear`, `Projectile_MagicMissile`)
- The subtype prefix matches the spell's `SpellType` and source file (Spell_Target.txt, Spell_Projectile.txt, etc.)
- Spell sets are referenced by character/NPC templates to define available abilities

## Cross-References

| From | To | Via |
|------|----|----|  
| `add spell "NAME"` | SpellData entries (Spell_*.txt) | Entry name match (case-sensitive) |
| NPC/Character templates | SpellSet.txt | Set name reference |

## Caveats

- **Entry name matching**: Spell names must match SpellData entry names exactly (case-sensitive). Mismatches are silently ignored.
- **No inheritance**: Spell sets don't support `using`. To modify a set, redefine it entirely.
- **Largely debug-only**: Most vanilla spell sets are `DEBUG_*` prefixed. Player spell selection uses Progressions + SpellLists (LSX), not SpellSet.txt.
