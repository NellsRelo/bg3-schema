# Region: `PhysicsBank`

> **Category**: Environment
> **Primary Node**: [Resource](Resource.md)
>
> Registers physics collision assets — references to compiled `.bin` physics files.
> Flat resource structure — simplest bank type.

---

## File Inventory

| Source | Path Pattern | Content |
|--------|-------------|---------|
| Shared | `Content/Assets/Tilesets/.../_merged.lsx` | Tileset physics collision |
| Gustav | `Content/Assets/.../_merged.lsx` | Campaign physics collision |

**51 files in Shared, 1 in Gustav** containing PhysicsBank regions.

## Region Structure

```xml
<region id="PhysicsBank">
  <node id="PhysicsBank">
    <children>
      <node id="Resource"> ... </node>
    </children>
  </node>
</region>
```

## Node Types

| Node | File | Description |
|------|------|-------------|
| Resource | [Resource.md](Resource.md) | One per physics asset — flat, no child nodes |

## Cross-Region References

| From | To | Via |
|------|----|-----|
| PhysicsBank.ID | GameObjects | `PhysicsTemplate` — object physics collision |
| PhysicsBank.ID | [TileSetBank](../TileSetBank/_REGION.md) | `Tile.PhysicsGUID` — tile physics collision |

## Notes

- 51 instances in Shared, 1 in Gustav
- Flat structure — no child nodes
- Physics data is compiled into `.bin` files; the bank just registers them
