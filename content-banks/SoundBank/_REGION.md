# Region: `SoundBank`

> **Category**: Scene
> **Primary Node**: [Resource](Resource.md)
>
> Registers audio assets — individual sound events from Wwise `.bnk` sound banks.
> Flat resource structure with extensive audio metadata.

---

## File Inventory

| Source | Path Pattern | Content |
|--------|-------------|---------|
| Shared | `Content/Assets/Sounds/Actions/[PAK]_Actions/_merged.lsx` | Action sound events |
| Shared | `Content/Assets/Sounds/.../_merged.lsx` | Other sound categories |

**80 files in Shared** containing SoundBank regions.

## Region Structure

```xml
<region id="SoundBank">
  <node id="SoundBank">
    <children>
      <node id="Resource"> ... </node>
    </children>
  </node>
</region>
```

## Node Types

| Node | File | Description |
|------|------|-------------|
| Resource | [Resource.md](Resource.md) | One per sound event — flat, no child nodes |

## Cross-Region References

| From | To | Via |
|------|----|-----|
| SoundBank.ID | [SkeletonBank](../SkeletonBank/_REGION.md) | `Bones.MapValue.SoundObjectIndex` — bone sound triggers |
| SoundBank.SoundEventID | Wwise audio engine | Runtime sound playback |

## Notes

- 80 instances in Shared — covers all gameplay sound effects
- `Duration = -1` indicates a looping sound
- `GMSoundCategory`/`GMSubSection` are Game Master mode attributes (rare)
