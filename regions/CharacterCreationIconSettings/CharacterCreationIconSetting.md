# Node: `CharacterCreationIconSetting`

> **Region**: [CharacterCreationIconSettings](_REGION.md)
> **Folder**: `CharacterCreation/`

---

## Attributes

> 42 nodes in Shared (vanilla)

| Attribute | Type | Count | Examples | Notes |
|-----------|------|-------|----------|-------|
| `UUID` | guid | 42/42 | `4a27e7ef-d111-40e3-a111-6da7655ce4b6` | Primary key |
| `BodyShape` | uint8 | 42/42 | `0`, `1` | Body build filter (0=Regular, 1=Strong) |
| `RootTemplate` | guid | 42/42 | `8570d6ed-42d9-47a4-886d-c61e125022ca` | Character template for icon rendering |
| `HeadAppearanceUUID` | guid | 8/42 | `7c538187-8c7f-4557-b850-e41a870c394b` | Specific head to use for icon |

## Child Nodes

### SlotNames

| Node | Count | Notes |
|------|-------|-------|
| `SlotNames` | 42 entries | Each icon setting has slot name children |

## Caveats & Gotchas

- Controls CC icon rendering for different body shapes and templates.
- `HeadAppearanceUUID` is only set for a few entries that need a specific head appearance.

## Cross-References

| From | To | Via |
|------|----|-----|
| — | — | — |

## Caveats & Gotchas

*(To be documented)*

## Similarities to Other Nodes

*(To be documented)*
