# Region: `AtmosphereBank`

> **Category**: Environment
> **Primary Node**: [Resource](Resource.md)
>
> Defines atmosphere presets — comprehensive environment configurations that control
> lighting, fog, post-processing, cloth wind, and color correction.
> The most attribute-rich bank type.

---

## File Inventory

| Source | Path Pattern | Content |
|--------|-------------|---------|
| Shared | `Content/Assets/Atmospheres/[PAK]_Atmospheres/_merged.lsx` | Shared atmospheres (co-located with VirtualTextureBank) |
| Gustav | `Content/Assets/Atmospheres/.../_merged.lsx` | Campaign-specific atmospheres |

**1 file in Shared, 1 in Gustav** containing AtmosphereBank regions.

## Region Structure

```xml
<region id="AtmosphereBank">
  <node id="AtmosphereBank">
    <children>
      <node id="Resource"> ... </node>
    </children>
  </node>
</region>
```

## Node Types

| Node | File | Description |
|------|------|-------------|
| Resource | [Resource.md](Resource.md) | One per atmosphere — deeply nested (5+ levels, hundreds of attributes) |

## Cross-Region References

| From | To | Via |
|------|----|-----|
| AtmosphereBank.Atmosphere.EnvironmentEffect | [EffectBank](../EffectBank/_REGION.md) | Environment effect |
| AtmosphereBank.Labels | [TimelineSceneBank](../TimelineSceneBank/_REGION.md) | Shared scene tagging system |

## Co-located Banks

AtmosphereBank is co-located with:
- [VirtualTextureBank](../VirtualTextureBank/_REGION.md) (atmosphere asset bundles)

## Notes

- **Most attribute-rich bank type** — hundreds of attributes across nested hierarchy
- Two color correction formats exist: `NewColorCorrection` (modern, range-based) and `ColorCorrection` (legacy, RGBA curves)
- `InheritanceFlags` on Atmosphere controls which settings cascade from parent atmospheres
