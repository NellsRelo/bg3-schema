# Region: `AnimationBlueprintBank`

> **Category**: Animation
> **Primary Node**: [Resource](Resource.md)
>
> Defines animation state machine blueprints — the logic that controls animation transitions.
> Each blueprint references a compiled `.lsabp` file.

---

## File Inventory

| Source | Path Pattern | Content |
|--------|-------------|---------|
| Shared | `Content/Assets/.../_merged.lsx` | Animation blueprint registrations |

**140 files in Shared** containing AnimationBlueprintBank regions.

## Region Structure

```xml
<region id="AnimationBlueprintBank">
  <node id="AnimationBlueprintBank">
    <children>
      <node id="Resource"> ... </node>
    </children>
  </node>
</region>
```

## Node Types

| Node | File | Description |
|------|------|-------------|
| Resource | [Resource.md](Resource.md) | One per blueprint — contains empty Params child |

## Cross-Region References

| From | To | Via |
|------|----|-----|
| AnimationBlueprintBank.ID | [VisualBank](../VisualBank/_REGION.md) | `BlueprintInstanceResourceID` — visual animation blueprint |
| AnimationBlueprintBank.PreviewVisualResourceID | [VisualBank](../VisualBank/_REGION.md) | Editor preview |

## Notes

- 140 instances in Shared — used for complex animation state machines (combat, interactions, cinematics)
- The `Params` child node is always empty in the data — actual parameters are compiled into the `.lsabp` file
- `PreviewVisualResourceID` is often null UUID (`00000000-...`)
