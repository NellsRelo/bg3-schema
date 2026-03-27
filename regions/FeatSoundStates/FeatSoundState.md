# Node: `FeatSoundState`

> **Region**: [FeatSoundStates](_REGION.md)
> **Folder**: `Feats/`
> **Source**: `Shared/Public/Shared/Feats/FeatSoundStates.lsx`
> **Total Nodes**: 0 (empty in vanilla)

---

## Attributes

| Attribute | Type | Frequency | Examples | Notes |
|-----------|------|-----------|----------|-------|
| *Empty* | — | — | — | No nodes in vanilla data |

## Child Nodes

None.

## Patterns of Use

- **Empty in vanilla** — the file exists (`FeatSoundStates.lsx`) but contains only the region shell with an empty root node
- Presumably intended for feat-specific Wwise sound state triggers, analogous to `FlagSoundStates`, `TagSoundStates`, `StatusSoundStates`
- Available for mods to add feat-triggered audio state changes

## Caveats & Gotchas

- Vanilla file is completely empty (just `<node id="root"/>`) — no schema to infer from data
- SharedDev does not have this file

## Similarities to Other Nodes

Same pattern as `FlagSoundState`, `TagSoundState`, `StatusSoundState` — but empty.
