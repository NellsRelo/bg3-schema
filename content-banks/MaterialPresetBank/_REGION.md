# Region: `MaterialPresetBank`

> **Category**: Visual
> **Primary Node**: [Resource](Resource.md)
>
> Defines material override presets for character visual customization (eye colors, skin tones, tattoo colors, etc.).
> Referenced by `CharacterVisualBank.MaterialOverrides.ColorPreset.MaterialPresetResource`.

---

## File Inventory

| Source | Path Pattern | Content |
|--------|-------------|---------|
| Shared | `Content/Assets/Characters/.../_merged.lsx` | Character material presets |
| Shared | `Content/[PAK]_CharacterVisuals/_merged.lsx` | Root-level presets |

**47 files in Shared** containing MaterialPresetBank regions.

## Region Structure

```xml
<region id="MaterialPresetBank">
  <node id="MaterialPresetBank">
    <children>
      <node id="Resource"> ... </node>
    </children>
  </node>
</region>
```

## Node Types

| Node | File | Description |
|------|------|-------------|
| Resource | [Resource.md](Resource.md) | One per material preset — contains color/scalar override values |

## Cross-Region References

| From | To | Via |
|------|----|-----|
| MaterialPresetBank.ID | [CharacterVisualBank](../CharacterVisualBank/_REGION.md) | `MaterialOverrides.ColorPreset.MaterialPresetResource` |
| MaterialPresetBank.Presets.MaterialResource | [MaterialBank](../MaterialBank/_REGION.md) | Base material |

## Co-located Banks

MaterialPresetBank is frequently co-located with:
- [CharacterVisualBank](../CharacterVisualBank/_REGION.md) (character preset bundles)
