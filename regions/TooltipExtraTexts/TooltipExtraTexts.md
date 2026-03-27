# Node: `TooltipExtraTexts`

> **Region**: [TooltipExtraTexts](_REGION.md)
> **Folder**: `TooltipExtras/`
> **Vanilla entries**: 101 (Shared)

---

## Attributes

| Attribute | Type | Frequency | Examples | Notes |
|-----------|------|-----------|----------|-------|
| `UUID` | guid | 101/101 | `0023d784-...` | Primary key |
| `Text` | TranslatedString | 101/101 | handle `h4c39...` | Extra tooltip text snippet |

## Child Nodes

*(None in vanilla data)*

## Patterns of Use

- Minimal schema — just UUID + translated text.
- Each entry is a standalone tooltip text snippet referenced by the UI tooltip system.
- 101 entries in vanilla Shared.

## Cross-References

| From | To | Via |
|------|----|-----|
| UI tooltip system | TooltipExtraTexts | `UUID` lookup |
| Stats TXT `DealDamage()` functor | TooltipExtraTexts | 6th positional argument is the TooltipExtraTexts UUID |
| TooltipExtraTexts.Text | `.loca.xml` | TranslatedString handle ? localization entry |

## DealDamage Functor Connection

The `DealDamage` functor in Stats TXT has an optional 6th positional argument that references a `TooltipExtraTexts` UUID:

```
DealDamage(1d8,Necrotic,,,,{TooltipExtraTexts-UUID})
```

This causes the game to render the localized tooltip text from this region alongside the damage display. The three-way cross-reference:

1. `.loca.xml` defines the display text (via `contentuid`)
2. `TooltipExtraTexts.lsx` links the UUID to the localization handle
3. Stats TXT `DealDamage(...)` references the `TooltipExtraTexts` UUID

## Caveats & Gotchas

- Only 2 attributes — the simplest node type in the schema. UUID is the only way to reference these entries.
- **Missing localization** — If the `Text` TranslatedString handle doesn't resolve in `.loca.xml`, the tooltip shows `[...]` placeholder.
- **Positional argument** — The DealDamage functor connection uses the 6th positional arg. All preceding args (even if empty) must be present as commas: `DealDamage(dice,type,,,,uuid)`.

## Similarities to Other Nodes

- **TooltipUpcastDescriptions**: Same folder, similar pattern but adds a `Name` attribute for keyed lookup.
