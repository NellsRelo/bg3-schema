# Region: `CharacterVisualBank`

> **Category**: Visual
> **Primary Node**: [Resource](Resource.md)
>
> Assembles complete character appearances from visual slots, material overrides, and color presets.
> The primary entry point for character appearance — referenced by `GameObjects.CharacterVisualResourceID`.

---

## File Inventory

| Source | Path Pattern | Content |
|--------|-------------|---------|
| Shared | `Content/[PAK]_CharacterVisuals/_merged.lsx` | Root-level character visuals (7 MB, largest single file) |
| Shared | `Content/Assets/Characters/.../_merged.lsx` | Per-creature character visuals |
| Gustav | `Content/Assets/Characters/.../_merged.lsx` | Campaign character visuals |

**17 files in Shared** containing CharacterVisualBank regions.

## Region Structure

```xml
<region id="CharacterVisualBank">
  <node id="CharacterVisualBank">
    <children>
      <node id="Resource"> ... </node>
    </children>
  </node>
</region>
```

## Node Types

| Node | File | Description |
|------|------|-------------|
| Resource | [Resource.md](Resource.md) | One per character visual — contains slots, material overrides, color presets |

## Cross-Region References

| From | To | Via |
|------|----|-----|
| CharacterVisualBank.ID | GameObjects | `CharacterVisualResourceID` field |
| CharacterVisualBank.BaseVisual | [VisualBank](../VisualBank/_REGION.md) | Base body mesh |
| CharacterVisualBank.BodySetVisual | [VisualBank](../VisualBank/_REGION.md) | Body set mesh |
| CharacterVisualBank.Slots.VisualResource | [VisualBank](../VisualBank/_REGION.md) | Per-slot mesh |
| CharacterVisualBank.MaterialOverrides.MaterialResource | [MaterialBank](../MaterialBank/_REGION.md) | Material override |
| CharacterVisualBank.MaterialOverrides.ColorPreset.MaterialPresetResource | [MaterialPresetBank](../MaterialPresetBank/_REGION.md) | Color preset |

## Co-located Banks

CharacterVisualBank is frequently co-located with:
- [MaterialPresetBank](../MaterialPresetBank/_REGION.md) (character preset bundles)

## Modding Notes

- Character appearance mods primarily create or modify CharacterVisualBank entries
- The `Slots` children define which mesh goes on which body part (`Head`, `Body`, `Hair`, `Underwear`, etc.)
- `MaterialOverrides` control skin tone, eye color, hair color, and similar shader parameters
- `Name` is a human-readable label — the engine uses `ID` for resolution
