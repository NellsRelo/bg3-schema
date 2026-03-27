# Node: `FixedHotBarSlot`

> **Region**: [FixedHotBarSlots](_REGION.md)
> **Folder**: `FixedHotBarSlots/`
> **Vanilla entries**: 11 (Shared)

---

## Attributes

| Attribute | Type | Frequency | Examples | Notes |
|-----------|------|-----------|----------|-------|
| `UUID` | guid | 11/11 | `4e6af047-...` | Primary key |
| `SpellId` | FixedString | 11/11 | `Target_MainHandAttack`, `Projectile_Jump`, `Throw_Throw` | Spell/action string ID |
| `SlotIndex` | uint32 | 11/11 | `0`, `1`, `11` | Position in the hotbar |
| `HotBarController` | uint8 | 11/11 | `1` | Controller type (all entries use `1`) |
| `HotBarType` | uint8 | 11/11 | `0`, `1` | 0=Actions, 1=Spells |

## Child Nodes

*(None in vanilla data)*

## Patterns of Use

- Defines the default hotbar layout for new characters.
- Includes core actions: `Target_MainHandAttack`, `Projectile_Jump`, `Throw_Throw`, `Shout_Dash_New`, etc.

## Cross-References

| From | To | Via |
|------|----|-----|
| FixedHotBarSlot | Spells (stats) | `SpellId` |

## Caveats & Gotchas

- `SpellId` references stat-entry spell names, not UUIDs.

## Similarities to Other Nodes

*(None)*
