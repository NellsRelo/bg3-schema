# Node: `LightbarSounds`

> **Region**: [LightbarSounds](_REGION.md)
> **Source**: `Shared/Public/SharedDev/Haptics/LightbarSounds.lsx`

---

## Attributes

| Attribute | Type | Frequency | Examples | Notes |
|-----------|------|-----------|----------|-------|
| `SpellID` | FixedString | always | `Fireball` | Spell identifier triggering lightbar sound |
| `CastSoundEvent` | FixedString | always | *(FMOD event name)* | Sound event for spell cast |
| `LoopSoundEvent` | FixedString | always | *(FMOD event name)* | Looping sound event |
| `UUID` | guid | always | — | Primary key |

## Child Nodes

*(None)*

## Vanilla Scope

| Pack | Nodes |
|------|-------|
| SharedDev | 1 |

Single entry mapping DualSense lightbar sound feedback to the Fireball spell.
Companion to [LightbarHaptics](../LightbarHaptics/LightbarHaptics.md) which controls lightbar *colour*.

## Cross-References

| From | To | Via |
|------|----|-----|
| — | — | — |

## Caveats & Gotchas

*(To be documented)*

## Similarities to Other Nodes

*(To be documented)*
