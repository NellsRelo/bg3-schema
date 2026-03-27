# Region: `VoiceBarkBank`

> **Category**: Scene
> **Primary Node**: [Resource](Resource.md)
>
> Registers voice bark resources — short voiced lines that play outside dialog trees
> (combat callouts, ambient reactions, etc.).

---

## File Inventory

| Source | Path Pattern | Content |
|--------|-------------|---------|
| Gustav | `Content/Assets/Voicebarks/Act1/.../_merged.lsx` | Act 1 voice barks |
| Gustav | `Content/Assets/Voicebarks/Act2/.../_merged.lsx` | Act 2 voice barks |
| Gustav | `Content/Assets/Voicebarks/Act3/.../_merged.lsx` | Act 3 voice barks |

**0 files in Shared, 56 in Gustav** — voice barks are campaign-specific content.

## Region Structure

```xml
<region id="VoiceBarkBank">
  <node id="VoiceBarkBank">
    <children>
      <node id="Resource"> ... </node>
    </children>
  </node>
</region>
```

## Node Types

| Node | File | Description |
|------|------|-------------|
| Resource | [Resource.md](Resource.md) | One per voice bark — flat, no child nodes |

## Notes

- **No `Name` attribute** — the only bank type that lacks a human-readable name on Resource
- 56 instances in Gustav, 0 in Shared — voice barks are campaign-specific content
- Organized by game act (`Act1/`, `Act2/`, `Act3/`)
- Flat structure — no child nodes
