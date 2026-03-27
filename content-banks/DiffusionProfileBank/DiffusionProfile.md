# Node: `DiffusionProfile`

> **Region**: [DiffusionProfileBank](_REGION.md)
> **Child Depth**: 1 (flat — no child nodes)

---

## Attributes

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `ID` | FixedString | UUID primary key | `d769c6b6-12e9-083e-35e3-02695252e44d` |
| `Name` | LSString | Profile name | `BLD_Druids_Camp_Tent_A_SS` |
| `Localized` | bool | Localization flag | `False` |
| `ScatterColor` | fvec3 | Subsurface scatter color | `0.11926401 0.28012437 0.3636039` |
| `ScatterDistance` | float | Scatter distance in world units | `200` |
| `TransmissionTint` | fvec3 | Transmission color tint | `0.11657577 0.28445205 0.3636039` |
| `ThickObjectTransmission` | bool | Enable thick object transmission | `False` |
| `ThicknessRemapMin` | float | Thickness remap minimum | `0` |
| `ThicknessRemapMax` | float | Thickness remap maximum | `1` |
| `DualSpecularMix` | float | Dual specular lobe mix ratio | `0.85` |
| `DualSpecularRoughnessA` | float | Primary specular roughness | `0.75` |
| `DualSpecularRoughnessB` | float | Secondary specular roughness | `1.3` |
| `_OriginalFileVersion_` | int64 | Engine version stamp | `144115198813274213` |

## Child Nodes

_(None — flat resource structure)_

## Cross-References

| From | To | Via |
|------|----|-----|
| DiffusionProfile.ID | [MaterialBank](../MaterialBank/_REGION.md) | `DiffusionProfileUUID` |

## Notes

- 17 instances in Shared — typically for skin, cloth, and organic surface materials
- Often co-located with [VirtualTextureBank](../VirtualTextureBank/_REGION.md) in the same file
