# Node: `Relation`

> **Region**: [FactionManager](_REGION.md)
> **Folder**: `Factions/`
> **Source**: `Shared/Public/Shared/Factions/Relations.lsx`, `Gustav/Public/Gustav/Factions/Relations.lsx`
> **Total Nodes**: ~520 combined (Shared: 38, Gustav: 482)

---

## Attributes

| Attribute | Type | Frequency | Examples | Notes |
|-----------|------|-----------|----------|-------|
| `Source` | guid | always | `a863d0cc-60b9-b450-f90d-8a4dc192ecb9` | FK → `Faction.UUID` (source faction) |
| `Target` | guid | always | `4be9261a-e481-8d9d-3528-f36956a19b17` | FK → `Faction.UUID` (target faction) |
| `Value` | int32 | always | `50`, `100` | Disposition value (0–100 scale; 50 = neutral) |

## Child Nodes

None.

## Patterns of Use

- Defines directional disposition between two factions
- Source → Target is directional; the reverse relation may differ or not exist
- `Value=50` is neutral; higher = friendlier, lower = hostile
- Gustav has the bulk of relations (~482) for game-specific faction interactions
- Shared has base/system relations (~38)
- **No UUID on this node** — the (Source, Target) pair is the composite key

## Cross-References

| From | To | Via |
|------|----|-----|
| `Relation.Source` | `Faction.UUID` | FK |
| `Relation.Target` | `Faction.UUID` | FK |

## Caveats & Gotchas

- **No UUID attribute** — unusual, uses composite key (Source + Target)
- Relations are directional: Faction A → Faction B may differ from B → A

## Similarities to Other Nodes

Companion node to `Faction` (in `FactionContainer` region) — factions define the entities, relations define how they interact.
