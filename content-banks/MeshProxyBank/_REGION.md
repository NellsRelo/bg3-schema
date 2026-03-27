# Region: `MeshProxyBank`

> **Category**: Environment
> **Primary Node**: [Resource](Resource.md)
>
> Registers mesh proxy assets — simplified LOD meshes for distance rendering.
> Flat resource structure.

---

## File Inventory

| Source | Path Pattern | Content |
|--------|-------------|---------|
| Shared | `Content/Assets/.../_merged.lsx` | Proxy mesh registrations |

**1 file in Shared** containing MeshProxyBank regions.

## Region Structure

```xml
<region id="MeshProxyBank">
  <node id="MeshProxyBank">
    <children>
      <node id="Resource"> ... </node>
    </children>
  </node>
</region>
```

## Node Types

| Node | File | Description |
|------|------|-------------|
| Resource | [Resource.md](Resource.md) | One per mesh proxy — flat, no child nodes |

## Notes

- Only 1 instance in Shared
- `Localized` attribute is optional — some entries omit it
- Used for VFX proxy meshes (collision/interaction proxies for particle effects)
