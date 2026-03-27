# Node: `TLScene`

> **Region**: [TLScene](_REGION.md)
> **Exists in**: Dialog timeline files only (not standalone)
> **Note**: Embedded region — no standalone data file in standard UnpackedData.

---

## Status

**Dialog-embedded region.** `TLScene` (Timeline Scene) is a top-level container node within
compiled dialog timeline files. It defines a cutscene/dialog timeline including:
- Actors and actor data
- Camera containers
- Effects and effect components
- Phases with sound events
- Timeline speakers and settings
- Transform/visibility channels

This is a deeply nested, complex structure that is not represented as a simple
repeating-node collection. Each dialog file has its own TLScene definition.

## Vanilla Scope

Not countable — one per dialog timeline file across thousands of dialogs.

## Cross-References

| From | To | Via |
|------|----|-----|
| — | — | — |

## Caveats & Gotchas

*(To be documented)*

## Similarities to Other Nodes

*(To be documented)*
