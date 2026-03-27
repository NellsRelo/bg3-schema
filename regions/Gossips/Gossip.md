# Node: `Gossip`

> **Region**: [Gossips](_REGION.md)
> **Folder**: `Gossips/`
> **Vanilla entries**: 408 (Gustav: 59, GustavDev: 349)

---

## Attributes

| Attribute | Type | Frequency | Examples | Notes |
|-----------|------|-----------|----------|-------|
| `UUID` | guid | 408/408 | `afe28d33-...` | Primary key |
| `Name` | FixedString | 408/408 | `PB_Shadowheart_Laezel_Gith1`, `PB_Astarion_Shadowheart_Temple` | Internal identifier |
| `DialogUUID` | guid | 408/408 | `0ed0a6e2-...` | References dialog resource |
| `Priority` | int32 | 408/408 | `30`, `50`, `80` | Higher priority = plays first when conditions met |
| `Type` | FixedString | 408/408 | `PartyBanter` | Gossip type (all vanilla entries are `PartyBanter`) |

## Child Nodes

| Child | Frequency | Notes |
|-------|-----------|-------|
| `ConditionFlags` | Gustav: 45, GustavDev: 349 | Flag conditions that trigger gossip |
| `ResultFlags` | Gustav: 3 | Flags set after gossip plays |

## Patterns of Use

- Almost all entries have ConditionFlags children.
- Names follow `PB_{Companion1}_{Companion2}_{Topic}` pattern.
- All vanilla entries use `PartyBanter` type.

## Cross-References

| From | To | Via |
|------|----|-----|
| Gossip.DialogUUID | Dialog resources | Dialog tree UUID |
| Gossip.ConditionFlags | [Flags](../Flags/Flags.md) | Flag UUID conditions that must be set/cleared for gossip to trigger |
| Gossip.ResultFlags | [Flags](../Flags/Flags.md) | Flag UUID set after gossip plays (prevents repeats) |

## ConditionFlags & ResultFlags Detail

**ConditionFlags** children define the conditions under which a gossip triggers. Each ConditionFlag entry contains:
- A Flag UUID reference
- A required state (set or cleared)
- These act as AND conditions — all must be satisfied for the gossip to be eligible

**ResultFlags** children define flags set after the gossip plays. This is the primary mechanism to prevent a gossip from replaying.

**Priority system**: When multiple gossips have their conditions met simultaneously, `Priority` determines which plays first. Higher priority = higher precedence.

## Caveats & Gotchas

- **Gustav-only** — Split across two packs (Gustav: 59, GustavDev: 349). No gossips in Shared/SharedDev/GustavX.
- **PartyBanter only** — All 408 vanilla entries use `Type="PartyBanter"`. Other types may exist for mods but are undocumented.
- **Naming convention** — Names follow `PB_{Companion1}_{Companion2}_{Topic}` pattern (e.g., `PB_Shadowheart_Laezel_Gith1`).
- **Dialog dependency** — The `DialogUUID` must reference a valid dialog resource. Without the dialog, the gossip triggers but produces no output.
- **Flag dependency** — ConditionFlags reference [Flags](../Flags/_REGION.md) that are set by story scripts, dialog results, and Osiris. Custom gossips require custom flags.

## Similarities to Other Nodes

- [Reactions](../Reactions/Reaction.md) also uses Flag-based conditions for companion approval events.
- [Crime](../Crime/Crime.md) uses similar flag/condition patterns for crime detection triggers.
