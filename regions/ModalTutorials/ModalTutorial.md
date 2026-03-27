# Node: `ModalTutorial`

> **Region**: [ModalTutorials](_REGION.md)
> **Folder**: `Tutorials/`
> **Vanilla entries**: 29 (Shared)

---

## Attributes

| Attribute | Type | Frequency | Examples | Notes |
|-----------|------|-----------|----------|-------|
| `UUID` | guid | 29/29 | `62bd3369-...` | Primary key |
| `TutorialName` | FixedString | 29/29 | `TUT_Combat`, `TUT_Help`, `TUT_Revivify` | Internal tutorial ID |
| `TutorialID` | int32 | 29/29 | `0`, `1`, `2` | Sequential integer ID |
| `DisplayTitle` | TranslatedString | 29/29 | handle `hbee6...` | Title shown in tutorial popup |
| `ControllerDescription` | TranslatedString | 29/29 | handle `h7e0e...` | Tutorial text for controller input |
| `KeyboardDescription` | TranslatedString | 29/29 | handle `h1de3...` | Tutorial text for keyboard input |
| `ModalType` | uint8 | 29/29 | `0`, `1`, `3` | Type of modal display |
| `Section` | uint8 | 29/29 | `2`, `13` | UI section grouping |
| `WaitForEndDialog` | bool | 29/29 | `true` | Wait for dialog to finish before showing |

## Child Nodes

*(None in vanilla data)*

## Patterns of Use

- All 29+ entries have all attributes — no optional fields.
- Separate text for controller vs keyboard (different button prompts).
- `WaitForEndDialog` is `true` for all vanilla entries.

## Cross-References

| From | To | Via |
|------|----|-----|
| TutorialEvents | ModalTutorial | `TutorialID` match |

## Caveats & Gotchas

- `TutorialID` is int32, not guid — used for cross-referencing.

## Similarities to Other Nodes

- **TutorialEvents**: Triggers that cause tutorials to display.
