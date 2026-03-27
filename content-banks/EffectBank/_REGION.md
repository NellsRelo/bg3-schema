# Region: `EffectBank`

> **Category**: Scene
> **Primary Node**: [Resource](Resource.md)
>
> Defines visual effects (VFX) — particle systems, overlays, lights, and sound triggers.
> The most deeply nested bank type (up to 5 levels deep).

---

## File Inventory

| Source | Path Pattern | Content |
|--------|-------------|---------|
| Shared | `Content/Assets/Effects/Effects/.../_merged.lsx` | Gameplay VFX (spells, actions) |
| Shared | `Content/Assets/Effects/Effects/[PAK]_LightSources/_merged.lsx` | Light source effects (co-located with LightingBank) |

**98 files in Shared** containing EffectBank regions.

## Region Structure

```xml
<region id="EffectBank">
  <node id="EffectBank">
    <children>
      <node id="Resource"> ... </node>
    </children>
  </node>
</region>
```

## Node Types

| Node | File | Description |
|------|------|-------------|
| Resource | [Resource.md](Resource.md) | One per VFX — deeply nested (5 levels: Resource → EffectComponents → Properties → Property → Parameter) |

## Cross-Region References

| From | To | Via |
|------|----|-----|
| EffectBank.ID | GameObjects (StatusEffect, HitEffect, etc.) | Effect references in stats/game data |
| EffectBank.Dependencies.DependentResource.Object | Various banks | Material, texture, model dependencies |

## Co-located Banks

EffectBank is often co-located with:
- [LightingBank](../LightingBank/_REGION.md) (light source files)

## Notes

- 98 instances in Shared — covers all spell VFX, combat effects, ambient particles
- **Most deeply nested bank** — 5 levels deep
- Component `Name` identifies the VFX module type: `OverlayMaterial`, `Light`, `ParticleSystem`, `Sound`, `Decal`, etc.
