# Node: `UnifiedTutorial`

> **Region**: [UnifiedTutorials](_REGION.md)
> **Folder**: `Tutorials/`
> **Source**: `Shared/Public/SharedDev/Tutorials/UnifiedTutorials.lsx` (primary, 142 nodes), `Gustav/Public/GustavDev/Tutorials/UnifiedTutorials.lsx` (1 node), `GustavX` (PhotoMode)
> **Total Nodes**: ~143+ combined

---

## Attributes

| Attribute | Type | Frequency | Examples | Notes |
|-----------|------|-----------|----------|-------|
| `UUID` | guid | always | `0dc3c736-083e-4195-856e-cd47f2a36e43` | Primary key |
| `TutorialName` | FixedString | always | `Camp`, `Short Rest`, `AvatarGaleItems` | Internal tutorial identifier |
| `DisplayTitle` | TranslatedString | always | — | Localized title shown to player |
| `Section` | uint8 | always | `14`, `3`, `17` | Tutorial section/category number |
| `InputType` | uint8 | ~138/143 | `0` | Input scheme (0 = both?) |
| `ModalType` | uint8 | ~138/143 | `0`, `15` | Modal display type |
| `KeyboardDescription` | TranslatedString | ~133/143 | — | KB+M description |
| `ControllerDescription` | TranslatedString | ~129/143 | — | Controller description |
| `LifeTime` | int32 | ~111/143 | `0` | Display duration (0 = until dismissed) |
| `KeyboardJournalDescription` | TranslatedString | ~79/143 | — | KB+M journal entry |
| `ControllerJournalDescription` | TranslatedString | ~81/143 | — | Controller journal entry |
| `KeyboardInputList` | TranslatedString | ~68/143 | — | KB+M input hints |
| `ControllerInputList` | TranslatedString | ~71/143 | — | Controller input hints |
| `ShowInSplitScreen` | bool | ~64/143 | `false` | Show in split-screen co-op |
| `WaitForEndDialog` | bool | ~26/143 | `true`, `false` | Delay until dialog ends |
| `HighlightedOption` | FixedString | ~23/143 | `Camp`, `ShortRest`, `LongRest` | UI element to highlight |
| `WaitForEndCC` | bool | ~4/143 | `false` | Wait for character creation to end |
| `WaitForLayers` | bool | ~3/143 | `false`, `true` | Wait for UI layers |

## Child Nodes

None.

## Patterns of Use

- Combines keyboard + controller tutorial descriptions in a single entry
- `Section` groups tutorials by game system (3 = exploration, 14 = combat, 17 = story, etc.)
- Many attributes are sparse — simpler tutorials have fewer fields
- `HighlightedOption` used on ~23 entries to highlight a specific UI element
- Wait flags control tutorial display timing relative to other game events

## Caveats & Gotchas

- Primary data in SharedDev (142 nodes), not Shared
- GustavDev adds 1 entry (`AvatarGaleItems`)
- GustavX adds PhotoMode tutorials
- Many attributes optional/sparse

## Similarities to Other Nodes

Related to `ModalTutorial` (simpler format) and `TutorialEvent` (trigger system). This is the unified replacement that combines KB + controller descriptions.
