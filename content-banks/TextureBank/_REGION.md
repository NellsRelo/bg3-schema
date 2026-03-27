# Region: `TextureBank`

> **Category**: Visual
> **Primary Node**: [Resource](Resource.md)
>
> Registers individual texture assets (DDS files) with metadata like dimensions, format, and streaming flags.
> Flat resource structure — no child nodes.

---

## File Inventory

| Source | Path Pattern | Content |
|--------|-------------|---------|
| Shared | `Content/Assets/.../_merged.lsx` | Texture registrations across all asset categories |

**9 files in Shared** containing TextureBank regions.

## Region Structure

```xml
<region id="TextureBank">
  <node id="TextureBank">
    <children>
      <node id="Resource"> ... </node>
    </children>
  </node>
</region>
```

## Node Types

| Node | File | Description |
|------|------|-------------|
| Resource | [Resource.md](Resource.md) | One per texture — flat, no child nodes |

## Cross-Region References

| From | To | Via |
|------|----|-----|
| TextureBank.ID | [MaterialBank](../MaterialBank/_REGION.md) | `Texture2DParameters.ID` — material texture parameter |
| TextureBank.ID | [LightCookieBank](../LightCookieBank/_REGION.md) | `TextureName` — light cookie texture |
| TextureBank.ID | [TerrainBrushBank](../TerrainBrushBank/_REGION.md) | `BaseColorMap`/`NormalMap`/`PhysicalMap` — terrain textures |
