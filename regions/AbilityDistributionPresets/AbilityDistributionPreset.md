# Node: `AbilityDistributionPreset`

> **Region**: [AbilityDistributionPresets](_REGION.md)
> **Folder**: `CharacterCreationPresets/`
> **Vanilla entries**: 22 (Shared; also present in SharedDev)

---

## Attributes

| Attribute | Type | Frequency | Examples | Notes |
|-----------|------|-----------|----------|-------|
| `UUID` | guid | 22/22 | `dfba0a23-...` | Primary key |
| `ClassUUID` | guid | 22/22 | `d8cadb42-...` | References ClassDescription |
| `Strength` | int32 | 22/22 | `15`, `10`, `14` | Default STR score |
| `Dexterity` | int32 | 22/22 | `13`, `14`, `10` | Default DEX score |
| `Constitution` | int32 | 22/22 | `14`, `13` | Default CON score |
| `Intelligence` | int32 | 22/22 | `8`, `16` | Default INT score |
| `Wisdom` | int32 | 22/22 | `12`, `15` | Default WIS score |
| `Charisma` | int32 | 22/22 | `10`, `12`, `16` | Default CHA score |

## Child Nodes

*(None in vanilla data)*

## Patterns of Use

- One preset per class — defines recommended ability score distributions.
- All 22 entries have all attributes (no optional fields).
- Scores use the standard point-buy range (8–16).

## Cross-References

| From | To | Via |
|------|----|-----|
| AbilityDistributionPreset | ClassDescriptions | `ClassUUID` |

## Caveats & Gotchas

- 22 presets for 12 classes — includes subclass-specific distributions.

## Similarities to Other Nodes

- **CompanionPresets**: Also per-class CC defaults but for companions.
