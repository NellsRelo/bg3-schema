# Region: `DiffusionProfileBank`

> **Category**: Visual
> **Primary Node**: [DiffusionProfile](DiffusionProfile.md)
>
> Defines subsurface scattering profiles — controls how light penetrates translucent surfaces
> (skin, wax, foliage, etc.). Referenced by `MaterialBank.DiffusionProfileUUID`.

---

## File Inventory

| Source | Path Pattern | Content |
|--------|-------------|---------|
| Shared | `Content/Assets/.../_merged.lsx` | SSS profile definitions |

**17 files in Shared** containing DiffusionProfileBank regions.

## Region Structure

```xml
<region id="DiffusionProfileBank">
  <node id="DiffusionProfileBank">
    <children>
      <node id="DiffusionProfile"> ... </node>   <!-- note: uses DiffusionProfile, not Resource -->
    </children>
  </node>
</region>
```

## Node Types

| Node | File | Description |
|------|------|-------------|
| DiffusionProfile | [DiffusionProfile.md](DiffusionProfile.md) | One per SSS profile — flat, no child nodes |

## Cross-Region References

| From | To | Via |
|------|----|-----|
| DiffusionProfileBank.ID | [MaterialBank](../MaterialBank/_REGION.md) | `DiffusionProfileUUID` — material SSS profile |

## Co-located Banks

DiffusionProfileBank is frequently co-located with:
- [VirtualTextureBank](../VirtualTextureBank/_REGION.md) (SSS material bundles)

## Caveats

- **Unique node ID**: Uses `DiffusionProfile` instead of the standard `Resource` node ID used by all other bank types
