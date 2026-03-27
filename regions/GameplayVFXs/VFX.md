# Node: `VFX`

> **Region**: [GameplayVFXs](_REGION.md)
> **Folder**: `VFX/`
> **Vanilla entries**: 52 (Shared)

---

## Attributes

| Attribute | Type | Frequency | Examples | Notes |
|-----------|------|-----------|----------|-------|
| `UUID` | guid | 52/52 | `6180810c-...` | Primary key |
| `VFXGameplayName` | FixedString | 52/52 | `VFX_AoE`, `VFX_Spell_Range`, `VFX_Spell_Move_And_Cast` | Gameplay VFX identifier |
| `VFXEffectName` | FixedString | 49/52 | `VFX_UI_Circle_Range_01`, `VFX_UI_CastAndMove_01` | Visual effect resource name |

## Child Nodes

*(None in vanilla data)*

## Patterns of Use

- Maps gameplay VFX identifiers to visual effect resource names.
- 3 entries lack `VFXEffectName` (gameplay name only without assigned visual).
- Used for spell range indicators, AoE circles, cast-and-move visuals, etc.

## Cross-References

| From | To | Via |
|------|----|-----|
| Spell system | VFX | `VFXGameplayName` lookup |

## Caveats & Gotchas

- Node name is `VFX`, region name is `GameplayVFXs` — these differ.

## Similarities to Other Nodes

- **PassivesVFX**: Also maps gameplay concepts to VFX resources.
