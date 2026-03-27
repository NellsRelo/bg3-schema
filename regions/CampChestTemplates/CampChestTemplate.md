# Node: `CampChestTemplate`

> **Region**: [CampChestTemplates](_REGION.md)
> **Folder**: `Lists/`
> **Source**: `Shared/Public/Shared/Lists/CampChestTemplates.lsx`
> **Total Nodes**: ~5 (Shared only)

---

## Attributes

| Attribute | Type | Frequency | Examples | Notes |
|-----------|------|-----------|----------|-------|
| `UUID` | guid | x5 | `6bf69d49-2428-4823-a6f2-21383a66395e` | Primary key |
| `TemplateId` | guid | x5 | `96eab9d1-74b1-42f7-b1ad-061a9fcea8c4`, `f68b5862-887c-4adf-b9f8-bb29e4d73b0f` | FK → GameObjects template for camp chest |

## Child Nodes

None.

## Patterns of Use

- Defines the 5 camp chest templates (traveler’s chests in the camp area)
- Each entry points to a different RootTemplate via `TemplateId`
- Used to spawn camp storage containers that persist between long rests

## Caveats & Gotchas

- Fixed set of 5 — one per party camp chest slot

## Similarities to Other Nodes

Same structure as `AvatarContainerTemplate` (UUID + TemplateId pattern).
