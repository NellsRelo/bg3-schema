# CriticalHitTypeData

> **Type identifier**: `CriticalHitTypeData`
> **Source file**: `Stats/Generated/Data/CriticalHitTypes.txt`
> **Modifier definition**: [Modifiers.md](../formats/Modifiers.md#criticalhittypedata) (13 fields)

## Overview

Maps each damage type to a VFX UUID for critical hit visual effects. The simplest stat type — just 13 Guid fields, one per damage type. Vanilla BG3 defines exactly **one entry** (`Default`) with no `using` inheritance.

## Entry Format

```
new entry "Default"
type "CriticalHitTypeData"
data "AcidFX" "7d815feb-075b-4c56-a9bb-a55c24a3e0c8"
data "BludgeoningFX" "54cee685-7ba1-4ab4-96b8-f5b2323027a3"
data "ColdFX" "fbf84ffe-13e0-4cdc-90f3-eed60846148d"
data "FireFX" "23ebafcb-e11c-4f9a-a4b2-e10396ea11cc"
data "ForceFX" "38e81436-b403-4c8b-abe3-616e5600016e"
data "LightningFX" "1ba77ac8-14d4-4ffd-a566-4bf1ad096a80"
data "NecroticFX" "366b5ab6-8280-44fa-84b0-56ef89216d08"
data "PiercingFX" "54cee685-7ba1-4ab4-96b8-f5b2323027a3"
data "PoisonFX" "168df269-f2d3-4cf7-8e79-113b146d9bb3"
data "PsychicFX" "9ef115db-4a1d-4846-b286-3364cd5fdc28"
data "RadiantFX" "cad6a0a7-08e1-45eb-85bc-5ea35fa34683"
data "SlashingFX" "54cee685-7ba1-4ab4-96b8-f5b2323027a3"
data "ThunderFX" "89dc7308-3fae-44e3-8333-d8307efec4a7"
```

## Form Reference — All Fields

> Complete field table for form/editor construction. 13 fields defined in [Modifiers.md](../formats/Modifiers.md#criticalhittypedata). ✓ = observed in vanilla data.

| Field | Type | Observed |
|-------|------|:--------:|
| `AcidFX` | Guid | ✓ |
| `BludgeoningFX` | Guid | ✓ |
| `ColdFX` | Guid | ✓ |
| `FireFX` | Guid | ✓ |
| `ForceFX` | Guid | ✓ |
| `LightningFX` | Guid | ✓ |
| `NecroticFX` | Guid | ✓ |
| `PiercingFX` | Guid | ✓ |
| `PoisonFX` | Guid | ✓ |
| `PsychicFX` | Guid | ✓ |
| `RadiantFX` | Guid | ✓ |
| `SlashingFX` | Guid | ✓ |
| `ThunderFX` | Guid | ✓ |

### Boost Fields & Observed Boosts

None — CriticalHitTypeData does not have boost-accepting fields.

### Functor Fields & Observed Functors

None — CriticalHitTypeData does not have functor-accepting fields.

---

## Complete Field Reference

All 13 fields are `Guid` type — UUIDs referencing VFX resources played on critical hits.

| Field | Damage Type | Vanilla UUID | Notes |
|-------|-------------|-------------|-------|
| `AcidFX` | Acid | `7d815feb-075b-4c56-a9bb-a55c24a3e0c8` | Unique VFX |
| `BludgeoningFX` | Bludgeoning | `54cee685-7ba1-4ab4-96b8-f5b2323027a3` | Shared with Piercing & Slashing |
| `ColdFX` | Cold | `fbf84ffe-13e0-4cdc-90f3-eed60846148d` | Unique VFX |
| `FireFX` | Fire | `23ebafcb-e11c-4f9a-a4b2-e10396ea11cc` | Unique VFX |
| `ForceFX` | Force | `38e81436-b403-4c8b-abe3-616e5600016e` | Unique VFX |
| `LightningFX` | Lightning | `1ba77ac8-14d4-4ffd-a566-4bf1ad096a80` | Unique VFX |
| `NecroticFX` | Necrotic | `366b5ab6-8280-44fa-84b0-56ef89216d08` | Unique VFX |
| `PiercingFX` | Piercing | `54cee685-7ba1-4ab4-96b8-f5b2323027a3` | Shared with Bludgeoning & Slashing |
| `PoisonFX` | Poison | `168df269-f2d3-4cf7-8e79-113b146d9bb3` | Unique VFX |
| `PsychicFX` | Psychic | `9ef115db-4a1d-4846-b286-3364cd5fdc28` | Unique VFX |
| `RadiantFX` | Radiant | `cad6a0a7-08e1-45eb-85bc-5ea35fa34683` | Unique VFX |
| `SlashingFX` | Slashing | `54cee685-7ba1-4ab4-96b8-f5b2323027a3` | Shared with Bludgeoning & Piercing |
| `ThunderFX` | Thunder | `89dc7308-3fae-44e3-8333-d8307efec4a7` | Unique VFX |

### Physical Damage VFX Sharing

Bludgeoning, Piercing, and Slashing all reference UUID `54cee685-7ba1-4ab4-96b8-f5b2323027a3` — physical damage types share a single critical hit VFX. The remaining 10 elemental/exotic damage types each have a unique VFX.

## Caveats

- **Single entry only** — vanilla defines exactly one `Default` entry. Mods can add new entries, but the engine likely only references `Default`.
- **No inheritance** — the `Default` entry does not use `using`, and there's nothing to inherit from.
- **No SharedDev file** — unlike most stat types, `CriticalHitTypes.txt` exists only in Shared.

## Pack Distribution

| Pack | Has File | Notes |
|------|----------|-------|
| Shared | Yes | Only pack — defines the single `Default` entry |
| SharedDev | No | No CriticalHitTypes.txt present |

## Cross-References

- **Modifiers.md** — [CriticalHitTypeData section](../formats/Modifiers.md#criticalhittypedata) defines the 13 Guid fields
- **ValueLists.md** — [CriticalHitTypes](../formats/ValueLists.md) enum used to look up entries by name
