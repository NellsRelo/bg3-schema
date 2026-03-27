# Node: `ProjectileDefault`

> **Region**: [ProjectileDefaults](_REGION.md)
> **Folder**: `ProjectileDefaults/`
> **Vanilla entries**: 2 (Shared)

---

## Attributes

| Attribute | Type | Frequency | Examples | Notes |
|-----------|------|-----------|----------|-------|
| `UUID` | guid | 2/2 | `4d88eda2-...` | Primary key |
| `ProjectileDefaultType` | uint8 | 2/2 | `0`, `1` | Projectile category |
| `ProjectileTemplateId` | guid | 2/2 | `6c2f2e14-...` | References projectile template (same for both) |

## Child Nodes

*(None in vanilla data)*

## Patterns of Use

- Only 2 entries differentiated by `ProjectileDefaultType` (0 and 1).
- Both reference the same projectile template.

## Cross-References

| From | To | Via |
|------|----|-----|
| ProjectileDefault | GameObjects (projectile templates) | `ProjectileTemplateId` |

## Caveats & Gotchas

- Very small region — only 2 entries in vanilla.

## Similarities to Other Nodes

*(None)*
