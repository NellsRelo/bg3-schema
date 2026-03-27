# Node: `Faction`

> **Region**: [FactionContainer](_REGION.md)
> **Folder**: `Factions/`
> **Vanilla entries**: 62 (Shared)

---

## Attributes

| Attribute | Type | Frequency | Examples | Notes |
|-----------|------|-----------|----------|-------|
| `UUID` | guid | 62/62 | `a863d0cc-...` | Primary key |
| `Faction` | FixedString | 62/62 | `AnimalBase`, `Animal_Bear`, `Player` | Human-readable faction name |
| `ParentGuid` | guid | 62/62 | `00000000-...` | Parent faction UUID (null GUID for root factions) |

## Child Nodes

*(None in vanilla data)*

## Patterns of Use

- Hierarchical faction tree: `AnimalBase` is parent of `Animal_Bear`, `Animal_Beetle`, etc.
- Root factions use null GUID (`00000000-...`) as `ParentGuid`.
- Key factions: `Player`, `Companion`, `NPC_Friendly`, `NPC_Hostile`, animal subtypes.

## Cross-References

| From | To | Via |
|------|----|-----|
| Faction | Faction (parent) | `ParentGuid` → `UUID` |
| FactionManager/Relation | Faction | `Faction1`/`Faction2` |
| GameObjects | Faction | Template faction assignment |

## Caveats & Gotchas

- **Region is `FactionContainer`**, not `Factions` — the region name differs from the folder name.
- Parent GUID can be null (all zeros) for root factions.

## Similarities to Other Nodes

- **FactionManager/Relation**: Defines faction-to-faction relationships (reaction values).
