# Node: `AiPathSettings` (root-level attributes)

> **Region**: [AiPathSettings](_REGION.md)
> **Folder**: `GUI/`
> **Source**: `Shared/Public/Shared/GUI/AiPathSettings.lsx`
> **Structure**: Non-standard — attributes directly on root node, no child nodes

---

## Attributes (on root)

All attributes are directly on the `root` node (no child `AiPathSettings` nodes).

| Attribute | Type | Value | Notes |
|-----------|------|-------|-------|
| `AnimationSpeed` | float | `1` | Animation playback speed |
| `AttenuationDistanceEnd` | float | `1` | Fade-out end distance |
| `AttenuationDistanceStart` | float | `1` | Fade-out start distance |
| `ClearStateIconVFXResourceName` | FixedString | `""` | VFX for clear visibility state (empty) |
| `ClimbingIconVFXResourceName` | FixedString | `""` | VFX for climbing state (empty) |
| `HeavilyStateIconVFXResourceName` | FixedString | `""` | VFX for heavily obscured state (empty) |
| `LightStateIconVFXResourceName` | FixedString | `""` | VFX for lightly obscured state (empty) |
| `IconPlaceRadius` | float | `0.5` | Radius for icon placement |
| `PatternClear` | fvec2 | `(1, 0)` | Dash pattern for clear visibility |
| `PatternHeavilyObscured` | fvec2 | `(0.05, 0.15)` | Dash pattern for heavily obscured |
| `PatternLightlyObscured` | fvec2 | `(0.2, 0.2)` | Dash pattern for lightly obscured |
| `PulsationLimits` | fvec2 | `(0.1, 0.4)` | Pulsation min/max range |
| `PulsationSpeed` | float | `1` | Pulsation animation speed |
| `RegularColor` | fvec3 | `(1, 1, 1)` | Default path line color (white) |
| `ColorPastLimit` | fvec3 | `(0.788, 0, 0.188)` | Path color beyond movement range (pinkish red) |
| `Width` | float | `0.025` | Path line width |

## Child Nodes

None — all data is root-level attributes.

## Patterns of Use

- Defines visual settings for AI/movement path display in the GUI
- Controls path line color, width, dash patterns, and icon VFX
- Uses `fvec2` for 2D dash patterns and `fvec3` for RGB colors (0–1 range)
- All VFX resource names are empty strings in vanilla — paths use geometry only

## Caveats & Gotchas

- **Single global config** — one root node with 16 fixed attributes, no child nodes
- Non-standard structure like `Color/GameColor` — scanner cannot process
- fvec2/fvec3 use `<float2>`/`<float3>` child elements, not `value` attribute

## Similarities to Other Nodes

Same flat-root pattern as `Color/GameColor`.
