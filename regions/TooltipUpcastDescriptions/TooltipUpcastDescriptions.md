# Node: `TooltipUpcastDescriptions`

> **Region**: [TooltipUpcastDescriptions](_REGION.md)
> **Folder**: `TooltipExtras/`
> **Vanilla entries**: 20 (Shared)

---

## Attributes

| Attribute | Type | Frequency | Examples | Notes |
|-----------|------|-----------|----------|-------|
| `UUID` | guid | 20/20 | `12d102c8-...` | Primary key |
| `Name` | FixedString | 20/20 | `Damage`, `Projectile_MainHandAttack`, `Healing` | Key for lookup; matches spell/status property names |
| `Text` | TranslatedString | 20/20 | handle `hf8a8...` | The upcast tooltip text shown in UI |

## Child Nodes

*(None in vanilla data)*

## Patterns of Use

- Each entry provides a named text snippet describing how a spell property scales when upcast.
- `Name` values are identifiers like `Damage`, `Healing`, `Projectile_MainHandAttack` — referenced by the tooltip system to inject upcast descriptions.

## Cross-References

| From | To | Via |
|------|----|-----|
| Spell tooltips | TooltipUpcastDescriptions | `Name` match |

## Caveats & Gotchas

- `Name` is a `FixedString`, not a `TranslatedString` — it is a lookup key, not displayed directly.

## Similarities to Other Nodes

- **TooltipExtraTexts**: Same folder, similar pattern (UUID + text), but for extra tooltip snippets rather than upcast descriptions.
