# Node: `Resource`

> **Region**: [VoiceBarkBank](_REGION.md)
> **Child Depth**: 1 (flat — no child nodes)

---

## Attributes

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `ID` | FixedString | UUID primary key | `12cef6a8-...` |
| `SourceFile` | LSString | Voice bark source file (.lsj) | `Mods/Gustav/Story/VoiceBarks/.../X.lsj` |
| `Localized` | bool | Localization flag | `False` |
| `_OriginalFileVersion_` | int64 | Engine version stamp | ... |

## Child Nodes

_(None — flat resource structure)_

## Caveats

- **No `Name` attribute** — the only bank type that lacks a human-readable name on Resource
