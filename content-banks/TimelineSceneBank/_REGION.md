# Region: `TimelineSceneBank`

> **Category**: Scene
> **Primary Node**: [Resource](Resource.md)
>
> Composes timeline scenes from timelines and speaker configurations.
> Metadata layer that describes how timelines are assembled into complete scenes.

---

## File Inventory

| Source | Path Pattern | Content |
|--------|-------------|---------|
| Shared | `Content/Generated/.../_merged.lsx` | Generated scene compositions |
| Gustav | `Content/Generated/.../_merged.lsx` | Campaign scene compositions |

**1 file in Shared, 1 in Gustav** — scene banks are generated files.

## Region Structure

```xml
<region id="TimelineSceneBank">
  <node id="TimelineSceneBank">
    <children>
      <node id="Resource"> ... </node>
    </children>
  </node>
</region>
```

## Node Types

| Node | File | Description |
|------|------|-------------|
| Resource | [Resource.md](Resource.md) | One per scene — contains optional labels |

## Cross-Region References

| From | To | Via |
|------|----|-----|
| TimelineSceneBank.Labels | [AtmosphereBank](../AtmosphereBank/_REGION.md) | Shared scene tagging system |

## Notes

- `SourceFile` uses type `string` (not `LSString`) — unusual among bank types
- Labels (like `EXT_NIGHT`, `CAMP`, `DUNGEON`) tag scenes for scheduling/filtering
- `SceneType` values observed: 1 (dialog), 2 (cinematic), 4 (ambient)
