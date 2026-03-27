# Node: `Attitudes` (singleton)

> **Region**: [Attitudes](_REGION.md)
> **Source**: `Shared/Public/Shared/Animation/Attitudes.lsx`
> **Structure**: Non-standard — single root node with nested Map structures, NOT a repeating-node collection.

---

## Structure

The `Attitudes` region contains a **single** `Attitudes` node (no UUID) with one `Data` child.
`Data` has three map-typed children:

### Fidget

Map of `FixedString` → list of animation GUIDs.
```xml
<node id="Fidget">
  <children>
    <node id="Object" key="MapKey">
      <attribute id="MapKey" type="FixedString" value="Default" />
      <children>
        <node id="MapValue">
          <attribute id="Object" type="FixedString" value="<animation-guid>" />
        </node>
        <!-- more MapValue children -->
      </children>
    </node>
  </children>
</node>
```

### AdditiveIdle

Same map structure as Fidget — maps string keys to lists of animation GUIDs.

### Pose

Same map structure as Fidget — maps string keys to lists of animation GUIDs.

## Vanilla Statistics

- **MapKey entries across all sections**: ~75 unique keys (mostly GUIDs, plus `Default`)
- Each key maps to multiple animation resource GUIDs via `MapValue` children

## Vanilla Scope

| Pack | Files |
|------|-------|
| Shared | 1 |

Single-file global animation attitude configuration. Maps named attitude states to sets of fidget, additive idle, and pose animations. Not directly moddable as individual entries — the entire file must be replaced.

## Cross-References

| From | To | Via |
|------|----|-----|
| — | — | — |

## Caveats & Gotchas

*(To be documented)*

## Similarities to Other Nodes

*(To be documented)*
