# Node: `AvatarContainerTemplate`

> **Region**: [AvatarContainerTemplates](_REGION.md)
> **Folder**: `Lists/`
> **Source**: `Shared/Public/Shared/Lists/AvatarContainerTemplates.lsx`
> **Total Nodes**: ~1 (Shared only)

---

## Attributes

| Attribute | Type | Frequency | Examples | Notes |
|-----------|------|-----------|----------|-------|
| `UUID` | guid | x1 | `0928889d-f5d0-4b93-80e5-48c73f255289` | Primary key |
| `TemplateId` | guid | x1 | `d94c7491-0868-4444-b83c-82f5454d4b64` | FK → GameObjects template for avatar container |

## Child Nodes

None.

## Patterns of Use

- Only 1 entry in vanilla — defines the RootTemplate used for the player avatar's inventory container
- `TemplateId` points to a GameObjects template defining the container

## Caveats & Gotchas

- Single-entry region — effectively a global config value

## Similarities to Other Nodes

Similar to `CampChestTemplate` (also template-reference lists).
