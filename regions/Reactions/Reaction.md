# Node: `Reaction`

> **Region**: [Reactions](_REGION.md)
> **Source**: `*/Public/*/ApprovalRatings/Reactions/<UUID>.lsx` (one file per entry)
> **Note**: The root `Reactions.lsx` files are empty shells; actual data lives in UUID-named subdirectories.

---

## Attributes

| Attribute | Type | Frequency | Examples | Notes |
|-----------|------|-----------|----------|-------|
| `Scope` | uint8 | always | `0`, `1`, `2` | Reaction scope (0=global?, 1=companion?, 2=party?) |
| `UUID` | guid | always | — | Primary key (matches filename) |

## Child Nodes

### Reactions

Container for one or more inner `Reaction` children defining approval/disapproval ratings:

```xml
<node id="Reactions">
  <children>
    <node id="Reaction">
      <attribute id="id" type="guid" value="<event-uuid>" />
      <attribute id="value" type="int32" value="1" />
    </node>
    <!-- more Reaction children -->
  </children>
</node>
```

| Attribute | Type | Notes |
|-----------|------|-------|
| `id` | guid | Reference to an approval event/trigger |
| `value` | int32 | Approval delta; observed values: `-1`, `0`, `1`, `3`, `5`, `8`, `10`, `15` |

Each outer Reaction typically has 0–8 inner Reaction children.

## Vanilla Scope

| Pack | Files |
|------|-------|
| Gustav | 39 |
| GustavDev | 2,102 |
| **Total** | **2,141** |

Shared, SharedDev, and GustavX have no Reactions data.

Companion approval reaction definitions. Each file defines how one companion/NPC reacts
to a set of game events (identified by guid) with positive or negative approval values.
The `Scope` field likely controls the context in which the reaction applies.

## Caveats & Gotchas

- **Folder ? Region**: Lives in `ApprovalRatings/` not `Reactions/`.
- **Gustav-only** — Only Gustav (39 files) and GustavDev (2,102 files) have reaction data. Shared/SharedDev/GustavX have none.
- **One file per companion/NPC** — Each UUID-named file contains one outer Reaction node representing one character's approval settings.
- **Inner Reaction children** share the same node name as the container — outer `Reactions` contains inner `Reaction` children. Do not confuse the two levels.
- **Approval values** — Observed values range from `-1` to `15`. Positive = approval, negative = disapproval. Common values: `1` (mild), `3` (moderate), `5` (significant), `10` (major), `15` (extreme).
- **Scope values** — `0`, `1`, `2` observed. Exact semantics undocumented (likely: 0=global, 1=companion-specific, 2=party-wide).

## Osiris Scripting Connection

Approval events are triggered via Osiris procedures and can be hooked:
- `ApprovalRatingChanged(companionGUID, oldValue, newValue)` — Fires when approval changes
- The `id` guid in inner Reaction children references specific game decisions/events tracked by the approval system
- SE: `Ext.Osiris.RegisterListener("ApprovalRatingChanged", ...)` for custom reactions to approval shifts

## Cross-References

| From | To | Via |
|------|----|-----|
| Reaction inner `id` | Approval events | Engine-tracked decision points |
| Outer Reaction UUID | Companion character | Maps to specific companion via UUID |
| [Flags](../Flags/Flags.md) | Reaction triggers | Flags set by dialog/story events that trigger approval |

## Similarities to Other Nodes

- [Gossips](../Gossips/Gossip.md) also uses Flag-based conditions for companion-related triggers.
- [BackgroundGoals](../BackgroundGoals/BackgroundGoal.md) also provides per-companion/per-character rewards (inspiration) tied to game events.
