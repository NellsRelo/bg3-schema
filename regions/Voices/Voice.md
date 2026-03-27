# Node: `Voice`

> **Region**: [Voices](_REGION.md)
> **Folder**: `Voices/`

---

## Attributes

> 4 nodes in Shared (vanilla)

| Attribute | Type | Count | Examples | Notes |
|-----------|------|-------|----------|-------|
| `UUID` | guid | 4/4 | `15ead9db-7a73-4681-8848-5f1487ad4c68` | Primary key |
| `DisplayName` | TranslatedString | 4/4 | handle + version | Localized voice name |
| `BodyType` | uint8 | 4/4 | `0`, `1` | Body type this voice is for |
| `SpeakerUUID` | guid | 4/4 | `24247531-c432-4f0f-8f35-6c90c4844aa8` | Speaker entity reference |
| `TableUUID` | guid | 4/4 | `5ee56242-d07c-482e-9260-24529d1473a3` | Voice table group reference |

## Cross-References

| From | To | Via |
|------|----|-----|
| Voice.TableUUID | [Origin](../Origins/Origin.md) | Origin.VoiceTableUUID |
| Voice.UUID | [CCVOLine](../CharacterCreationVOLines/CharacterCreationVOLine.md) | Indirect via table lookups |

## Caveats & Gotchas

- Only 4 voices in vanilla Shared — 2 body types × 2 voice sets for player character.
- Companion voices are defined separately in Gustav/GustavDev Origins, not in the Voices region.

## Cross-References

| From | To | Via |
|------|----|-----|
| — | — | — |

## Caveats & Gotchas

*(To be documented)*

## Similarities to Other Nodes

*(To be documented)*
