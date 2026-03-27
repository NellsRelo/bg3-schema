# Region: `ScriptBank`

> **Category**: Scene
> **Primary Node**: [Resource](Resource.md)
>
> Registers script/behavior resources — item scripts and character scripts used for
> gameplay behaviors. Each entry references a compiled script file.

---

## File Inventory

| Source | Path Pattern | Content |
|--------|-------------|---------|
| Shared | `Content/Assets/Scripts/.../_merged.lsx` | Shared script registrations |
| Gustav | `Content/Assets/Scripts/.../_merged.lsx` | Campaign script registrations |

**7 files in Shared, 7 in Gustav** containing ScriptBank regions.

## Region Structure

```xml
<region id="ScriptBank">
  <node id="ScriptBank">
    <children>
      <node id="Resource"> ... </node>
    </children>
  </node>
</region>
```

## Node Types

| Node | File | Description |
|------|------|-------------|
| Resource | [Resource.md](Resource.md) | One per script — contains empty Parameters child |

## Notes

- `Parameters` child node is always empty — parameters are defined within the script file itself
- Script types: `.itemScript` (item behaviors), `.charScript` (character behaviors)
