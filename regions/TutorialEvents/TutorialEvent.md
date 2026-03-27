# Node: `TutorialEvent`

> **Region**: [TutorialEvents](_REGION.md)
> **Folder**: `Tutorials/`
> **Vanilla entries**: 70 (Shared)

---

## Attributes

| Attribute | Type | Frequency | Examples | Notes |
|-----------|------|-----------|----------|-------|
| `UUID` | guid | 70/70 | `82a77570-...` | Primary key |
| `Name` | LSString | 70/70 | `Action_Depleted`, `Bonus_Depleted`, `Movement_Depleted` | Event identifier |
| `EventType` | uint8 | 70/70 | `1` | Event type (all vanilla use `1`) |
| `UserAction` | uint8 | 70/70 | `0` | User action type (all vanilla use `0`) |
| `ActionResource` | guid | 22/70 | `734cbcfb-...` | References action resource (when event ties to resource depletion) |

## Child Nodes

| Child | Frequency | Notes |
|-------|-----------|-------|
| `HotbarSlotFlags` | 5/70 | Hotbar-related trigger conditions |

## Patterns of Use

- Defines events that trigger tutorial popups.
- Event names indicate triggers: `Action_Depleted`, `First_Level_Up`, `First_Camp_Visit`, etc.
- `ActionResource` links to specific resources (spell slots, actions, etc.).

## Cross-References

| From | To | Via |
|------|----|-----|
| TutorialEvent | ActionResourceDefinitions | `ActionResource` |
| TutorialEvent | ModalTutorial | Event triggers tutorial display |

## Caveats & Gotchas

- `ActionResource` only present on 22 of 70 entries.

## Similarities to Other Nodes

- **ModalTutorials**: The content displayed when tutorial events fire.
