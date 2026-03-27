# Region: `FeatDescriptions`

> **Folder**: `Feats/`
> **Primary Node**: [FeatDescription](FeatDescription.md)
>
> 23 vanilla feat descriptions

---

## File Inventory

| Source | File | Entries | Version |
|--------|------|---------|---------|
| Shared | FeatDescriptions.lsx | 23 | — |
| SharedDev | FeatDescriptions.lsx | 23 | — |

## Region Structure

```xml
<region id="FeatDescriptions">
  <node id="root">
    <children>
      <node id="FeatDescription"> ... </node>
    </children>
  </node>
</region>
```

## Node Types

| Node | File | Description |
|------|------|-------------|
| FeatDescription | [FeatDescription.md](FeatDescription.md) | Display text for a feat |

## Cross-Region References

| Target Region | Via | Purpose |
|---------------|-----|---------|
| [Feats](../Feats/_REGION.md) | `ExactMatch` → `Feat.Name` | Links description to mechanical feat |

## Caveats

- **Folder ≠ Region**: Lives in `Feats/` folder but uses `FeatDescriptions` region.
- **23 entries** match the 23 vanilla feats.
