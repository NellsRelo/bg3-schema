# Node: `ScriptMaterialOverridePreset`

> **Region**: [ScriptMaterialOverridePresets](_REGION.md)
> **Source**: `Gustav/Public/Gustav/ScriptMaterialOverrides/ScriptMaterialOverridePresets.lsx`

---

## Attributes

| Attribute | Type | Frequency | Examples | Notes |
|-----------|------|-----------|----------|-------|
| `PresetName` | FixedString | always | `S_HAG_LeftEyeBlind`, `S_HAG_RightEyeBlind` | Preset identifier |
| `UUID` | guid | always | — | Primary key |

## Child Nodes

### ParameterUUIDs

Container for one or more `ParameterUUID` children linking to [ScriptMaterialOverrideParameter](../ScriptMaterialOverrideParameters/ScriptMaterialOverrideParameter.md) entries:

```xml
<node id="ParameterUUIDs">
  <children>
    <node id="ParameterUUID">
      <attribute id="Object" type="guid" value="<uuid>" />
    </node>
  </children>
</node>
```

Each preset in vanilla has 2 ParameterUUID children (one per `Blindness_L` / `Blindness` parameter).

## Vanilla Scope

| Pack | Nodes |
|------|-------|
| Gustav | 2 |

Groups material override parameters into named presets for scripted visual effects (e.g. Hag eye blindness).

## Cross-References

| From | To | Via |
|------|----|-----|
| — | — | — |

## Caveats & Gotchas

*(To be documented)*

## Similarities to Other Nodes

*(To be documented)*
