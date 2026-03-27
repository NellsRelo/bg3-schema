# Node: `LightbarHaptics`

> **Region**: [LightbarHaptics](_REGION.md)
> **Folder**: `Haptics/`
> **Source**: `Shared/Public/SharedDev/Haptics/LightbarHaptics.lsx`
> **Total Nodes**: ~56 (SharedDev only)

---

## Attributes

| Attribute | Type | Frequency | Examples | Notes |
|-----------|------|-----------|----------|-------|
| `UUID` | guid | x56 | `d36d91a8-e0a1-432b-a21d-dc8172a4d9f8` | Primary key |
| `Name` | LSString | x56 | `Spell_SlashingDamage`, `Spell_PiercingDamage`, `Spell_BludgeoningDamage` | Haptic effect name |
| `Lightbar_Colour` | LSString | x56 | `#FFFDAD5A`, `#FFFDAE5A` | DualSense lightbar color (hex ARGB) |
| `PriorityOrder` | int32 | x56 | `1` | Priority for overlapping effects |
| `CastSoundEvent` | FixedString | x20 | `Ds_Spell_Cast_Slashing`, `Ds_Spell_Cast_Piercing` | Wwise event on cast (sparse) |
| `LoopSoundEvent` | FixedString | x20 | `Ds_Spell_Loop_Slashing`, `Ds_Spell_Loop_Piercing` | Wwise loop event (sparse) |
| `StatusGroup` | FixedString | x36 | `SG_Condition`, `SG_Blinded`, `SG_Cursed` | Status group trigger (sparse) |
| `DamageType` | uint8 | x13 | `1`, `2`, `3` | Damage type enum (sparse) |
| `SpellIntent` | uint8 | x7 | `1`, `2`, `3` | Spell intent enum (sparse) |

## Child Nodes

None.

## Patterns of Use

- Defines PS5 DualSense lightbar color + haptic feedback mappings for game events
- Maps spell damage types, status effects, and spell intents to lightbar colors
- `CastSoundEvent`/`LoopSoundEvent` for DualSense speaker audio (sparse — 20/56)
- `StatusGroup` triggers lightbar color on status application (36/56)
- `DamageType` for damage-specific effects (13/56)
- `SpellIntent` for intent-based colors (7/56)

## Caveats & Gotchas

- Only in SharedDev pack
- Many attributes are sparse — each node uses a different subset
- `Lightbar_Colour` is `#AARRGGBB` format (ARGB)

## Similarities to Other Nodes

Companion to `LightbarSounds` (not found in vanilla data — may share same haptics system).
