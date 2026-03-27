# Region: `VirtualTextureBank`

> **Category**: Visual
> **Primary Node**: [Resource](Resource.md)
>
> Registers virtual texture assets for streaming — allows large textures to be loaded on demand.
> Flat resource structure — no child nodes. Often co-located with other banks in the same file.

---

## File Inventory

| Source | Path Pattern | Content |
|--------|-------------|---------|
| Shared | `Content/Assets/.../_merged.lsx` | Virtual texture registrations across all asset categories |
| Gustav | `Content/Assets/.../_merged.lsx` | Campaign virtual textures |

**263 files in Shared, 204 in Gustav** — the most common bank type by file count.

## Region Structure

```xml
<region id="VirtualTextureBank">
  <node id="VirtualTextureBank">
    <children>
      <node id="Resource"> ... </node>
    </children>
  </node>
</region>
```

## Node Types

| Node | File | Description |
|------|------|-------------|
| Resource | [Resource.md](Resource.md) | One per virtual texture — flat, no child nodes |

## Cross-Region References

| From | To | Via |
|------|----|-----|
| VirtualTextureBank.ID | [MaterialBank](../MaterialBank/_REGION.md) | `VirtualTextureParameters.ID` — material VT binding |

## Co-located Banks

VirtualTextureBank is almost always co-located with other banks:
- [MaterialBank](../MaterialBank/_REGION.md), [VisualBank](../VisualBank/_REGION.md), [SkeletonBank](../SkeletonBank/_REGION.md) (asset bundles — 212 files)
- [AtmosphereBank](../AtmosphereBank/_REGION.md) (atmosphere bundles)
- [DiffusionProfileBank](../DiffusionProfileBank/_REGION.md) (SSS material bundles)
