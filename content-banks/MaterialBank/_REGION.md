# Region: `MaterialBank`

> **Category**: Visual
> **Primary Node**: [Resource](Resource.md)
>
> Defines material/shader instances — controls how surfaces look when rendered.
> Referenced by `VisualBank.Objects.MaterialID` and indirectly through `CharacterVisualBank.MaterialOverrides`.

---

## File Inventory

| Source | Path Pattern | Content |
|--------|-------------|---------|
| Shared | `Content/Assets/.../_merged.lsx` | Material definitions across all asset categories |

**48 files in Shared** containing MaterialBank regions.

## Region Structure

```xml
<region id="MaterialBank">
  <node id="MaterialBank">
    <children>
      <node id="Resource"> ... </node>
    </children>
  </node>
</region>
```

## Node Types

| Node | File | Description |
|------|------|-------------|
| Resource | [Resource.md](Resource.md) | One per material — contains shader parameters, texture refs, virtual texture bindings |

## Cross-Region References

| From | To | Via |
|------|----|-----|
| MaterialBank.ID | [VisualBank](../VisualBank/_REGION.md) | `Objects.MaterialID` — LOD mesh material |
| MaterialBank.DiffusionProfileUUID | [DiffusionProfileBank](../DiffusionProfileBank/_REGION.md) | Subsurface scattering profile |
| MaterialBank.Texture2DParameters.ID | [TextureBank](../TextureBank/_REGION.md) | Texture reference |
| MaterialBank.VirtualTextureParameters.ID | [VirtualTextureBank](../VirtualTextureBank/_REGION.md) | Virtual texture reference |

## Key Difference: MaterialBank vs MaterialPresetBank

| Aspect | MaterialBank | [MaterialPresetBank](../MaterialPresetBank/_REGION.md) |
|--------|-------------|-------------------|
| Scalar param name field | `ParameterName` | `Parameter` |
| Has `BaseValue`/`GroupName`/`ExportAsPreset` | Yes | No |
| Has `Color`/`Custom` | No | Yes |
| Purpose | Full material definition | Override preset for character visuals |

## Co-located Banks

MaterialBank is frequently co-located with:
- [VirtualTextureBank](../VirtualTextureBank/_REGION.md), [VisualBank](../VisualBank/_REGION.md), [SkeletonBank](../SkeletonBank/_REGION.md) (asset bundles — 212 files)
- [TextureBank](../TextureBank/_REGION.md) (material definition files)
