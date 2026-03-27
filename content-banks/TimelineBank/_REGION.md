# Region: `TimelineBank`

> **Category**: Scene
> **Primary Node**: [Resource](Resource.md)
>
> Registers timeline resources — cinematic/dialog sequences that control camera, animation,
> audio, and staging over time. Links to DialogBank resources.

---

## File Inventory

| Source | Path Pattern | Content |
|--------|-------------|---------|
| Shared | `Content/Generated/[PAK]_GeneratedDialogTimelines/_merged.lsx` | Auto-generated dialog timelines |
| Gustav | `Content/Generated/.../_merged.lsx` | Campaign timelines |

**1 file in Shared, 2 in Gustav** containing TimelineBank regions.

## Region Structure

```xml
<region id="TimelineBank">
  <node id="TimelineBank">
    <children>
      <node id="Resource"> ... </node>
    </children>
  </node>
</region>
```

## Node Types

| Node | File | Description |
|------|------|-------------|
| Resource | [Resource.md](Resource.md) | One per timeline — contains dependency cache |

## Cross-Region References

| From | To | Via |
|------|----|-----|
| TimelineBank.ID | [TimelineSceneBank](../TimelineSceneBank/_REGION.md) | Scene composition |
| TimelineBank.DialogResourceId | [DialogBank](../DialogBank/_REGION.md) | Dialog link |
