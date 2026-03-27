# Region: `Reactions`

> **Folder**: `ApprovalRatings/`
> **Primary Node**: [Reaction](Reaction.md)
>
> Gustav only - approval events

---

## File Inventory

| Source | File | Entries | Version |
|--------|------|---------|---------|
| Shared | *.lsx | — | — |
| SharedDev | *.lsx | — | — |
| Gustav | *.lsx | — | — |
| GustavDev | *.lsx | — | — |
| GustavX | *.lsx | — | — |

## Region Structure

```xml
<region id="Reactions">
  <node id="root">
    <children>
      <node id="Reaction"> ... </node>
    </children>
  </node>
</region>
```

## Node Types

| Node | File | Description |
|------|------|-------------|
| Reaction | [Reaction.md](Reaction.md) | Primary node type |

## Cross-Region References

- **Origins** — each Reaction is tied to a companion via `OriginUUID`; only origin companions have approval ratings
- **Tags** — reaction conditions may check tags on the player or NPCs involved in the triggering event
- **Flags** — approval milestones set flags that gate dialog, romance, and story progression
- **Osiris** — `ApprovalRatingChanged`, `DB_Approval_HasAttitude` events fire when reactions shift approval state
- **Dialog** — companion dialog branches frequently check cumulative approval thresholds

## Caveats

- **Folder != Region**: This region lives in `ApprovalRatings/` not `Reactions/`
- **Gustav-only** — approval reactions are campaign-specific; Shared/SharedDev contain no entries
