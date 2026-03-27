# Region: `LightingBank`

> **Category**: Environment
> **Primary Node**: [Resource](Resource.md)
>
> Defines lighting setups — sun, sky light, fog, SSAO, volumetric clouds, and shadow configuration.
> Often co-located with EffectBank in light source files.

---

## File Inventory

| Source | Path Pattern | Content |
|--------|-------------|---------|
| Shared | `Content/Assets/Effects/Effects/[PAK]_LightSources/_merged.lsx` | Light source definitions |

**1 file in Shared** containing LightingBank regions.

## Region Structure

```xml
<region id="LightingBank">
  <node id="LightingBank">
    <children>
      <node id="Resource"> ... </node>
    </children>
  </node>
</region>
```

## Node Types

| Node | File | Description |
|------|------|-------------|
| Resource | [Resource.md](Resource.md) | One per lighting setup — deeply nested (4+ levels) |

## Cross-Region References

| From | To | Via |
|------|----|-----|
| LightingBank.ID | [AtmosphereBank](../AtmosphereBank/_REGION.md) (indirect) | Atmosphere lighting reference |
| LightingBank co-located with | [EffectBank](../EffectBank/_REGION.md) | Same `_merged.lsx` file |

## Notes

- Only 1 instance in Shared — LightingBank defines scene-level lighting presets
- **Always co-located with EffectBank** — light source `_merged.lsx` files contain both banks
- Fog attributes differ from AtmosphereBank fog (LightingBank uses `Albedo`, `Density0`/`Density1`, noise params)
