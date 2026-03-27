# Node: `ItemWallTemplates`

> **Region**: [ItemWallTemplates](_REGION.md)
> **Folder**: `ItemWallTemplates/`
> **Source**: `Shared/Public/SharedDev/ItemWallTemplates/ItemWallTemplates.lsx`
> **Total Nodes**: ~6 (SharedDev only)

---

## Attributes

| Attribute | Type | Frequency | Examples | Notes |
|-----------|------|-----------|----------|-------|
| `UUID` | guid | x6 | `a2d0fcc0-f5bc-4346-9d4b-105e621084cc` | Primary key |
| `Name` | LSString | x6 | `BladeBarrier`, `WallOfFire`, `WallOfIce` | Wall spell name |
| `HighLeft` | LSString | x6 | VFX ref + UUID | VFX for high-left wall segment |
| `HighMiddle` | LSString | x6 | VFX ref + UUID | VFX for high-middle wall segment |
| `HighRight` | LSString | x6 | VFX ref + UUID | VFX for high-right wall segment |
| `LowLeft` | LSString | x6 | VFX ref + UUID | VFX for low-left wall segment |
| `LowMiddle` | LSString | x6 | VFX ref + UUID | VFX for low-middle wall segment |
| `LowRight` | LSString | x6 | VFX ref + UUID | VFX for low-right wall segment |
| `Animation` | FixedString | x4 | `OddEven` | Wall segment animation pattern (sparse) |
| `RandomRotation` | bool | x4 | `true` | Randomize segment rotation (sparse) |
| `TimeBetweenItems` | float | x4 | `0.033`, `0.050000001` | Delay between spawning segments (sparse) |
| `Padding` | float | x3 | `-0.30000001`, `-0.2`, `-0.60000002` | Spacing offset between segments (sparse) |

## Child Nodes

None.

## Patterns of Use

- Defines VFX templates for wall spells (Blade Barrier, Wall of Fire, Wall of Ice, etc.)
- 6 positional VFX slots (HighLeft/Middle/Right, LowLeft/Middle/Right) define wall segment visuals
- VFX values are composite strings: `VFX_Name_UUID` format
- `Animation`, `RandomRotation`, `TimeBetweenItems`, `Padding` are sparse — used only by some walls

## Caveats & Gotchas

- Only in SharedDev pack, not Shared
- VFX attribute values embed both name and UUID in a single string

## Similarities to Other Nodes

None — unique wall spell VFX template system.
