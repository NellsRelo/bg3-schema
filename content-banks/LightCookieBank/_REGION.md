# Region: `LightCookieBank`

> **Category**: Environment
> **Primary Node**: [Resource](Resource.md)
>
> Defines light cookie textures — projected shadow/pattern maps for light sources.
> Each entry includes a grid of boolean coverage data (~128 cells).

---

## File Inventory

| Source | Path Pattern | Content |
|--------|-------------|---------|
| Shared | `Content/Assets/.../_merged.lsx` | Light cookie definitions |
| Gustav | `Content/Assets/.../_merged.lsx` | Campaign light cookies |

**2 files in Shared, 1 in Gustav** containing LightCookieBank regions.

## Region Structure

```xml
<region id="LightCookieBank">
  <node id="LightCookieBank">
    <children>
      <node id="Resource"> ... </node>
    </children>
  </node>
</region>
```

## Node Types

| Node | File | Description |
|------|------|-------------|
| Resource | [Resource.md](Resource.md) | One per light cookie — contains ~128 boolean coverage grid cells |

## Cross-Region References

| From | To | Via |
|------|----|-----|
| LightCookieBank.TextureName | [TextureBank](../TextureBank/_REGION.md) | Cookie texture source |

## Notes

- Used for window shadows, foliage dappling, gobo patterns on spotlights
- The `Data` children form a flattened 2D grid (~128 cells) representing the coverage pattern
