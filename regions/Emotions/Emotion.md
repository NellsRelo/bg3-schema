# Node: `Emotions` (singleton)

> **Region**: [Emotions](_REGION.md)
> **Source**: `Shared/Public/Shared/Animation/Emotions.lsx`
> **Structure**: Non-standard — single root node with nested Map structures, NOT a repeating-node collection.

---

## Structure

The `Emotions` region contains a **single** `Emotions` node with:
- `version` attribute (int32, currently `2`)
- One `Data` child containing two map-typed sections:

### EmotionToAnimSet

Maps emotion IDs (int32) to animation set names (FixedString):
```xml
<node id="EmotionToAnimSet">
  <children>
    <node id="Object" key="MapKey">
      <attribute id="MapKey" type="int32" value="1" />
      <children>
        <node id="MapValue">
          <attribute id="MapValue" type="FixedString" value="Neutral" />
        </node>
      </children>
    </node>
  </children>
</node>
```

### AnimSetToShortNames

Maps animation set names (FixedString) to weighted short-name lists:
```xml
<node id="AnimSetToShortNames">
  <children>
    <node id="Object" key="MapKey">
      <attribute id="MapKey" type="FixedString" value="Neutral" />
      <children>
        <node id="MapValue">
          <children>
            <node id="Object">
              <attribute id="Name" type="FixedString" value="<guid>" />
              <attribute id="Weight" type="float" value="0.15" />
            </node>
          </children>
        </node>
        <!-- more MapValue entries -->
      </children>
    </node>
  </children>
</node>
```

## Vanilla Statistics

- **EmotionToAnimSet**: Emotion IDs mapped to ~12 unique animation set names (e.g. `Neutral`)
- **AnimSetToShortNames**: Each set maps to multiple weighted animation short-name GUIDs

## Vanilla Scope

| Pack | Files |
|------|-------|
| Shared | 1 |

Single-file global emotion→animation configuration. Maps numeric emotion IDs to named animation sets, then maps those sets to weighted lists of animation short-names. Not directly moddable as individual entries — the entire file must be replaced.

## Cross-References

| From | To | Via |
|------|----|-----|
| — | — | — |

## Caveats & Gotchas

*(To be documented)*

## Similarities to Other Nodes

*(To be documented)*
