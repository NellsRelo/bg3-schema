# Node: `DeathEffect`

> **Region**: [DeathEffects](_REGION.md)
> **Folder**: `VFX/`
> **Vanilla entries**: 22 (Shared)

---

## Attributes

| Attribute | Type | Frequency | Examples | Notes |
|-----------|------|-----------|----------|-------|
| `UUID` | guid | 22/22 | `eb0aa43b-...` | Primary key |
| `Name` | LSString | 22/22 | `Default`, `UniqueDarkSmoky`, `SummonDruidNecrotic` | Death effect set name |
| `Acid` | guid | 22/22 | `217d7431-...` | VFX template for acid death |
| `Chasm` | guid | 22/22 | `3bd49f3e-...` | VFX template for chasm/void death |
| `CinematicDeath` | guid | 22/22 | `8513eaaf-...` | VFX template for cinematic death |
| `Cold` | guid | 22/22 | `84497bd0-...` | VFX template for cold death |
| `Disintegrate` | guid | 22/22 | `43e47166-...` | VFX template for disintegration |
| `DoT` | guid | 22/22 | `9923f4e5-...` | VFX template for damage-over-time death |
| `Electrocution` | guid | 22/22 | `c8573a1c-...` | VFX template for lightning death |
| `Explode` | guid | 22/22 | `49a45fc7-...` | VFX template for explosion death |
| `Fallback` | guid | 22/22 | `256f6bd9-...` | Default VFX when no specific type applies |
| `Falling` | guid | 22/22 | `2931cb89-...` | VFX template for falling death |
| `Incinerate` | guid | 22/22 | `5146a084-...` | VFX template for fire death |
| `KnockedDown` | guid | 22/22 | `8a0e4b52-...` | VFX template for knocked-down death |
| `Lifetime` | guid | 22/22 | `692747ac-...` | VFX template for lifetime-expiry death (summons) |
| `Necrotic` | guid | 22/22 | `e7074131-...` | VFX template for necrotic death |
| `Physical` | guid | 22/22 | `43303547-...` | VFX template for physical death |
| `Psychic` | guid | 22/22 | `c71b00ba-...` | VFX template for psychic death |
| `Radiant` | guid | 22/22 | `257d9555-...` | VFX template for radiant death |

## Child Nodes

*(None in vanilla data)*

## Patterns of Use

- Each effect set maps every damage type to a VFX template GUID.
- All 22 entries have all 18 attributes — no optional fields.
- Most entries use the same VFX GUIDs for each damage type, with variations in `Fallback` and `Lifetime`.

## Cross-References

| From | To | Via |
|------|----|-----|
| DeathEffect | VFX templates | Each damage-type attribute is a template GUID |

## Caveats & Gotchas

- Every damage type column is always present (no sparse fields).

## Similarities to Other Nodes

- **ManagedStatusVFX**: Also maps VFX by category.
